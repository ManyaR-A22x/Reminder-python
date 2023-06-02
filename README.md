# Reminder-python

Berikut adalah contoh script Python yang dapat digunakan untuk mengirim notifikasi setiap jam 10 pagi hingga 3 sore:

```python

import time

from plyer import notification

def send_notification():

    title = "Pengingat"

    message = "Waktunya istirahat sebentar!"

    notification.notify(title=title, message=message, timeout=10)

# Menentukan rentang waktu untuk mengirim notifikasi (10:00 - 15:00)

start_time = time.strptime("10:00:00", "%H:%M:%S")

end_time = time.strptime("15:00:00", "%H:%M:%S")

while True:

    current_time = time.localtime()

    if start_time <= current_time <= end_time:

        send_notification()

    # Menunggu 1 jam sebelum memeriksa lagi

    time.sleep(3600)  # 3600 detik = 1 jam

```

Pada contoh di atas, kami menggunakan pustaka `plyer` untuk mengirim notifikasi pada sistem operasi yang Anda gunakan. Pastikan untuk menginstal pustaka tersebut sebelum menjalankan script dengan menggunakan perintah `pip install plyer`.

Script ini akan berjalan secara terus menerus dan memeriksa waktu saat ini setiap jam. Jika waktu saat ini berada di antara rentang waktu yang ditentukan (10:00 pagi hingga 3:00 sore), maka akan dikirimkan notifikasi sebagai pengingat.

Harap diperhatikan bahwa beberapa sistem operasi mungkin memerlukan izin atau konfigurasi tambahan agar notifikasi dapat ditampilkan. Pastikan untuk memeriksa dokumentasi sistem operasi yang Anda gunakan.
