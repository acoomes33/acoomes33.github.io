---
layout: post
title:      "Good Vibes and Perseverance"
date:       2020-12-20 22:37:30 +0000
permalink:  good_vibes_and_perseverance
---


When it came to my final project, the choice was clear for me. I wanted to revisit one of my first projects of the year, a songwriting app for users to create personal songs and curate their own custom albums. I considered it one of my better ideas so far, and because it combined my love of music with my burgeoning addiction to coding, it seemed like a perfect fit for my final project for the course. Although, as with all coding projects, there were some obstacles and challenges that popped up along the way.

One of the major challenges I faced in this project was the functionality of adding songs to an album. In the album show page, I wanted a checkbox form that listed all the songs that were not yet assigned to an album, and when checked and submitted, would be added to the album. The main issue was getting and listing the songs themselves. I first created an AddSongsForm component that would be added onto the album show page, passing in the available songs and the album as props. I also connected it to the redux store, using 'react-redux' to pass in the addSongToAlbum dispatch action to the component. 

```
export const addSongToAlbum = (song, album) => {
  return (dispatch) => {
    fetch(`http://localhost:3000/songs/${song.id}`, {
      method: "PATCH",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({ album_id: album.id }),
    })
      .then((res) => res.json())
      .then((song) =>
        dispatch({ type: "ADD_SONG_TO_ALBUM_SUCCESS", payload: song })
      );
  };
};
```

This action allowed me to send a patch request for each song that was selected in order to change the song's album_id foreign key to the id received from the album argument. Once I had the redux portion working, I had to figure out a way to render the songs as a usable checkbox. This part was much more difficult than I imagined, but with loads or perseverance and a little help from my buddy Google, I had found a solution to my problems. One of the important pieces to the puzzle was setting up a proper local state with a checkboxes property with a reducer function that looked a little something like this: 

```
state = {
    checkboxes: this.props.songs.reduce(
      (options, option) => ({
        ...options,
        [option.name]: false,
      }),
      {}
    ),
  };
```

This allowed me to take in the songs prop and reduce it to an object with the song name as a key, and a boolean value that would indicate whether a song had been selected or not. Once I had that up and running, it was just a matter of sending a fetch request for each updated song and presto, the functionality was complete! All in all, it was the perfect app for  my final project, as it showed my growth from a simple Sinatra project to a combined front and back-end project using multiple languages and frameworks. It's been a fun journey, and it is just getting started!
