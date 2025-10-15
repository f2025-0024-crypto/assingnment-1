#include<iostream>
using namespace std;

int main() {
    int firstNumber, secondNumber, thirdNumber;
    
    cout << "Enter three integers:\n" << endl;
    cout << "First number: ";
    cin >> firstNumber;
    cout << "Second number: ";
    cin >> secondNumber;
    cout << "Third number: ";
    cin >> thirdNumber;
    
    if (cin.fail()){
       cin.clear();
       cin.ignore(10000,'\n');
       cout<<"\nInvalid data type Inputs!!!"<<endl;
       return 1;
    }   
       
    cout << "\n=== Analysis Results ===" << endl;
    if (firstNumber == secondNumber && secondNumber == thirdNumber) {
        cout << " ALL THREE NUMBERS ARE EQUAL" << endl;
        cout << "  " << firstNumber << " = " << secondNumber << " = " << thirdNumber << endl;
    }
    else {
        cout << " NOT ALL NUMBERS ARE EQUAL" << endl;
        int largest = firstNumber;
        if (secondNumber > largest) largest = secondNumber;
        if (thirdNumber > largest) largest = thirdNumber;
        int smallest = firstNumber;
        if (secondNumber < smallest) smallest = secondNumber;
        if (thirdNumber < smallest) smallest = thirdNumber;
        cout << "\nLargest number: " << largest << endl;
        cout << "Smallest number: " << smallest << endl;
        cout << "\nEquality Check:" << endl;
        
        if (firstNumber == secondNumber) {
            cout << " First (" << firstNumber << ") and Second (" << secondNumber << ") are equal" << endl;
        } else {
            cout << " First (" << firstNumber << ") and Second (" << secondNumber << ") are NOT equal" << endl;
        }
        
        if (secondNumber == thirdNumber) {
            cout << " Second (" << secondNumber << ") and Third (" << thirdNumber << ") are equal" << endl;
        } else {
            cout << " Second (" << secondNumber << ") and Third (" << thirdNumber << ") are NOT equal" << endl;
        }
        
        if (firstNumber == thirdNumber) {
            cout << " First (" << firstNumber << ") and Third (" << thirdNumber << ") are equal" << endl;
        } else {
            cout << " First (" << firstNumber << ") and Third (" << thirdNumber << ") are NOT equal" << endl;
        }
    }
    
    return 0;
}