#include <iostream>
#include <vector>
#include <string>

using namespace std;

class Contact {
public:
    string name;
    string phone;

    Contact(const string& name, const string& phone) : name(name), phone(phone) {}
};

class ContactManager {
private:
    vector<Contact> contacts;

public:
    void addContact(const string& name, const string& phone) {
        contacts.emplace_back(name, phone);
        cout << "Kontak \"" << name << "\" telah ditambahkan." << endl;
    }

    void removeContact(int index) {
        if (index < 0 || index >= contacts.size()) {
            cout << "Indeks tidak valid!" << endl;
            return;
        }
        cout << "Kontak \"" << contacts[index].name << "\" telah dihapus." << endl;
        contacts.erase(contacts.begin() + index);
    }

    void displayContacts() const {
        if (contacts.empty()) {
            cout << "Daftar kontak kosong." << endl;
            return;
        }
        cout << "Daftar Kontak:" << endl;
        for (size_t i = 0; i < contacts.size(); ++i) {
            cout << i + 1 << ". " << contacts[i].name << " - " << contacts[i].phone << endl;
        }
    }
};

int main() {
    ContactManager contactManager;
    int choice;
    string name, phone;
    int index;

    do {
        cout << "\nMenu:" << endl;
        cout << "1. Tambah Kontak" << endl;
        cout << "2. Hapus Kontak" << endl;
        cout << "3. Tampilkan Kontak" << endl;
        cout << "4. Keluar" << endl;
        cout << "Pilih opsi (1-4): ";
        cin >> choice;
        cin.ignore(); // Mengabaikan newline setelah input angka

        switch (choice) {
            case 1:
                cout << "Masukkan nama kontak: ";
                getline(cin, name);
                cout << "Masukkan nomor telepon: ";
                getline(cin, phone);
                contactManager.addContact(name, phone);
                break;
            case 2:
                cout << "Masukkan indeks kontak yang ingin dihapus: ";
                cin >> index;
                contactManager.removeContact(index - 1); // Mengurangi 1 untuk indeks berbasis 0
                break;
            case 3:
                contactManager.displayContacts();
                break;
            case 4:
                cout << "Keluar dari program." << endl;
                break;
            default:
                cout << "Opsi tidak valid! Silakan coba lagi." << endl;
        }
    } while (choice != 4);

    return 0;
}
