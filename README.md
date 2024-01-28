# Hehehehe

```json
// Isi variabel-token dan chatId sesuai dengan data Anda
var token = '';
var chatId = '';
var photoUrl = 'https://awsimages.detik.net.id/community/media/visual/2017/12/06/6414c1ae-fcd1-49a6-8316-4a71c29f93ff_43.jpg';

// Membangun URL untuk mengirim gambar ke Telegram
var apiUrl = `https://api.telegram.org/bot${token}/sendPhoto?chat_id=${chatId}&photo=${photoUrl}`;
var delay = 5000;
// Fungsi untuk mengirim gambar ke Telegram
function kirimGambar() {
  // Menggunakan fetch untuk mengirim permintaan HTTP POST ke API Telegram
  fetch(apiUrl, { method: 'POST' })
    .then(response => response.json())
    .then(data => {
      console.log('Pesan berhasil dikirim:', data);
      // Mengatur interval waktu antara pengiriman gambar (dalam milidetik)
       // Contoh: mengirim setiap 5 detik
      setTimeout(kirimGambar, delay);
    })
    .catch(error => {
      console.error('Terjadi kesalahan:', error);
      // Jika terjadi kesalahan, juga mengatur interval waktu antara pengiriman gambar
    // Contoh: mengirim setiap 5 detik
      setTimeout(kirimGambar, delay);
    });
}

// Memulai pengiriman gambar
kirimGambar();
```
