## Gambaran Umum

Kode ini berfungsi untuk mengurutkan data array.

Fitur-fitur:

1️⃣ Mampu mengurutkan bilangan terkecil dan terbesar dari data array bertipe integer.  

2️⃣ Mampu mengurutkan nama-nama berdasarkan abjad secara ASC (Asceding) dari data array bertipe char atau string.

3️⃣ Mampu mengurutkan nama-nama berdasarkan abjad secara DESC (Descending) dari data array bertipe char atau string.

4️⃣ Mampu menampilkan jumlah data array.

## Bahasa Pemrograman

Kode proyek ini ditulis menggunakan bahasa pemrograman C++.

## Software Pendukung

Proyek ini dikembangkan menggunakan [Dev-C++ v5.11](https://sourceforge.net/projects/orwelldevcpp/). Pastikan Anda memiliki Dev-C++ terpasang sebelum menjalankan proyek.

## Cara Penggunaan

1. Buka proyek menggunakan Dev-C++.
2. Jalankan aplikasi dengan melakukan compile dan Run (shortcut F11).
4. Ikuti petunjuk.

## Contoh Penggunaan Program

```cpp
// Library yang digunakan
#include <iostream>
#include <algorithm>
#include <vector>
#include <string>

using namespace std;

int main() {
    vector<int> numbers;
    vector<string> names;

    cout << "Apa yang ingin anda lakukan?" << endl;
    cout << "1. Mengurutkan bilangan terkecil dan terbesar didalam Array" << endl;
    cout << "2. Mengurutkan nama-nama berdasarkan abjad didalam Array" << endl;

    int choice;
    cin >> choice;

    if (choice == 1) {
        int num;
        cout << "Masukkan bilangan integer (inputkan karakter non-angka untuk STOP):" << endl;

        while (cin >> num) {
            numbers.push_back(num);
        }

        // Mengurutkan array kecil to besar
        sort(numbers.begin(), numbers.end());

        cout << "Array setelah diurutkan dari terkecil :" << endl;
        for (vector<int>::iterator it = numbers.begin(); it != numbers.end(); ++it) {
            cout << *it << " ";
        }

        // Mengurutkan array besar to kecil
        cout << "\nArray setelah diurutkan dari terbesar :" << endl;
        for (vector<int>::reverse_iterator rit = numbers.rbegin(); rit != numbers.rend(); ++rit) {
            cout << *rit << " ";
        }

        // Menampilkan jumlah elemen array
        cout << "\nJumlah elemen array: " << numbers.size() << endl;
    } else if (choice == 2) {
        string name;
        cout << "Masukkan nama (inputkan '0' untuk STOP) :" << endl;

        while (cin >> name && name != "0") {
            names.push_back(name);
        }

        // Mengurutkan array nama berdasarkan abjad secara Ascending (ASC)
        sort(names.begin(), names.end());

        // Menampilkan array nama setelah diurutkan
        cout << "Array nama setelah diurutkan secara Ascending (ASC) :" << endl;
        for (vector<string>::iterator it = names.begin(); it != names.end(); ++it) {
            cout << *it << endl;
        }

        // Mengurutkan array nama berdasarkan abjad secara Descending (DESC)
        sort(names.rbegin(), names.rend());

        // Menampilkan array nama setelah diurutkan
        cout << "Array nama setelah diurutkan secara Descending (DESC) :" << endl;
        for (vector<string>::iterator it = names.begin(); it != names.end(); ++it) {
            cout << *it << endl;
        }

        // Menampilkan jumlah elemen array
        cout << "Jumlah elemen array : " << names.size() << endl;
    } else {
        cout << "Pilihan tidak valid." << endl;
    }

    return 0;
}
