#include<iostream>
#include<iomanip>
using namespace std;

int check_datatype(){
   if (cin.fail()){
        cin.clear();
        cin.ignore(10000,'\n');
        cout<<"\nInvalid datatype input !";
        return 1;
    }
    return 0;
}
void float_zerodevision(float num1, float num2){
  if(num2 != 0) {
        cout << "Quotient: " << num1 / num2 << endl;
    } else {
        cout << "Quotient: Cannot divide by zero!" << endl;
    }
    
}
void int_zerodevision(int int1,int int2){   
   if(int2 != 0) {
        cout << "Quotient: " << int1 / int2 << endl;
   } else {
        cout << "Quotient: Cannot divide by zero!" << endl;
    }
}

int main() {
    double num1, num2;
    cout << "Enter first floating point number: ";
    cin >> num1;
    if (check_datatype()==1){
        return 1;
    }
    cout << "Enter second floating point number: ";
    cin >> num2;
    if (check_datatype()==1){
        return 1;
    }
    cout << fixed << setprecision(3);
    cout << "\n--- Floating Point Results (3 decimal places) ---" << endl;
    cout << "Sum: " << num1 + num2 << endl;
    cout << "Difference: " << num1 - num2 << endl;
    cout << "Product: " << num1 * num2 << endl;
    float_zerodevision(num1,num2);
    
    int int1 = static_cast<int>(num1);
    int int2 = static_cast<int>(num2);
    cout << "\n--- Integer Results (after casting) ---" << endl;
    cout << "Sum: " << int1 + int2 << endl;
    cout << "Difference: " << int1 - int2 << endl;
    cout << "Product: " << int1 * int2 << endl;
    int_zerodevision(int1,int2);
    
    cout << "\n--- Casting Demonstration ---" << endl;
    cout << num1 << " cast to int: " << int1 << endl;
    cout << num2 << " cast to int: " << int2 << endl;
    
    return 0;
}



    // Explanation in comments:
    /*
    DIFFERENCE IN OUTPUTS EXPLANATION:
    
    1. PRECISION LOSS: When casting from double to int, the decimal part is truncated (not rounded).
       Example: 5.789 becomes 5, 3.999 becomes 3
    
    2. INTEGER DIVISION: When dividing integers, the result is also an integer (decimal part truncated).
       Example: 5 / 2 = 2 (not 2.5)
    
    3. NO DECIMAL PLACES: Integer results don't have decimal places, so formatting with setprecision(3) 
       doesn't affect them.
    
    4. POTENTIAL DATA LOSS: Large floating point numbers might lose significant digits when cast to int.
    */

