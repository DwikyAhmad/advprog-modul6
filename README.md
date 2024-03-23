# Reflection

## Commit 1
function handle_connection akan membuat sebuah bufReader dari object mutable TcpStream yang di pass dari parameter dan membuat sebuah Vector String yang berisikan data HTTP request menggunakan method `lines()` untuk mendapatkan data yang masuk pada bufReader dan `unwrap()` untuk mendapatkan konten dari setiap baris data sampai baris terakhir menggunakan method `take_while()`, lalu menggunakan method `collect()` untuk disimpan sebagai `Vec<String>` dan di print request tersebut ke console.

## Commit 2
![Commit 2](img/commit2.png)
Pada function handle_connection yang baru, function tersebut akan memberikan sebuah fixed response dari setiap TcpStream yang masuk ke listener, response status akan diberikan selalu bernilai 200, content length dari file `hello.html`, dan file content `hello.html` yang akan diberikan dalam format {status_line}\r\nContent-Length:{length}\r\n\r\n{contents} kepada user.

