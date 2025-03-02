# Task2-
Login and registration system 
/* Task 2: Login and Registration System */
#include <iostream>
#include <fstream>
using namespace std;

void registerUser() {
    string username, password;
    cout << "Enter username: "; cin >> username;
    cout << "Enter password: "; cin >> password;
    ofstream file(username + ".txt");
    file << username << endl << password;
    file.close();
    cout << "User registered successfully!\n";
}

bool loginUser() {
    string username, password, u, p;
    cout << "Enter username: "; cin >> username;
    cout << "Enter password: "; cin >> password;
    ifstream file(username + ".txt");
    file >> u >> p;
    file.close();
    return (u == username && p == password);
}

int main() {
    int choice;
    cout << "1. Register\n2. Login\nChoose: ";
    cin >> choice;
    if (choice == 1) registerUser();
    else if (choice == 2) {
        if (loginUser()) cout << "Login Successful!\n";
        else cout << "Invalid Credentials!\n";
    }
    return 0;
}
