<div id="top"></div>
<!--
*** Thanks for checking out the Best-README-Template. If you have a suggestion
*** that would make this better, please fork the repo and create a pull request
*** or simply open an issue with the tag "enhancement".
*** Don't forget to give the project a star!
*** Thanks again! Now go create something AMAZING! :D
-->



<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="images/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Dokumentasi Proses Pembuatan Dashboard IPM Provinsi di Indonesia</h3>

  <p align="center">
    Sebuah dokumentasi pembuatan dashboard disertai gambar dan link cara pembuatannya
    <br />
    <a href="https://github.com/othneildrew/Best-README-Template"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/othneildrew/Best-README-Template">View Demo</a>
    ·
    <a href="https://github.com/othneildrew/Best-README-Template/issues">Report Bug</a>
    ·
    <a href="https://github.com/othneildrew/Best-README-Template/issues">Request Feature</a>
  </p>
</div>





<!-- TABLE OF CONTENTS -->
# Link dashboard
Dashboard dapat diakses secara online pada [Dashboard IPM Provinsi di Indonesia](https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12)
atau dapat diakses dengan link : (https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12)
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## Proses Pembuatan Dashboard Indeks Pembangunan Manusia di Indonesia

[![Tampilan Penuh Dashboard][product-screenshot]]((https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12))

Tujuan dari pembuatan dashboard ini ada 4, yaitu : 

* Pembuatan diagram yang tepat sesuai dengan data yang akan divisualisasikan
* Penerapan visualisasi data yang interaktif agar pembaca dapat menganalisis data dengan lebih detail
* Penerapan Pre-Attentive Attribute dan Gestalt Principle pada visualisasi data
* Pembuatan dashboard  yang dapat membuat pembaca lebih mudah menganalisis dan membandingkan data
  
Dalam rangka mencapai tujuan tersebut, diperlukan beberapa langkah dalam pembuatannya. angkah - langkah tersebut diantaranya adalah :

<br />
<br />

### Pengumpulan data

Terdapat beberapa data yang akan divisualisasikan sehingga membutuhkan langkah pengumpulan data. Data - data tersebut adalah :

* [Data runtun waktu IPM tahun 2010 - 2021 tiap Provinsi di Indonesia](https://www.bps.go.id/indicator/26/413/1/-metode-baru-indeks-pembangunan-manusia.html) 
* [Pengeluaran per Kapita Disesuaikan tiap Provinsi di Indonesia tahun 2019-2021](https://www.bps.go.id/indicator/26/416/1/-metode-baru-pengeluaran-per-kapita-disesuaikan.html)
* [Harapan Lama Sekolah tiap Provinsi di Indonesia tahun 2019-2021](https://www.bps.go.id/indicator/26/417/1/-metode-baru-harapan-lama-sekolah.html)
* [Umur Harapan Hidup tahun tiap Provinsi di Indonesia tahun 2010 - 2021](https://www.bps.go.id/indicator/26/414/1/-metode-baru-umur-harapan-hidup-saat-lahir-uhh-.html)
* [Data geospasial provinsi di Indonesia](https://gadm.org/download_country_v3.html) 

Data data diatas diperoleh dari web [Badan Pusat Statistik](https://bps.go.id) kecuali data geospasial di Indonesia

<br />
<br />

<!-- GETTING STARTED -->
### Preprocessing Data

Dalam pembuatan line chart pada [Tableau](https://tableau.com) data haruslah berupa runtun waktu / time series, sedangkan data IPM pada web [Badan Pusat Statistik](https://bps.go.id) setiap kolom merupakan IPM dengan tahun yang berbeda. Sehingga diperlukan penyatuan data-data dalam beberapa kolom tersebut menjadi 1 kolom dan memberi tambahan kolom yang memuat tahun dari setiap baris data. 

Selain itu, pada pembuatan radar chart, karena data yang dimiliki yaitu data HLS 2019-2021, UHH 2019-2021, Pengeluaran per kapita (yang disesuakan) memiliki range data yang berbeda. UHH memiliki range puluhan-ratusan yang dapat mencapai 50 lebih, HLS memiliki skala belasan, sedangkan pengeluaran perkapita (yang disesuaikan) memiliki range ratusan ribu sehingga memerlukan preprocessing. Preprocessing yang dipilih adalah min-max preprocesing. Rumus dari [min-max preprocesing](https://androidkt.com/how-to-scale-data-to-range-using-minmax-normalization/) 



data lainnya dapat digunakan secara langsung tanpa menggunakan preprocessing.
<br />
<br />



## Pembuatan Diagram 

### Pembuatan Chloropleth Map
Saya melihat tutorial membuat chloropleth dari Youtube dengan laman [Tutorial Membuat Chloropleth Map](https://www.youtube.com/watch?v=aTJS2qkU748&t=449s). Dalam tutorial tersebut diajari bagaimana membuat chloropleth dari tahap download data geospasial sampai memasukkan data ke peta agar tercipta perbedaan warna pada peta yang menunjukkan tinggi atau rendahnya IPM suatu provinsi. 
Langkah langkah tersebut diantaranya 
* memasukkan longitude data pada kolom dan latitude data pada baris.
* Lalu memasukkan data IPM provinsi pada "color" agar tercipta chloropleth map. 
* Lalu meletakkan data nama provinsi pada "detail" agar ketika pembaca meng-highlight atau memilih suatu provinsi, muncul nama provinsi tersebut. 

Tampilan chloropleth map ditunjukkan pada gambar dibawah ini 

[![Tampilan Penuh Chloropleth Map][originalmap]]((https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12))

Sedangkan tampilan Chloropleth Map ketika dihiglight/ diselect

[![Tampilan highlight Chloropleth Map][highlightmap]]((https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12))

Selain itu juga terdapat fitur memilih tahun IPM yang akan ditampilkan peta menggunakan calculate field 

masukkan code pada calculate field untuk fitur pilih tahun
   ```tableau
   CASE [PilihTahunIPMpeta]
WHEN "Tahun2019" THEN [IPM_2019]
WHEN "Tahun2020" THEN [IPM_2020]
WHEN "Tahun2021" THEN [IPM_2021]
END
   ```
[![Pilih tahun peta][yearmap]]((https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12))

### Pembuatan Line Chart
Pembuatan diagram ini cukup gampang, langkah langkah yang dibutuhkan yaitu : 

* Memasukkan data pada "rows" dengan nilai IPM dengan menggunakan measure "sum"
* Memasukkan data pada "columns" dengan data tahun
* Memasukkan detail "color" pada nama provinsi agar tiap provinsi memiliki warna garis yang berbeda
* Memasukkan detail "Detail" pada nama provinsi agar tiap provinsi yang dipilih memunculkan namanya
* Memasukkan komponen "Analytics" berupa forecast agar mengetahui ramalan IPM 2  tahun kedepan dengan dasar data yang dimiliki
  
  Tampilan dari line chart ditunjukkan pada gambar dibawah

  [![Line chart][linechart]](https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12)

### Pembuatan Animasi Ranking IPM
Pada dasarnya pembuatan visualisasi data ini terinsipirasi dari pertemuan awal APG yang diputarkan [video Hans Rowling]((https://www.youtube.com/watch?v=hVimVzgtD6w&t=1091s)) di TedEx tentang data yang bergerak (flicker) memudahkan pembaca dalam menganalisis data. 

Pembuatan animasi ini membutuhkan langkah - langkah sebagai berikut : 
* Memasukkan data pada "rows" dengan olahan kalkulasi yang dinamakan "ranking"
* Memasukkan data pada "columns" data sum(IPM)
* Memasukkan data tahun pada fiter dan pages
* Memasukkan detail "Detail" pada nama provinsi agar tiap provinsi yang dipilih memunculkan namanya
* Memasukkan detail "Label" pada nama provinsi agar tiap provinsi yang memunculkan namanya 
  
  Tampilan dari animasi ranking  IPM ditunjukkan pada gambar dibawah
    [![Anmiasi ranking IPM][animationrank]](https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12)

    sayangnya, pada public tableau animasi ini ketika dicoba tidak berjalan. Akan tetapi masih tetap bisa digunakan dengan memilih tahun yang ingin dilihat ranking nya.

### Pembuatan Radar Chart
Pembuatan radar chart ini mengadopsi cara cara pembuatan radar chart yang diajarkan Megha Narang [link video]((https://www.youtube.com/watch?v=r2LI9Vq8F3g&t=950s)). Menurut saya ini pembuatan diagram paling sulit diantara diagram lain yang saya buat. Chart ini berprinsip bahwa semakin menjorok suatu sudut yang mewakili 1 variabel, maka variabel tersebut semakin besar nilainya.

* masukkan code pada calculate field X RADAR yang nanti akan dimasukkan pada komponen kolom
   ```tableau
   SIN(RADIANS([INDEX])*[DEGREE]*[RADAR SCORE])
   ```
* masukkan code pada calculate field Y RADAR yang nanti akan dimasukkan pada komponen baris
  
   ```tableau
   COS(RADIANS([INDEX])*[DEGREE]*[RADAR SCORE])
   ```
* Buat CODE index YANG AKAN DIGUNAKAN untuk membuat path radar chart
   ```tableau
   INDEX()-1
   ```

Tampilan default radar chart :

[![Tampilan Radar Chart][radarori]](https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12)

Tampilan radar chart ketika ada 1  provinsi di highlight:
[![Tampilan Radar Chart ketika di highlight][radarhighlight]](https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12)

### Pembuatan Cluster Scatter Plot
Diagram ini dapat menjelaskan pengelompokkan data berdasar 2 variabel yang diletakkan pada sumbu X dan Y.

Pembuatan diagram ini menggunakan calculated field yang dapat memilih variabel apa yang diwakili sumbu X dan variabel apa yang diwakili sumbu Y. Dalam pengklasteran menggunakan komponen analytics "cluster"

Tampilan default cluster scatter plot :
[![Tampilan Cluster Scatter Plot][cluster]](https://public.tableau.com/app/profile/mohamad.choirul.zamzami/viz/DashboardIPMProvinsidiIndonesia/Dashboard12)



<!-- CONTACT -->
## Contact

Mohamad Choirul Zamzami  - 221910908@stis.ac.id


<p align="right">(<a href="#top">back to top</a>)</p>





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/othneildrew/Best-README-Template.svg?style=for-the-badge
[contributors-url]: https://github.com/othneildrew/Best-README-Template/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/othneildrew/Best-README-Template.svg?style=for-the-badge
[forks-url]: https://github.com/othneildrew/Best-README-Template/network/members
[stars-shield]: https://img.shields.io/github/stars/othneildrew/Best-README-Template.svg?style=for-the-badge
[stars-url]: https://github.com/othneildrew/Best-README-Template/stargazers
[issues-shield]: https://img.shields.io/github/issues/othneildrew/Best-README-Template.svg?style=for-the-badge
[issues-url]: https://github.com/othneildrew/Best-README-Template/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=for-the-badge
[license-url]: https://github.com/othneildrew/Best-README-Template/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/othneildrew
[product-screenshot]: images/Untitled.png
[minmax]: images/minmax.png
[originalmap]: images/originalmap.png
[highlightmap]: images/highlightmap.png
[yearmap]: images/yearmap.png
[linechart]: images/linechart2.png
[animationrank]: images/animationrank.png
[radarori]: images/radarori.png
[radarhighlight]: images/radarhighlight.png
[cluster]: images/cluster.png