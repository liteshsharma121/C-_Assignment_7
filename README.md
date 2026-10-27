
#include <iostream>
using namespace std;

// Compile-Time Polymorphism
class Calculator {
public:
    int add(int a, int b) {
        return a + b;
    }

    float add(float a, float b) {
        return a + b;
    }
};

// Run-Time Polymorphism
class Animal {
public:
    virtual void sound() {
        cout << "Animal makes a sound." << endl;
    }
};

class Dog : public Animal {
public:
    void sound() override {
        cout << "Dog barks." << endl;
    }
};

class Cat : public Animal {
public:
    void sound() override {
        cout << "Cat meows." << endl;
    }
};

int main() {
    Calculator c;

    cout << "COMPILE-TIME POLYMORPHISM" << endl;
    cout << "Sum of integers: " << c.add(10, 20) << endl;
    cout << "Sum of floats: " << c.add(5.5f, 2.5f) << endl;

    cout << "\nRUN-TIME POLYMORPHISM" << endl;

    Animal* a;

    Dog d;
    Cat ct;

    a = &d;
    a->sound();

    a = &ct;
    a->sound();

    return 0;
}

