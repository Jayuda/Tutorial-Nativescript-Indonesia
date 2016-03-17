# Tutorial-Nativescript-Indonesia
Tutorial Nativescript dengan bahasa Indonesia. 

## Selamat Datang di NativeScript
_Apakah Anda seorang pengembang aplikasi hybrid & sedang mencari cara untuk membuat aplikasi yang benar-benar native? Atau Apakah Anda seorang pengembang aplikasi native bertanya-tanya bagaimana untuk memperluas cakupan dari aplikasi yang Anda tulis sehingga bisa di build untuk platform lainnya? Atau mungkin Anda seorang pengembang web mencari cara untuk mentransfer keterampilan yang ada ke dunia pengembangan mobile?_

NativeScript memungkinkan Anda mengembangkan aplikasi yang benar-benar Native untuk iOS dan Android dari basis kode TypeScript, JavaScript, XML dan CSS. NativeScript mengambil kode cross-platform dan menerjemahkannya ke dalam bahasa yang target platform.

## Bagaimana cara kerjanya
Mengembangkan logika bisnis Anda dengan JavaScript atau TypeScript , desain dan gaya antarmuka pengguna Anda menggunakan XML dan CSS dan membiarkan NativeScript menerjemahkan kode aplikasi single-sumber Anda ke dalam aplikasi yang benar-benar native untuk iOS atau Android. 

Anda dapat mengembangkan untuk Android ( Versi 4.2 atau yang lebih baru)  & iOS ( Versi 7.1 atau yang lebih baru).

![](DraggedImage.png)

1. Setelah Anda tulis kode aplikasi menggunakan modul NativeScript dan runtimes NativeScript. Maka Modul mengekspos perangkat dan platform Android/iOS dengan cara yang konsisten dan membiarkan Anda mengaksesnya melalui perintah non-platform.   
	Modul membiarkan Anda mengakses beberapa kemampuan asli melalui platform-spesifik dengan kode JavaScript.
2. Sesuaikan aplikasi Anda dengan aset platform tertentu seperti ikon dan layar splash
3. Runtime NativeScript menerjemahkan kode tertentu non-platform untuk bahasa Native dari platform target Anda dan NativeScript Tools akan menggunakan SDK Native Platform beserta tools native untuk menjalankan aplikasi.
4. Jalankan cross-platform aplikasi asli Anda di emulator asli, pada perangkat nyata atau mendistribusikannya ke device.


## Install 
Sebelum Anda dapat memulai membuat app dengan NativeScript, Anda harus mengkonfiguarsi dan install native script. Pada article ini kita akan menggunakan NativeScript Command-Line Interface bukan Telerik AppBuilder yang berbayar. :)

> TIP: Jika Anda sudah familiar dengan Apache Cordova CLI, maka NativeScript CLI hampir sama. CLI ini menyediakan satu set dengan perintah dan pengalaman yang sama.




## Panduan Awal NativeScript
Selamat datang di Panduan Awal NativeScript. Dalam tutorial ini Anda akan menggunakan NativeScript, cross-platform JavaScript framework untuk membangun aplikasi mobile, untuk membangun sebuah iOS dan Android app dari awal. 

## Apa yang akan dibangun dari latihan ini ?
Pada latihan ini kita akan membangun program HRD untuk perusahaan. Yaitu traksaksi mobile untuk membantu management HRD. Adapun ketentuan yang dipakai yaitu :
1. Konek dengan RESTful Service
2. Ada security dengan Login dan Registrasi
3. Terdapat menu untuk ADD, EDIT dan DELETE Data Karyawan
4. Program build ke Android dan iOS

## Prerequisites
Pada latihan ini, diasumsikan Anda menguasai Javascript, CSS dan Command line Terminal. Yang spesifik pada fiture :
- Javascript : Anda harus tau basic dari Konsep Javascript, yaitu fungsi, statement if, dan looping
- CSS : Anda harus bisa menulis CSS yang simple seperti CSS Selectors dan bagaimana mengaplikasikan CSS pada penerapan name atau value
- Terminal Command : Anda harus menguasai command line prompt pada OS yang Anda pakai. Seperti bagaimana membuat Folder, bagaimana mengexecute program, dll. Pada tutorial ini saya menggunakan MacOS. 
### Install Nativescript
#### MAC OS
1. Install Homebrew untuk memudahkan Anda menginstall program  
	` ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" `
2. Install Node.JS terbaru  
	` brew install homebrew/versions/node012 `
3. Install dependensi untuk iOS development  
	Untuk bisa menjalankan di iOS anda harus intall XCODE terbaru, selain itu untuk memudakan install cocoapods
4. Install dependensi untuk Android Development  
	  


### Getting Up Dan Jalankan Program
1. Install Nativescript dan configure enviroment  
	  
	Untuk memverifikasi apakah instalasi sudah ok, bisa dengan ketik perintah $tns maka akan muncul tampilan seperti berikut :   
	![](Screen%20Shot%202016-03-07%20at%2019.55.13.png)
2. Jalankan Aplikasi  

3. Add target development platforms
4. Running your app
5. Development workflow


### Membuat UI
Sebelum Anda memulai coding untuk program Data Karyawan, sangat penting untk mengetahu struktur folder dari Nativescript. Hal ini akan sangat membantu anda dalam menaruh file pada tempat yang tepat. 


Sekarang mari kita lihat struktur yang Ada :   


└── sample-Groceries
├── `app`
│   └── ...
├── `node_modules`
│   └── `tns-core-modules`
├── `package.json`
└── `platforms`
├── `android`
└── `ios`


Mari kita lihat apa fungsi dari setiap module tersebut :
- `app` : Folder ini berisi coding yang Anda bangun. Jadi di dalam folder ini nanti Anda akan membuat tampilan Login, tampilan data karyawan dll.
- `node_modules`  : Pada folder ini berisi dependensi npm module. Atau bisa disebut Add on dari nativescript. Semua program native script dimulai dengan dependensi tns-core-modules yang berada di dalam folder ini.
- `nide_modules/tns-code-modules` : Folder ini adalah module utama dari Nativescript, yang berisi jvascript module yang akan dipakai untuk membangun aplikasi - seperti module kamera, http, file systems yang diakses melalui platform API misalkan `camera.takePicture()`. Kita nanti akan melihat tiap API tersebut di latihan. 
- ` package.json` : File ini berisi detail configurasi, seperti aplikasi ID, versi dari Nativescript yang dipakai, dan module apa yang digunakan. Kita akan melihat lebih jauh nanti di bab V.
- ` platforms ` : Folder ini berisi spesifik platform yang digunakan - iOS atau ANDROID.  Sebagai contoh, pada folder android anda akan menemukan `AndroidManifest.xml` dan file `.apk`.  Begitu juga pada folder ios akan ditemukan ` xcodeproject ` dan file `.ipa`.

Diatas merupakan folder utama. sekarang kita tambahkan folder app menjadi seperti berikut :   
  
└── sample-Groceries
├── `app`
│   ├── `App_Resources`
│   │   ├── `Android`
│   │   └── `iOS`
│   ├── `shared`
│   │   └── ...
│   ├── `views`
│   │   └── `login`
│   │       ├── `login.js`
│   │       └── `login.xml`
│   ├── `app.css`
│   ├── `app.js`
│   └── ...
└── ...

Tambahan folder tersebut berfungsi :
- `App_Resources` : Folder ini berisi spesifik platform seperti icon, splash screen dan file konfigurasi. 
- `shared` : Folder yang berfungsi untuk share antar view di app Anda. Jadi semua view bisa mengakses ke folder ini. Misalkan config.js yang berisi variabel konfigurasi (- API Keys) yang akan dipakai semua view.
- `app.css` : File yang berisi styling CSS
- `app.js` : File ini berisi setup untuk starting module aplikasi dan inisialisasi aplikasi.


Ok, mari kita masuk lebih dalam lagi untuk membuat tampilan di aplikasi - yaitu pada folder `app/views`. Aplikasi yang kita bangun terdiri dari Register, Login dan List data karyawan. Jadi tiga menu tersebut berada pada `app/views`.


## Application logic
Dalam bab ini, Kita akan belajar bagaimana menambahkan logika JavaScript untuk aplikasi NativeScript. Selain itu Anda akan melakukannya dengan menggunakan pola dasar yang ada di NativeScript - MVVM, atau "model view view model". 
Berikut penjelasan detailnya:
1. Model  
	Model mendefinisikan dan mewakili data. Memisahkan model dari berbagai fungsi, sehingga memungkinkan untuk digunakan kembali.
2. View  
	View mewakili UI, yang di NativeScript ditulis dalam XML. Pada view Data-terikat pada model, sehingga perubahan yang dilakukan pada model dalam JavaScript langsung memicu perubahan visual untuk komponen UI.
3. View Model  
	View - Model berisi logika aplikasi (sering termasuk model), dan mengekspos data ke view. NativeScript menyediakan modul yang disebut 'Observable', sebagai fasilitas untuk menciptakan objek View - Model yang dapat terikat ke View.

Manfaat terbesar dari memisahkan Model, View, dan View-Model, adalah bahwa Anda dapat menggunakan dua arah data yang mengikat. Yaitu, perubahan data dalam Model akan langsung berubah di View, dan sebaliknya. Manfaat besar lainnya adalah bari kode yang bisa digunakan kembali.  
  
Dalam aplikasi ini, sejauh Anda hanya melihat baris kode di  View ( login.xml ), dan dalam bab ini Anda akan membuat sebuah View-Model. Untuk melakukannya, pertama kita perlu memperkenalkan satu jenis file lainnya: *The code-behind*.

## The code-behind - TCB
Dalam NativeScript *The Code-Behind* adalah file JavaScript yang memiliki nama yang sama sebagai View. Misalnya, tampilan halaman login ini bernama login.xml , sehingga TCB yang bernama login.js. TCB adalah tempat Anda meletakkan semua kode yang berinteraksi dengan View itu sendiri.

## Komponen UI
### TextField
#### hint
Placeholder text yang tampil di screen box
#### keyboardType
Tipe dari keyboard untuk memudahkan input data. Misalkan email, number, dll. Terdapat 5 Tipe yaitu :
1. datetimes  
	Android:   
	`TYPE_CLASS_DATETIME | TYPE_DATETIME_VARIATION_NORMAL`   
	iOS:  
	`UIKeyboardTypeNumbersAndPunctuation`
2. phone  
	Android:   
	`TYPE_CLASS_PHONE`   
	iOS:   
	`UIKeyboardTypePhonePad`
3. number  
	Android:   
	`TYPE_CLASS_NUMBER |android.text.InputType.TYPE_NUMBER_VARIATION_NORMAL |TYPE_NUMBER_FLAG_SIGNED | TYPE_NUMBER_FLAG_DECIMAL`   
	iOS:  
	`UIKeyboardTypeNumbersAndPunctuation`
4. url  
	Android:   
	`TYPE_CLASS_TEXT | TYPE_TEXT_VARIATION_URI`  
	iOS:  
	`UIKeyboardTypeURL`
5. email  
	Android:   
	`TYPE_CLASS_TEXT |TYPE_TEXT_VARIATION_EMAIL_ADDRESS`  
	iOS:  
	`UIKeyboardTypeEmailAddress`

#### autocorrect 
yaitu boolean atribut untuk auto koreksi dari apa yang di input user.


#### autocapitalizationType
Agar inputan user bisa di auto kapital. Terdapat 4 tipe yaitu :
1. none  
	Tidak ada auto kapital.
2. word  
	Kapital untuk huruf pertama di setiap kata.
3. sentences  
	Kapital untuk huruf pertama di setiap kalimat.
4. allCharacters  
	Semua karakter huruf kapital.


#### secure
Boolean atribut untuk text yang di Masked. biasa digunakan di password text.

### button
#### text 
Tampilan text yang muncul di button.

## Layouts UI
Nativescript menyediakan berbagai tipe tampilan container, sehingga komponen akan lebih presisi.
### Absolute Layout 
Akan memudahkan Anda untuk menyebutkan secara explisit x dan y koordinat. Tipe ini bermanfaat jika Anda ingin menyebutkan secara pasti lokasi mana dari element yang tambahkan - misalkan di pojok kanan atas, dll.

### Dock Layout
Tipe ini untuk menempatkan UI Element pada tepi terluat dari aplikasi Misalkan docked pada bottom, dll

### Grid Layout
Tipe ini seperti table di HTML, yang membagi layar menjadi rows dan columns.

### Stack Layouts
Memungkinkan anda membuat susunan / seperti rak dari child UI komponen. Bisa vertikal atau horisontal.

### Wrap Layout
Memungkinkan anda untuk mengisi penuh bari atau kolom.

## Membuat Login & Registrasi
Untuk membulai maka buka `app.js` dan tambahkan baris code berikut :

`  
var applicationModule = require("application");  
application.start({ moduleName: "views/login/login" });  
`

Pada baris pertama Anda mengimport NativeScript Aplication Module[^1]. Lalu Anda memanggil `start()` yang tampil di layar screen yaitu login.

### Tambahkan Komponen UI
Sekarang kita buka `login.xml` lalu ubah baris code menjadi :

`<page>`
` <StackLayout orientation="vertical">`
`     <TextField hint="Email Address" keyboardType="email" autocorrect="false" autocapitalizationType="none" />`
`     <TextField hint="Password" secure="true" />`
``
`     <Button text="Sign in" />`
`     <Button text="Sign up for Groceries" />`
` </StackLayout>`
`<page>`

Pada tampilan ini kita gunakan *stacklayout*[^2] Silahkan test program dengan perintah `tns run android --device` maka akan muncul tampilan :  
![](Screen%20Shot%202016-03-10%20at%2010.49.47.png)


[^1]:	[http://docs.nativescript.org/ApiReference/application/HOW-TO](http://docs.nativescript.org/ApiReference/application/HOW-TO)

[^2]:	Layout dengan tampilan susun dari sub komponen. Lihat Bab LAYOUT UI untuk detail dari tipe layout. 
