# Project-UAS

    from datetime import datetime

mengimpor kelas datetime dari modul datetime, yang akan digunakan nanti untuk mencetak tanggal dan waktu saat ini.

    # Header
    toko = {
        "nama": "======== Candy Shop  ========",
        "alamat": "DC Cakung",
        "nomor_telepon": "0813 3946 3480"
    }

Ini mendefinisikan sebuah dictionary (toko) yang berisi informasi tentang toko permen, seperti nama, alamat, dan nomor teleponnya.

    # Menu List
    daftar_menu = {
        1: {"nama": "Skittles", "harga": 5000},
        2: {"nama": "Jelly Bean", "harga": 8000},
        3: {"nama": "SilverQueen", "harga": 12000},
        4: {"nama": "Lollipop", "harga": 6000},
        5: {"nama": "Kiss", "harga": 1000}
    }

Ini membuat sebuah dictionary (daftar_menu) yang berisi barang-barang yang tersedia di toko permen, masing-masing dengan identifikasi unik, nama, dan harga.

    # Print Store Details
    print(toko["nama"])
    print(toko["alamat"])
    print(toko["nomor_telepon"])
    print("=" * 29)

Mencetak detail toko permen secara terformat.

    # Showing Menu List
    print("Menu:")
    for i, menu in daftar_menu.items():
        print(f"{i}. {menu['nama']} ({menu['harga']} IDR)")

Mencetak item menu beserta nomor dan harganya.

    # Input Orders
    pesanan = {}
    total_harga = 0

    while True:
        pilihan = input("Select menu (1-5) or type 'done' to end the order: ")
        if pilihan.lower() == 'done':
            break
        elif not pilihan.isdigit() or int(pilihan) not in daftar_menu:
            print("Invalid Option.")
        else:
            indeks_menu = int(pilihan)
            menu_terpilih = daftar_menu[indeks_menu]
            jumlah = input(f"Quantity of {menu_terpilih['nama']} ordered: ")
            while not jumlah.isdigit() or int(jumlah) <= 0:
                print("Invalid number. Please enter a positive number.")
                jumlah = input(f"Quantity of {menu_terpilih['nama']} ordered: ")
            jumlah = int(jumlah)
            total_harga += menu_terpilih['harga'] * jumlah
            pesanan[menu_terpilih['nama']] = jumlah

Menerima pesanan dari pengguna sampai mereka mengetik 'done'. Pengguna memilih item dengan memasukkan nomor menu yang sesuai.

    # Input Payments From Customers
    uang_pelanggan = float(input("Cash: "))

Menerima input jumlah uang yang diberikan oleh pelanggan.

    # Showing Receipt
    print("Candy Shop")
    print(toko["nama"])
    print(toko["alamat"])
    print(toko["nomor_telepon"])
    print("=" * 29)
    print("Ordered Menu:")
    for item, jumlah in pesanan.items():
        print(f"{item}: {jumlah} x {daftar_menu[indeks_menu]['harga']} IDR = {jumlah * daftar_menu[indeks_menu]['harga']} IDR")
    print("Total: ", total_harga)
    print("Cash: ", uang_pelanggan)
    print("Change: ", uang_pelanggan - total_harga)
    print("=" * 29)
    print("Items that have been purchased cannot be returned")
    print("=" * 29)
    print(datetime.now().strftime("%d/%m/%Y %H:%M:%S"))

Menghitung dan menampilkan struk, termasuk barang yang dipesan, total harga, uang yang diberikan, dan kembalian.

    print(datetime.now().strftime("%d/%m/%Y %H:%M:%S"))

Mencetak tanggal dan waktu saat ini ketika transaksi selesai dilakukan.