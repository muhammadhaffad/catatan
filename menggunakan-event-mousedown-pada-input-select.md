# Menggunakan event mousedown pada input select
Sebelumnya saya mempunyai masalah, yaitu saya mempunyai input select nah di input select tersebut saya ingin option yang didapatkan itu dinamis, yaitu option yang saya dapatkan itu hasil dari request service API, jadi tujuan saya adalah setiap saya menekan input select (bukan option-nya) itu script akan selalu melakukan request ke service API. sehingga awal kodingan saya seperti ini:
```
<script>
  let inputSelect = document.getElementById('select-something');
  inputSelect.addEventListener('click', function(event) {
    // melakukan fetch() beserta append child ke parent (input select)
  })
</script>
```
dari kode di atas, sepertinya make sense ya,.. namun masalahnya ada di sini, jadi kode di atas itu ketika kita memilih option maka script akan mengirim request ke service API, sehingga kita tidak bisa memilih option. setelah mencari-mencari saya bertanya ke chatGPT dan bertemu dengan event mousedown, jadi menurut chatGPT adalah sebagai berikut `event "click" hanya dipicu saat pengguna mengklik opsi, sedangkan event "mousedown" dipicu saat pengguna menekan opsi`, sehingga kode saya ubah seperti ini:
```
<script>
  let inputSelect = document.getElementById('select-something');
  inputSelect.addEventListener('mousedown', function(event) {
    // melakukan fetch() beserta append child ke parent (input select)
  })
</script>
```
