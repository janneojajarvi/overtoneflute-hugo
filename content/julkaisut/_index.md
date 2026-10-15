---
title: "Pitkähuilujulkaisut"
---

<p style="font-size: 1.05rem; line-height: 1.6; margin-bottom: 1.5rem;">
Tässä epäsäännöllisen säännöllisesti päivittyvä lista pitkähuiluun liittyvistä julkaisuista sekä pitkähuilun soittoa sisältävistä äänitteistä. Jos huomaat, että jokin julkaisu puuttuu niin vinkkaa toki :)
</p>

<h3 style="margin-top: 2rem; margin-bottom: 1rem;">Nuotit</h3>

<p style="line-height: 1.8; margin-bottom: 1.5rem;">
<a href="https://payhip.com/b/n04oe" target="_blank" rel="noopener" style="color: #ed8936; text-decoration: underline;">UUSI DIGITAALINEN NUOTTIJULKAISU: Ojajärvi, Janne: Traditional Folk Tunes for Willow Flute (2024)</a><br />
Goss, Catherine. 2023. Tunes for Willow Flutes.<br />
Ojajärvi, Janne: <a href="https://kansanmusiikkiliitto.fi/tuote/ojajarvi-janne-pitkahuilu-opas-sormireiattomien-ylasavelhuilujen-soittamiseen-ja-rakentamiseen" target="_blank" rel="noopener" style="color: #ed8936; text-decoration: underline;">Pitkähuilu – Opas sormireiättömien yläsävelhuilujen soittamiseen ja rakentamiseen</a> (2022).
</p>

<h3 style="margin-top: 2rem; margin-bottom: 1rem;">Äänitteet</h3>

<!-- Tähän diviin skripti lataa levyt automaattisesti aakkosjärjestyksessä -->
<div id="album-list" style="line-height: 1.8; margin-bottom: 1.5rem; font-size: 0.95rem;">
  Ladataan äänitteitä...
</div>

<h3 style="margin-top: 2rem; margin-bottom: 1rem;">Kirjallisuus</h3>

<ul style="line-height: 1.8;">
  <li>Erkeus, A., Gustafsson, R., Kåll, M., Näslund, Å. &amp; Oijens, K. 1979. <em>Instrument att bygga och spela på – Ljudlekslänken</em>. S. 22.</li>
  <li>Goss, Catherine. 2023. <em>Tunes for Willow Flutes</em>.</li>
  <li>Joutsenlahti, Riitta-Liisa. 2000. <em>Sormireiätön pilli – Kokemuksia ja näkemyksiä pitkähuilusta</em>.</li>
  <li>Joutsenlahti, Riitta-Liisa. 1996. <em>Pedipaketti: Pitkähuilu - soitto-opas</em>.</li>
  <li>Leisiö, Timo. 1983. <em>Suomen ja Karjalan vanhankantaiset torvi- ja pillisoittimet</em>.</li>
  <li>Lund, Cajsa S. 2003. <em>Den gröna musiken</em>. s. 5-6.</li>
  <li>Nieminen, Rauno. 2000. Styrbjörn Bergelt – pitkähuilun taitaja, <em>Friiti</em> 3/2000, 10–11.</li>
  <li>Nieminen, Rauno. 2000. Soittimia Rakentamaan, Pitkähuilu, <em>Friiti</em> 3/2000, 8–10.</li>
  <li>Nieminen Rauno. 2006. <em>Kansansoittimet. Tekniset Käden taidot</em>.</li>
  <li>Ojajärvi, Janne. 2022. <em>Pitkähuilu - Opas sormireiättömien yläsävelhuilujen soittamiseen ja rakentamiseen</em>.</li>
  <li>Yvert, Jean-Pierre. 1996. <em>Spela sälgflöjt – Playing the willow flute</em>.</li>
</ul>

<!-- PIILOTETTU TYÖKALU / LOMAKE UUSIEN LISÄYKSEEN -->
<div style="margin-top: 3rem; border-top: 1px dashed #4a5568; padding-top: 1rem;">
  <details>
    <summary style="cursor: pointer; color: #ed8936; font-weight: bold;">[ Piilotettu työkalu: Lisää uusi levy listaan ]</summary>
    <div style="margin-top: 1rem; background-color: #1a202c; padding: 15px; border-radius: 4px; border: 1px solid #4a5568;">
      <p style="font-size: 0.9rem; margin-bottom: 10px; color: #a0aec0;">Syötä uuden levyn tiedot, niin työkalu lisää sen listaan ja näyttää valmiin koodin:</p>
      <input type="text" id="new-album" placeholder="Esim. Artisti: Levyn nimi (Vuosi): 1, 3" style="width: 100%; padding: 8px; margin-bottom: 10px; background-color: #2d3748; color: #fff; border: 1px solid #4a5568; border-radius: 4px;" />
      <button onclick="addAlbum()" style="background-color: #ed8936; color: #1a202c; font-weight: bold; padding: 8px 15px; border: none; border-radius: 4px; cursor: pointer;">Lisää ja lajittele</button>
      <div id="output-code" style="margin-top: 10px; font-family: monospace; font-size: 0.85rem; color: #63b3ed; word-break: break-all;"></div>
    </div>
  </details>
</div>

<script>
  // Kaikki äänitteet taulukkona
  let albums = [
    "Ale Möller & Lena Willemark: Nordan (1994): 15",
    "Andrew Cronshaw: Ochre (2004): 2",
    "Arto Järvelä & Tapani Varis (2018): 2, 7, 9, 11",
    "Ånon Egeland: Ånon Egeland (1999): 12",
    "Blå Bergens Borduner: Blå Bergens Borduner (1993): 8, 15",
    "Buddha-Bar: Buddha Bar XIV: Zoohacker, Laar: Tilinko (2012): 12",
    "Bukkene Bruse – Bukkene Bruse (1993): 2",
    "Bukkene Bruse - Åre (1995): 3",
    "Bäsk: Kennemark, Simonson, Källman (2011): 2",
    "Celtic Muse: Crossroads: Celtic Harp, Finnish Kantele and Woodwinds (2009): 3",
    "Christian Oller, Jean-Pierre Yvert & Michel Sanlaville: Funambules (1993): 2, 7",
    "Dutar: Idegen Vendég (2008): 8",
    "Eberhard Weber: Résumé (2012): 10",
    "Egil Storbekken: Helsing fra Østerdalen (2015): 15",
    "Egil Storbekken: Trolldans (2015): 7",
    "Eivind Groven: Med hardingfele og seljefløyte på nye og gamle vegar (1981): 1, 2, 3, 9",
    "Faun: Renaissance (2005): 7",
    "FiBo: The World is Born (2023)",
    "Fjøllmanntonar (1993): 11",
    "Freija: Kiekkumaralla, Kansanlauluja lapsille (2007): 10",
    "Freshet: Freshet (2004): 9",
    "Frifot: Frifot: (1991): 16",
    "Frifot: Järven (1997): 15",
    "Fränder: Fränder (2017): 1",
    "Gamle Folkemusikkinstrument - Langeleik - Slåttestev Og Slått (2009): 1, 2",
    "Gjallarhorn: Sjofn (2000): 10",
    "Groupa: Fjalar (2002): 2",
    "Groupa: Frost (2008): 2, 8",
    "Groupa: Imeland (1995): 1, 6",
    "Groupa: Kind of Folk, Vol. 1 Sweden (2016): 12",
    "Groupa: Kind of Folk, Vol. 2 Norway (2018): 1, 4, 6, 9",
    "Groupa: Kind of Folk, Vol. 3 Iceland (2020): 13, 14",
    "Groupa: Kind of Folk, Vol. 4 Iberia (2023): 5, 10",
    "Groupa: Lavalek (1998): 3, 6",
    "Groupa: Silent folk (2014): 3, 10",
    "Göran Månsson: Inland (2002): 7",
    "Hedningarna: Kaksi! (1992): 4, 11",
    "Hedningarna: Kult (2016): 8, 9, 12",
    "Hedningarna: Trä (1998): 9",
    "Hurja Halla: Riitti (2022): 3, 5, 6",
    "Hurja Halla: Surma hiihti (2025): 1, 7, 8",
    "I Hallingdal, I Hallingdal (1996): 27",
    "Ihtiriekko: Ihtiriekko (2002): 2",
    "Ivanzvuk: Калюка (2019): 1",
    "Jarmo Romppanen: Solmogen (2007): 9",
    "Jonas Simonson: Crane Dance (2007): 1, 6, 7, 12, 15, 17",
    "Jonas Simonson: Songs in Meantone (2011): 6",
    "Jouhiorkesteri: Nikodemus (2008): 3",
    "KhaRa: Meryachenie (2016): 5, 6",
    "Klava: Klava (2019): 8",
    "Knut Myran: Frå Numedal til Tinn (2016): 3",
    "Laár András: Tündértantra (2009): 1",
    "Laszlo Borteri & Niko Radic: Authentic Hungary, Vol. 2 (2004): 18",
    "Leena Joutsenlahti: Makale (1999): 6",
    "Lieto: Paljasjaloin / Barfota (2004): 11",
    "Lockrop och vallåtar (1995): 32",
    "Makám: Skanzen (1999): 8",
    "Marie Selander, Styrbjörn Bergelt, Susanne Broms: å än är det glädje å än är det gråt (1976): 7, 8",
    "Martti Pokela: Improsette by Martti Pokela (2005): 5",
    "Merema: Eryamon' koytneva (2022): 1, 3",
    "Miklós Sugár, Zsusanna Mindszenty: Pulsations (2014): 16, 17",
    "Nathan Riki Thomson: Under Ubi's Tree (2008): 8",
    "Niekku: Niekku (1987): 12",
    "Niekku: 2 (1989): B4",
    "Nikolai Blad: Nikolai Blad (1995): 12",
    "Nordisk Sang (1991) (Steinar Ofsdal, Eivind Groven): 1, 15, 19",
    "Nord-Sud: Fragments De Routes (2000): 1, 2, 3, 4, 5, 6, 8, 10 , 11, 12, 13, 14, 15",
    "Ojajärvi Blom Ojajärvi: Ojajärvi Blom Ojajärvi (2020): 1, 2, 3, 4, 5, 6, 7, 8",
    "Olav Øyaland; Marit Vågen Lilleland; Per Spilling: På hjartestrenger (2012): 14, 16",
    "Отава Ё: Do You Love (2019): 6",
    "Paabel: Epöpoa (2009): 1, 2",
    "Pentti Ojajärvi: Pelimannin mopo keulii (2025): 3",
    "Per-Ulf Allmo & Styrbjörn Bergelt: Svarta jordens sång (1995): 7, 12",
    "Piirpauke: 2 (1976): 5, 6",
    "Prillarhorn och knaverharpa (1996): 4",
    "Primo: Karhujuhla (1986): 5",
    "Päre: Hausjärvi Beat (2016): 8",
    "Ro:Toro: Khanty Madness/Handi Hullus (2008): 6",
    "Ruumen: Silo (2009): 1, 3, 6, 8, 10",
    "Sebestyén Márta: Magyar Népköltészet (2004): 3",
    "Sibelius-Akatemian Folk Big Band: Katrilli toisesta elämästä (2019): 7",
    "Silvestru Lungoci: Silvestru Lungoci Fluier (1975)",
    "Sinikka Kontio: Kalevala! (2002): 7",
    "Soili Perkiö & Hannele Huovi: Karvakorvan laulupurkki (2010): 12",
    "Soolojen yö = Solos in the night : live at the Kaustinen folk music festival (1993): 3",
    "Steinar Ofsdal, Hallgrim Berg & Hans Fredrik Jacobsen: Seljefløyta (1997): 1-40",
    "Styrbjörn Bergelt: Tagelharppa och videflöjt (1979): 3, 5, 14, 18",
    "Suden aika: Armas (2009): 8",
    "Suède - Norvège: Musique des vallées scandinaves (1993): 17, 27",
    "Suo: Ei päivien perijätä (2008): 5",
    "Tapani Varis Collective: Värisevä rauta (2014): 4, 8",
    "Tapani Varis: Munniharppuuna / Jew's Harp (1996): 12",
    "Teppo Repo: Paimensoittaja Teppo Repo (1979): 6, 11, 24",
    "Tiriltunga: Det æ tungvint fri (1992): 5, 16",
    "Trad.Attack: Ah! (2015): 11",
    "Trad.Attack: Kullakarva (2017): 7",
    "Trio Beoir: Trio Beoir (2018): 5",
    "Tulikulkku: Musiikia menneessä ja nyt (1993): 12",
    "Tuulentei: Pokela (2024)",
    "Tuultenpesä: Vindstilla (2022): 4, 8, 9",
    "Ulla Pirttijärvi & Ulda: Roijk (2016): 4",
    "Usi ja Mammi: Lauluni - Min sång (2023)",
    "Värttinä: Viena (2015): 6",
    "Waldkauz: Komm’mit (2015): 3, 4",
    "Waldkauz: Mythos (2017): 2, 7",
    "Wind on Wind: Sees (2013): 5"
  ];

  // Lajitellaan aakkosjärjestykseen suomalaisilla erikoisaakkosilla (Å, Ä, Ö oikeille paikoilleen)
  function renderAlbums() {
    albums.sort((a, b) => a.localeCompare(b, 'fi'));
    const container = document.getElementById('album-list');
    container.innerHTML = albums.join('<br />');
  }

  renderAlbums();

  // Apufunktio lomakkeelle
  function addAlbum() {
    const val = document.getElementById('new-album').value.trim();
    if(!val) return;
    albums.push(val);
    albums.sort((a, b) => a.localeCompare(b, 'fi'));
    renderAlbums();
    
    // Näytetään koodinpätkä, jonka voi halutessaan kopioida suoraan tänne lähdekoodiin
    document.getElementById('output-code').innerText = 
      `Lisätty listaan! Voit halutessasi kopioida tämän rivin koodin taulukkoon:\n"${val}",`;
  }
</script>
