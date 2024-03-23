# Reflection

## Commit 1
function handle_connection akan membuat sebuah bufReader dari object mutable TcpStream yang di pass dari parameter dan membuat sebuah Vector String yang berisikan data HTTP request menggunakan method `lines()` untuk mendapatkan data yang masuk pada bufReader dan `unwrap()` untuk mendapatkan konten dari setiap baris data sampai baris terakhir menggunakan method `take_while()`, lalu menggunakan method `collect()` untuk disimpan sebagai `Vec<String>` dan di print request tersebut ke console.