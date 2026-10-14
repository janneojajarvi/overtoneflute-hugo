---
title: "Etusivu"
---

<div class="tc pv2">
  <img src="/overtoneflute-hugo/images/banner.jpg" alt="Pitkähuilun suukappale" style="max-width: 100%; height: auto; border-radius: 2px;">
</div>
 
<p style="font-style: italic; color: #a0aec0; margin-top: 1.5rem; margin-bottom: 1.5rem;">
“Pitkähuilu, yläsävelhuilu, overtoneflute, willow flute, sälgflöjt, seljefløyte, pikkvile…”
</p>

<p style="font-size: 1.05rem; line-height: 1.6; margin-bottom: 1.5rem;">
Tämä sivusto pyrkii tarjoamaan tietoa, oppimateriaalia, ohjelmistoa (nuotteineen ja ääninäytteineen) sekä kuunteluvinkkejä soittimesta jota kutsutaan muun muassa nimillä pitkähuilu ja yläsävelhuilu. Tässä tapauksessa yläsävelhuilusta puhuttaessa viitataan sormiaukottomaan sivusta tai päästä puhallettavaan huiluun.
</p>

<div id="weekly-video-container" style="margin: 20px 0;">
  <!-- Viikon video latautuu tähän -->
</div>

<script>
  // Lista YouTube-videoiden ID:istä (voit lisätä tähän niin paljon videoita kuin haluat)
  const weeklyVideos = [
      "sQxQA46WuaY",
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


<h3 style="margin-top: 2rem; margin-bottom: 1rem;">Video of the week</h3>

<p style="font-size: 1.05rem; line-height: 1.6; margin-top: 1.5rem; margin-bottom: 1.5rem;">
Sivuston materiaaleja voi hyödyntää eri sävellajeihin rakennetuilla huiluilla, vaikkakin suurin osa sivuston ääninäytteistä on soitettu D-vireisellä pitkähuilulla. Vaikka kappaleet ja harjoitukset ovatkin sivustolla nuotteina, ei niiden soittoon tarvitse kuitenkaan välttämättä nuotinlukutaitoa. Riittää kun soitat ääninäytteiden mukana ja katsot nuottilapuista sormitukset (auki/kiinni). Onnittelut sinulle joka olet löytänyt tämän marginaalisen ja ensi kuulemalta mahdollisesti oudon kuuloisen soittimen pariin! Pitkähuiluissa piilee potentiaalia, josta suurinta osaa ei ole vielä hyödynnetty. Tervetuloa oppimaan pitkähuilun soittoa!
</p>

<p style="font-size: 1.05rem; line-height: 1.6; margin-bottom: 2rem;">
Jos haluat tukea tämän sivun ylläpitoa, voit ostaa pdf-muotoisen nuottikirjan "Traditional Folk Tunes for Willow Flute" <a href="https://payhip.com/b/n04oe">täältä.</a>
</p>

<div style="display: flex; flex-direction: column; gap: 2rem; margin-top: 2rem; margin-bottom: 2rem;">
  <div>
    <img src="/overtoneflute-hugo/images/bassopitkahuilu.jpg" alt="Bassopitkähuilu" style="max-width: 100%; height: auto;">
    <p style="font-size: 0.9rem; color: #a0aec0; margin-top: 0.5rem;">Bassopitkähuilu (Rakentanut Vladiswar Nadishana)</p>
  </div>

  <div>
    <img src="/overtoneflute-hugo/images/d-pitkahuilu.jpg" alt="D-pitkähuilu" style="max-width: 100%; height: auto;">
    <p style="font-size: 0.9rem; color: #a0aec0; margin-top: 0.5rem;">D-pitkähuilu (Rakentanut Kirsi Vinkki)</p>
  </div>

  <div>
    <img src="/overtoneflute-hugo/images/erilaisia-pitkahuiluja.jpg" alt="Erilaisia pitkähuiluja" style="max-width: 100%; height: auto;">
    <p style="font-size: 0.9rem; color: #a0aec0; margin-top: 0.5rem;">Erilaisia pitkähuiluja</p>
  </div>
</div>

<div style="margin-top: 3rem; padding-top: 1rem; border-top: 1px solid #2d3748; font-size: 0.95rem;">
  <span>Overtoneflute.fi muilla kielillä: </span>
  <a href="https://janneojajarvi.github.io/overtoneflute-hugo/de/" style="color: #f0c040 !important;">Auf Deutsch</a> 
  <a href="https://janneojajarvi.github.io/overtoneflute-hugo/fr/" style="color: #f0c040 !important;">En Français</a> 
  <a href="https://janneojajarvi.github.io/overtoneflute-hugo/zh/" style="color: #f0c040 !important;">柳笛</a> 
  <a href="https://janneojajarvi.github.io/overtoneflute-hugo/en/" style="color: #f0c040 !important;">English</a> 
  <a href="https://janneojajarvi.github.io/overtoneflute-hugo/ja/" style="color: #f0c040 !important;">日本語</a>
</div>
