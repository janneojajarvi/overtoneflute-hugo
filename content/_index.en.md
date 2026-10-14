---
title: "Home"
---

## Your Online Resource for Overtone and Willow Flutes

Learn to play the overtone flute (willow flute) with our free tutorials, sheet music, and guides. Explore the ancient Scandinavian sound and harmonic music today.

_“Overtone flute, willow flute, pitkähuilu, sälgflöjt, seljefløyte, pikkvile, obertonflöte, flûte harmonique, koncovka, калюка...”_

The objective of this site is to offer as much information, self-study material, repertoire (sheets & audio) and listening tips on the Scandinavian overtone flute, in one place. This site focuses especially on side-blown overtone flutes with no finger holes, though all the exercises and tunes can be played with most of the overtone flutes (with no finger holes).

Check out our [free fingering charts for willow flute](soitto-opas/sormitusmerkinnat/) here.

## Video of the week

<script>
  // Lista YouTube-videoiden ID:istä (voit lisätä tähän niin paljon videoita kuin haluat)
  const weeklyVideos = [
      sQxQA46WuaY",
    "i54uu2Lc7jk",
    "P0V0oLu799Y",
    "sEURxC5CeLc",
    "iZlH1ET5ouc",
    "FUWEN3dYwzY",
    "pn1mn-RCiZ0",
    "9Sm7pcVfbqQ",
    "niqDIUnEfLU",
    "5T9E6Fvv8II",
    "Hv2vAQMpQps",
    "s1Kf1DJXrHs",
    "rceyUZqBgE8",
    "dxNrQ3QkADA",
    "B--FIbZd27o",
    "ezureVn-cJQ",
    "qDIK3JlYpeo",
    "nVRmnqPDj2E",
    "bgYVT_lxlxs",
    "x2oW18XS6tk",
    "1KqIbTe6chY",
    "rYG9ZZch8QI",
    "NCiCMhig0z0",
    "y9ndzf_ev2Y",
    "fNbs9eGK04s",
    "0_W2Osel9gk",
    "4lwnKR4vbLE",
    "KI8mXl3xNN0",
    "dCp6w6bf2NA",
    "4a4rB6TDsOw",
    "wjPfYymfcgs",
    "ICU7RAp2frE",
    "iYWuc3qR5ys",
    "DYN16utru1o",
    "Mk2obS_jEpc",
    "xwRVLzKi-7Y",
    "gMH0XyWw9r4",
    "8ceUoWrF-EU",
    "B3FIi7eS3i8",
    "BAcgpamZNEM",
    "Q0Mbsewq63o",
    "E5FgUyyDhn8",
    "vLe7g6HOWeM",
    "DP6_I6zEcZc",
    "F1fl60ypdLs",
    "Z8Z51no1TD0",
    "B0guALHZg30",
    "jad2oY7elzA"
    // Lisää tähän halutessasi lisää video-ID:itä pilkulla erotettuna, esim:
    // "TOINEN_VIDEO_ID",
    // "KOLMAS_VIDEO_ID"
  ];

  // Apufunktio viikkonumeron laskemiseen, jotta video vaihtuu aina kerran viikossa
  function getWeekNumber(d) {
    d = new Date(Date.UTC(d.getFullYear(), d.getMonth(), d.getDate()));
    d.setUTCDate(d.getUTCDate() + 4 - (d.getUTCDay()||7));
    var yearStart = new Date(Date.UTC(d.getUTCFullYear(),0,1));
    var weekNo = Math.ceil((((d - yearStart) / 86400000) + 1)/7);
    return weekNo;
  }

  // Valitaan video viikkonumeron perusteella
  const now = new Date();
  const weekIndex = getWeekNumber(now) % weeklyVideos.length;
  const selectedVideoId = weeklyVideos[weekIndex];

  // Upotetaan iframe sivulle dynaamisesti
  const container = document.getElementById('weekly-video-container');
  container.innerHTML = `
    <iframe width="100%" height="450" src="https://www.youtube-nocookie.com/embed/${selectedVideoId}" title="Viikon video" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
  `;
</script>


Most of the exercises and tunes on this site are written for a flute tuned in D, but you can anyway play them with a flute of any key, though most of the audio samples are played with a D-flute. Congratulations to you that you have reached to this page and are perhaps willing to learn to play this ancient instrument. You are warmly welcome!

If you'd like to support the maintenance of this page, you can purchase a PDF sheet music book 'Traditional Folk Tunes for Willow Flute' [here](https://payhip.com/b/n04oe).

© Janne Ojajärvi
