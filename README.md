# Reflection

## Commit 1
function handle_connection akan membuat sebuah bufReader dari object mutable TcpStream yang di pass dari parameter dan membuat sebuah Vector String yang berisikan data HTTP request menggunakan method `lines()` untuk mendapatkan data yang masuk pada bufReader dan `unwrap()` untuk mendapatkan konten dari setiap baris data sampai baris terakhir menggunakan method `take_while()`, lalu menggunakan method `collect()` untuk disimpan sebagai `Vec<String>` dan di print request tersebut ke console.

## Commit 2
![Commit 2](img/commit2.png)
Pada function handle_connection yang baru, function tersebut akan memberikan sebuah fixed response dari setiap TcpStream yang masuk ke listener, response status akan diberikan selalu bernilai 200, content length dari file `hello.html`, dan file content `hello.html` yang akan diberikan dalam format {status_line}\r\nContent-Length:{length}\r\n\r\n{contents} kepada user.

## Commit 3
![Commit 3](img/commit3.png)
Pada commit 3 ini, function handle_connection dibuat untuk memberikan conditional pada page yang tidak diketahui dengan memberikan response file `404.html`, cara memisahkan antara response lainnya adalah menggunakan if else yang di mana variable status_line dan filename akan berbeda tergantung get request yang diminta, alasan kenapa refactoring yang dilakukan seperti itu penting adalah if else dengan cara biasa akan memiliki banyak repetisi pada kode membaca file dan menulis content dari file ke stream, maka untuk mengurangi repetisi akan dilakukan refactoring dengan melakukan ekstraksi pada variabel status line dan filename. Repetisi sangat penting untuk membuat kode mudah dibaca dan maintainability yang baik.