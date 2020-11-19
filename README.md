<img align="center" src="https://res.cloudinary.com/aibnuhibban/image/upload/v1605659033/Github/Node-RajaOngkir/RajaOngkir_k1pvsq.png">

<p align="center">.
<a href="https://badgen.net/github/watchers/LeeNuksID/node-rajaongkir"><img src="https://badgen.net/github/watchers/LeeNuksID/node-rajaongkir" alt="Watchers"></a>
<a href="https://ci.appveyor.com/project/AIbnuHIbban/node-rajaongkir"><img src="https://ci.appveyor.com/api/projects/status/bq33xq476yj5ut7u/branch/master?svg=true" alt="Build Status"></a>
<a href="https://github.com/LeeNuksID/node-rajaongkir"><img src="https://img.shields.io/github/stars/LeeNuksID/node-rajaongkir.svg" alt="Total Downloads"></a>
<a href="https://github.com/LeeNuksID/node-rajaongkir/releases"><img src="https://badge.fury.io/js/node-rajaongkir.svg" alt="Latest Stable Version"></a>
<a href="https://github.com/LeeNuksID/node-rajaongkir/blob/master/LICENSE"><img src="https://img.shields.io/github/license/LeeNuksID/node-rajaongkir.svg" alt="License"></a>
</p>

# Node RajaOngkir

*Node RajaOngkir is **Node.js Library for RajaOngkir***

Node RajaOngkir adalah **Library Node.js untuk RajaOngkir**

> Saya hanya menambah dan memperbaharui repository yang sudah ada https://github.com/andhikamaheva/node-rajaongkir


# Daftar Isi

* [Dokumentasi](#documentation)
* [Instalasi](#installation)
* [Quick Start](#quick_start)
* [Penggunaan](#usage)
* [Cara Kontribusi](#contribute)
* [Lisensi](#license)

<a name="documentation"></a>
# Dokumentasi
Silahkan buka halaman [Wiki](https://github.com/LeeNuksID/node-rajaongkir/wiki) untuk dokumentasi penggunaan lengkap dari RajaOngkir Node.js


<a name="installation"></a>
# Instalasi

## Persyaratan
- Node.js versi 10 ke Atas
- RajaOngkir Service (telah mendaftar di RajaOngkir.com dengan akun tipe Starter, Basic maupun Pro dan telah memiliki **API Key**)

## Cara Install
```bash
npm install --save node-rajaongkir
```
<a name="quick_start"></a>
# Quick Start

### Menampilkan Seluruh Provinsi (Starter)
```javascript
var RajaOngkir = require('node-rajaongkir').Starter('apiKey');

RajaOngkir.getProvinces().then(function (result){
    // Aksi ketika data Provinsi berhasil ditampilkan
}).catch(function (error){
    // Aksi ketika error terjadi
});
```

### Menampilkan Spesifik Provinsi (Starter)
```javascript
var RajaOngkir = require('node-rajaongkir').Starter('apiKey');

var id = 1; // ID Provinsi
RajaOngkir.getProvince(id).then(function (result){
    // Aksi ketika data Provinsi berhasil ditampilkan
}).catch(function (error){
    // Aksi ketika error terjadi
});
```
### Menampilkan Seluruh Kota (Starter)
```javascript
var RajaOngkir = require('node-rajaongkir').Starter('apiKey');

RajaOngkir.getCities().then(function (result){
    // Aksi ketika data Kota berhasil ditampilkan
}).catch(function (error){
    // Aksi ketika error terjadi
});
```

### Menampilkan Spesifik Kota (Starter)
```javascript
var RajaOngkir = require('node-rajaongkir').Starter('apiKey');

var id = 1; // ID Kota
RajaOngkir.getCity(id).then(function (result){
    // Aksi ketika data Kota berhasil ditampilkan
}).catch(function (error){
    // Aksi ketika error terjadi
});
```
### Menghitung Biaya Kirim (Starter)
```javascript
var RajaOngkir = require('node-rajaongkir').Starter('apiKey');

var params = {
    origin: 501, // ID Kota atau Kabupaten Asal
    destination: 114, // ID Kota atau Kabupaten Tujuan
    weight: 1700, // Berat Barang dalam gram (gr)
    courirer: 'jne' // Kurir
};
RajaOngkir.getCosts(params).then(function (result){
    // Aksi ketika data Biaya berhasil ditampilkan
}).catch(function (error){
    // Aksi ketika error terjadi
});
```

### Menghitung Biaya Kirim JNE (Starter)
```javascript
var RajaOngkir = require('node-rajaongkir').Starter('apiKey');

var params = {
    origin: 501, // ID Kota atau Kabupaten Asal
    destination: 114, // ID Kota atau Kabupaten Tujuan
    weight: 1700 // Berat Barang dalam gram (gr)
};
RajaOngkir.getJNECost(params).then(function (result){
    // Aksi ketika data Biaya berhasil ditampilkan
}).catch(function (error){
    // Aksi ketika error terjadi
});
```

<a name="usage"></a>
# Penggunaan
Dalam RajaOngkir Node.js terdapat 3 jenis API yang dapat digunakan yaitu **Starter, Basic, dan Pro** sesuai dengan [dokumentasi](http://rajaongkir.com/dokumentasi) RajaOngkir.com.
Untuk menjalankan masing - masing API tersebut Anda dapat menggunakan perintah sebagai berikut : 

### Starter
```javascript
var RajaOngkir = require('node-rajaongkir').Starter('apiKey');
```
Tipe akun **Starter** memiliki beberapa fitur antara lain : 
* <code>getProvinces()</code> untuk menampilkan seluruh data Provinsi 
* <code>getProvince(idProvinsi)</code> untuk menampilkan data Provinsi berdasarkan ID / parameter ID
* <code>getCities()</code> untuk menampilkan seluruh data Kota
* <code>getCity(idKota)</code> untuk menampilkan data Kota berdasarkan ID / Parameter ID
* <code>getCosts(params)</code> untuk menampilkan biaya pengiriman berdasarkan Parameter
* <code>getJNECost(params)</code> untuk menampilkan biaya pengiriman Kurir JNE
* <code>getPOSCost(params)</code> untuk menampilkan biaya pengiriman Kurir POS
* <code>getTIKICost(params)</code> untuk menampilkan biaya pengiriman Kurir TIKI


### Basic
```javascript
var RajaOngkir = require('node-rajaongkir').Basic('apiKey');
```
Tipe akun **Basic** memiliki beberapa fitur antara lain :
* <code>getProvinces()</code> untuk menampilkan seluruh data Provinsi 
* <code>getProvince(idProvinsi)</code> untuk menampilkan data Provinsi berdasarkan ID / parameter ID
* <code>getCities()</code> untuk menampilkan seluruh data Kota
* <code>getCity(idKota)</code> untuk menampilkan data Kota berdasarkan ID / Parameter ID
* <code>getCosts(params)</code> untuk menampilkan biaya pengiriman berdasarkan Parameter
* <code>getJNECost(params)</code> untuk menampilkan biaya pengiriman Kurir JNE
* <code>getPOSCost(params)</code> untuk menampilkan biaya pengiriman Kurir POS
* <code>getTIKICost(params)</code> untuk menampilkan biaya pengiriman Kurir TIKI
* <code>getRPXCost(params)</code> untuk menampilkan biaya pengiriman Kurir RPX
* <code>getESLCost(params)</code> untuk menampilkan biaya pengiriman Kurir ESL
* <code>getPCPCost(params)</code> untuk menampilkan biaya pengiriman Kurir PCP
* <code>getInterOrigins()</code> untuk menampilkan data Kota (asal pengiriman) yang tersedia untuk pengiriman internasional
* <code>getInterOrigin(idKota)</code> untuk menampilkan data Kota (asal pengiriman) yang tersedia untuk pengiriman internasional berdasarkan ID Kota/Kabupaten
* <code>getInterDests()</code> untuk menampilkan data Negara yang mendukung pengiriman internasional
* <code>getInterDest(idNegara)</code> untuk menampilkan data Negara yang mendukung pengiriman internasional berdasarkan ID Negara
* <code>getTIKIInterConst(params)</code> untuk menampilkan biaya pengiriman internasional melalui kurir TIKI
* <code>getPOSInterCost(params)</code> untuk menampilkan biaya pengiriman internasional melalui kurir POS
* <code>getCurrency()</code> untuk menampilkan informasi nilai tukar rupiah terhadap US dollar
* <code>getJNEWaybill(params)</code> untuk melacak / mengetahui status pengiriman berdasarkan nomor resi JNE

### Pro
```javascript
var RajaOngkir = require('node-rajaongkir').Pro('apiKey');
```
Tipe akun **Pro** memiliki beberapa fitur antara lain :
* <code>getProvinces()</code> untuk menampilkan seluruh data Provinsi 
* <code>getProvince(idProvinsi)</code> untuk menampilkan data Provinsi berdasarkan ID / parameter ID
* <code>getCities()</code> untuk menampilkan seluruh data Kota
* <code>getCity(idKota)</code> untuk menampilkan data Kota berdasarkan ID / Parameter ID
* <code>getSubdistrict(idKota)</code> untuk menampilkan data Kecamatan berdasarkan ID / Parameter ID
* <code>getCosts(params)</code> untuk menampilkan biaya pengiriman dari beberapa layanan pengiriman (kurir)
* <code>getCost(params)</code> untuk menampilkan biaya pengiriman berdasarkan Parameter
* <code>getJNECost(params)</code> untuk menampilkan biaya pengiriman Kurir JNE
* <code>getPOSCost(params)</code> untuk menampilkan biaya pengiriman Kurir POS
* <code>getTIKICost(params)</code> untuk menampilkan biaya pengiriman Kurir TIKI
* <code>getRPXCost(params)</code> untuk menampilkan biaya pengiriman Kurir RPX
* <code>getESLCost(params)</code> untuk menampilkan biaya pengiriman Kurir ESL
* <code>getPCPCost(params)</code> untuk menampilkan biaya pengiriman Kurir PCP
* <code>getInterOrigins()</code> untuk menampilkan data Kota (asal pengiriman) yang tersedia untuk pengiriman internasional
* <code>getInterOrigin(idKota)</code> untuk menampilkan data Kota (asal pengiriman) yang tersedia untuk pengiriman internasional berdasarkan ID Kota/Kabupaten
* <code>getInterDests()</code> untuk menampilkan data Negara yang mendukung pengiriman internasional
* <code>getInterDest(idNegara)</code> untuk menampilkan data Negara yang mendukung pengiriman internasional berdasarkan ID Negara
* <code>getTIKIInterConst(params)</code> untuk menampilkan biaya pengiriman internasional melalui kurir TIKI
* <code>getPOSInterCost(params)</code> untuk menampilkan biaya pengiriman internasional melalui kurir POS
* <code>getCurrency()</code> untuk menampilkan informasi nilai tukar rupiah terhadap US dollar
* <code>getJNEWaybill(params)</code> untuk melacak / mengetahui status pengiriman berdasarkan nomor resi JNE

<a name="contribute"></a>

# Kontribusi
* Anda dapat Melaporkan issue (Kesalahan Program, Saran, dll) dengan membuat **New Issue** melalui halaman [Issue](https://github.com/LeeNuksID/node-rajaongkir/issues)
* Anda juga dapat berkontribusi untuk Package ini dengan cara [Pull Request](https://github.com/LeeNuksID/node-rajaongkir/pulls) 

<a name="license"></a>
# Lisensi

**The MIT License (MIT)**

Copyright © 2020 LeeNuksID

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
