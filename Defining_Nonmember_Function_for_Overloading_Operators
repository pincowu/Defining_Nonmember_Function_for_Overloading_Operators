//Zhicheng Wang
#include <iostream>
using namespace std;

// =============================
// Version 1: Member function overload
// =============================
class RationalMember {
private:
    int num;  // numerator
    int den;  // denominator

public:
    // Constructor (with implicit conversion)
    RationalMember(int n = 0, int d = 1) : num(n), den(d) {}

    // Member version of operator+
    RationalMember operator+(const RationalMember& r) const {
        return RationalMember(num * r.den + r.num * den, den * r.den);
    }

    // Output function
    friend ostream& operator<<(ostream& os, const RationalMember& r) {
        os << r.num << "/" << r.den;
        return os;
    }
};

// =============================
// Version 2: Nonmember function overload
// =============================
class RationalNonMember {
private:
    int num;
    int den;

public:
    RationalNonMember(int n = 0, int d = 1) : num(n), den(d) {}

    // Getter for nonmember access
    int getNum() const { return num; }
    int getDen() const { return den; }

    // Add logic (used by nonmember operator+)
    RationalNonMember add(const RationalNonMember& r) const {
        return RationalNonMember(num * r.den + r.num * den, den * r.den);
    }

    // Output
    friend ostream& operator<<(ostream& os, const RationalNonMember& r) {
        os << r.num << "/" << r.den;
        return os;
    }
};

// Nonmember version of operator+
RationalNonMember operator+(const RationalNonMember& r1, const RationalNonMember& r2) {
    return r1.add(r2);
}

// =============================
// Main function
// =============================
int main() {
    cout << "===== Member Function Overload =====" << endl;
    RationalMember m1(1, 3);
    RationalMember m2(2, 5);

    cout << "m1 + m2 = " << m1 + m2 << endl;   //  works
    cout << "m1 + 4  = " << m1 + RationalMember(4) << endl; //  works (right side converted)
    // cout << "4 + m1  = " << 4 + m1 << endl;   //  ERROR: left side is int, no operator+ for int

    cout << endl;
    cout << "===== Nonmember Function Overload =====" << endl;
    RationalNonMember n1(1, 3);
    RationalNonMember n2(2, 5);

    cout << "n1 + n2 = " << n1 + n2 << endl;   // works
    cout << "n1 + 4  = " << n1 + 4 << endl;    // works (right side converted)
    cout << "4 + n1  = " << 4 + n1 << endl;    // works (left side converted)

    return 0;
}

