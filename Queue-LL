#include <iostream>
#include<conio.h>

// Node untuk merepresentasikan elemen dalam linked list
struct Node {
    int data;
    Node* next;
    Node(int val) : data(val), next(nullptr) {}
};


class Queue {
private:
    Node* front; // Pointer ke elemen depan antrian
    Node* rear;  // Pointer ke elemen belakang antrian

public:
    // Konstruktor untuk menginisialisasi antrian kosong
    Queue() : front(nullptr), rear(nullptr) {}

    // Fungsi untuk menambahkan elemen ke belakang antrian
    void enqueue(int val) {
        Node* newNode = new Node(val);
        if (isEmpty()) {
            front = rear = newNode;
        } else {
            rear->next = newNode;
            rear = newNode;
        }
        std::cout << "Elemen " << val << " ditambahkan ke antrian.\n";
    }

    // Fungsi untuk menghapus elemen dari depan antrian
    void dequeue() {
        if (isEmpty()) {
            std::cout << "Antrian kosong. Tidak dapat dequeue.\n";
            return;
        }

        Node* temp = front;
        front = front->next;
        delete temp;

        std::cout << "Elemen dihapus dari depan antrian.\n";

        // Jika setelah dequeue antrian menjadi kosong, perbarui rear
        if (front == nullptr) {
            rear = nullptr;
        }
    }

    // Function untuk mengecek apakah antrian kosong
    bool isEmpty() const {
        return front == nullptr;
    }

    // Function untuk menampilkan daftar antrian
    void display() const {
        if (isEmpty()) {
            std::cout << "Antrian kosong.\n";
            return;
        }

        Node* current = front;
        std::cout << "Isi antrian: ";
        while (current != nullptr) {
            std::cout << current->data << " -> ";
            current = current->next;
        }
        std::cout << "\n";
    }
};

int main() {
    Queue queue;

    char choice;
    char name[50];
    do {
        system("cls");
        std::cout << "Menu:\n";
        std::cout << "1. Tambah Queue\n";
        std::cout << "2. Hapus Queue\n";
        std::cout << "3. Tampilkan Queue\n";
        std::cout << "4. Keluar\n";

        std::cout << "Pilihan Anda: ";
        std::cin >> choice;

        switch (choice) {
            case '1': {
                int value;
                std::cout << "Masukkan nilai untuk enqueue: ";
                std::cin >> value;
                queue.enqueue(value);
                break;
            }
            case '2':
                queue.dequeue();
                break;
            case '3':
                queue.display();
                getch();
                break;
            case '4':
                std::cout << "Program selesai.\n";
                break;
            default:
                std::cout << "Pilihan tidak valid. Coba lagi.\n";
        }
    } while (choice != '4');

    return 0;
}
