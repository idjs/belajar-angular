Belajar AngularJS
====
----
![](img/angularjs.png)

## Dasar-dasar AngularJS
- [Apa itu AngularJS?](#apa-itu-angularjs)
- [Apa yang membuat AngularJS istimewa?](#apa-yang-membuat-angularjs-istimewa)
    - Two way data-binding
    - Ajari broswer sintak HTML baru
    - Dependency Injection (DI)
- [Key Concept AngularJS](#key-concept-angularjs)
    - `Model`
    - `Scope`
    - `Controller`
    - `View`
    - `Expression`
    - `Filter`
    - `Directive`

## Apa itu AngularJS?
  AngularJS merupakan framework javascript berbasis open-source yang dirilis oleh Google pada tahun 2009. 
  Merujuk pada situs resmi AngularJS (http://angularjs.org), akan kita dapatkan tagline berikut ini
  
> "HTML Enhanced for Web apps!"

Maksud dari tagline ini AngularJS merupakan HTML yang ditingkatkan fungsinya untuk membangun web app. 
  Melihat sejarah kemunculan HTML, awalnya HTML hanya digunakan untuk membuat dokumen statis (website) bukan untuk membuat web app. Nah, sekarang bayangkan kalau sejak awal HTML memang dikembangkan untuk membuat web app, seperti itulah konsep AngularJS.

  AngularJS bukan merupakan pustaka (library) javascript melainkan sebuah framework yang solid untuk membangun web app, seperti framework javascript pada umumnya AngularJS mengadopsi konsep MVC (Model, View, Controller), meskipun menggunakan implementasi yang berbeda dengan konsep asli MVC. Agar tujuan dari MVC ini tercapai, yaitu pemisahan tugas masing-masing komponen, AngularJS memiliki `Model`, `View`, dan `Controller` yang saling berinteraksi. Berikut beberapa filosofi dalam AngularJS:
  1. View haruslah deklaratif
  
  Elemen-elemen pada `View` harus memberikan arti yang jelas dan bersih dari kode logika.
  2. Controller bersifat imperatif (logika)
  
  Kode pemrosesan dan logika dihandle dan dituangkan di dalam `Controller` sebelum dikirim hasilnya ke `View`.
  
## Apa yang membuat AngularJS istimewa?
### Two way data-binding 

  Two way data-binding merupakan mekanisme sinkronisasi otomatis antara `Controller` dan `View`. Gampangnya, ketika ada perubahan pada `Model` yang berasal dari `View`, Angular secara otomatis membuat perubahan pada `Controller`. Begitu pula sebaliknya. Hal ini terjadi secara otomatis, jadi kita tidak perlu menuliskan kode secara manual untuk mencapai mekanisme ini.
      
### Ajari browsers sintak HTML baru

  HTML5 menawarkan sejumlah elemen baru semisal `<video>`, `<section>`, `<article>`, dsb. Nah dengan AngularJS, Kita bahkan dapat menambahkan lebih banyak lagi elemen-elemen baru yang akan dimengerti oleh browser, misal `<draggable>` membuat elemen bisa didrag, `<zippy>` membuat elemen semisal akordion, atau bahkan menggunakan bahasa indonesia seperti `<sembunyikan>` jika diklik akan menyembunyikan elemen (contoh saja, pada praktik gunakanlah bahasa inggris sebagai bahasa internasional). Fungsi ini disebut dengan istilah `Directive`. Kitalah yang bertanggungjawab membuat `Directive` tersebut bisa ditafsirkan oleh browser dengan menuliskan kode pada deklarasi `Directive` itu sendiri. Atau dengan kata lain, kita mengajari browser sintak HTML baru. Bahkan tidak terbatas pada elemen, kita bisa membuat `Directive` menggunakan attribute, HTML comment atau class.
### HTML Template

  Template yang digunakan AngularJS hanyalah HTML biasa dengan penambahan ekspresi (`expression`), sehingga kita tidak perlu menggunakan template engine khusus.
###Dependency Injection (DI)

  Dependency Injection memungkinkan developer menulis beberapa komponen kode yang terpisah satu sama lain. Ketika memerlukan salah satu komponen, developer dapat memanggil komponen yang dibutuhkan tersebut dan dapat menggunakan fungsi yang tersedia. Fitur ini memudahkan developer dalam membuat komponen yang dapat dipakai berulang kali (reusable component)

## Key Concept AngularJS  
  - **Model**
  
    Dalam pola MVC, `Model` merepresentasikan suatu set data yang digunakan oleh `Controller` dan `View`.`Model` dapat mendeteksi perubahan data dan memberikan notifikasi perubahan tersebut ke `Controller` dan `View`. Pada implementasi pasif, notifikasi perubahan dapat diabaikan. Untuk membuat `Model` di beberapa framework selain AngularJS diperlukan konstruktor khusus. Sedangkan `Model` pada AngularJS tidak memiliki konstruktor tersendiri dan tidak memerlukan inheritance dari Object Class tertentu. Model tidak memerlukan setter atau getter method khusus. Model bisa berupa primitive, object hash, atau full object. Dengan kata lain Model hanyalah javascript object biasa.

  - **Scope ($scope)**
  
    `Scope` merupakan perekat (glue) atau perantara antara `Controller` dengan `View`. Masing-masing controller memiliki scope atau lingkup sendiri.

  - **Controller**
  
    `Controller` merupakan kode dibalik `View`. Kode pemrosesan dan logika ditaruh pada controller yang akan menghasilkan `Model` untuk ditampilkan pada `View`.

  - **View**
  
    `View` adalah apa yang terlihat oleh pengguna. Dimulai dari sebuah template kemudian digabungkan dengan `Model` lalu browser melakukan proses rendering dan hasilnya ditampilkan ke pengguna. Template yang digunakan hanyalah sintak HTML (bukan HTML diselingi dengan markup khusus seperti pada template engine pada umumnya). 

  - **Expression**
  
    `Expression` merupakan kode snippet yang dapat kita tulis pada `View`. `Expression` berkaitan dengan mekanisme binding pada AngularJS, formatnya adalah sebagai berikut `{{ expression }}`
    Contoh :
    - `{{ 1+2 }}` , akan menampilkan angka 3 ke pengguna.
    - `{{ user.name }}` , akan menampilkan nilai properti 'name' dari model 'user'
    - `{{ 1000 | currency }}` , akan menampilkan angka 1000 dalam format mata uang (currency), keyword setelah tanda pipa ( | ) merupakan `filter`.

  - **Filter**
  
    `Filter` melakukan transformasi data pada `Model`. Bisa digunakan untuk menyesuaikan format sesuai keinginan kita atau melakukan pengurutan data, dsb. AngularJS juga memiliki beberapa `filter` bawaan, seperti contoh yang sudah kita lihat pada poin pembahasan Expression yaitu currency, lainnya seperti number, filter, limitTo, sortBy, lowercase, upercase, dsb. Kita juga dapat menulis custom filter jika dibutuhkan.

  - **Directive**
  
    `Directive` merupakan cara untuk membuat sintak HTML baru yang akan dimengerti oleh browser. Directive dapat berupa `elemen`, `attribute`, `HTML comment` atau `Class`. Angular telah menyediakan beberapa directive bawaan yang penting dalam pengembangan web app. Beberepa directive bawaan Angular diantaranya `ng-controller`, `ng-model`, `ng-repeat`, `ng-click` dll. Kita dapat pula membuat custom directive dengan perilaku (behavior) tertentu seperti yang telah dijelaskan pada pembahasan Apa yang membuat AngularJS istimewa


  Untuk mengetahui bagaimana komponen-komponen di atas saling berinteraksi, lihat contoh berikut:
  
          // file: index.html --> sebagai View
          
            <!DOCTYPE html>
            <html ng-app>
            <head>
              <title>Angular Hello</title>
              <script src="js/angular-min.js"></script>
              <script src="js/main.js"></script>
            </head>
            <body>
              <div ng-controller="MyCtrl">
                <input ng-model="nama" />
                <span>Hello {{ nama | lowercase }}</span>
              </div>
            </body>
            </html>
    
    **Keterangan:**
    1. Terdapat satu model yaitu 'nama'.
    2. Pada View kita memiliki beberapa deklarasi
    
      - `<html ng-app>`, menginstruksikan angular untuk melakukan inisialisasi app

      - `<div ng-controller="MyCtrl">`, menginstruksikan angular untuk menggunakan controller bernama `MyCtrl` dalam lingkup div yang terdapat directive ng-controller itu. Controller `MyCtrl` dapat ditemukan pada file main.js
        
      - `<input ng-model="nama" />`, binding ke model `nama`. Artinya input tersebut memiliki value sesuai nilai model `nama`
        
      - `{{ nama | lowercase }}` merupakan expression, tampilkan nilai dari model `nama`.
    
      - `lowercase` pada `expression` di atas merupakan `filter` untuk menampilkan nilai model `nama` dalam format lowercase.

    Lalu perhatikan contoh kode `controller` di bawah ini

              // file: main.js --> sebagai tempat Controller

              function MyCtrl = angular.controller($scope) {
                $scope.nama = "World";
              }         

**Keterangan:**

1. `MyCtrl` merupakan `controller`, dan memiliki `scope` tersendiri. Pada controller ini Model `nama` diberi nilai awal 'World', agar `Model` bisa diakses oleh `View` maka kita rekatkan dengan `Scope` seperti ini `$scope.nama = "World"`;
2. Scope digunakan untuk mengirimkan nilai 'nama' dari controller (lihat $scope.nama) ke View.
