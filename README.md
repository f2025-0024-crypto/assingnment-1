#include<iostream>
#include<iomanip>
using namespace std;

int check_datatype(){
   if (cin.fail()){
        cin.clear();
        cin.ignore(543,'\n');
        cout<<"\nInvalid datatype input !";
        return 1;
    }
    return 0;
}
void float_zerodevision(float n1, float n2){
  if(n2 != 0) {
        cout << "Quotient: " << n1 / n2 << endl;
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
    double n1, n2;
    cout << "Enter first floating point number: ";
    cin >> n1;
    if (check_datatype()==1){
        return 1;
    }
    cout << "Enter second floating point number: ";
    cin >> n2;
    if (check_datatype()==1){
        return 1;
    }
    cout << fixed << setprecision(3);
    cout << "\n--- Floating Point Results (3 decimal places) ---" << endl;
    cout << "Sum: " << n1 + n2 << endl;
    cout << "Difference: " << n1 - n2 << endl;
    cout << "Product: " << n1 * n2 << endl;
    float_zerodevision(n1,n2);
    
    int int1 = static_cast<int>(n1);
    int int2 = static_cast<int>(n2);
    cout << "\n--- Integer Results (after casting) ---" << endl;
    cout << "Sum: " << int1 + int2 << endl;
    cout << "Difference: " << int1 - int2 << endl;
    cout << "Product: " << int1 * int2 << endl;
    int_zerodevision(int1,int2);
    
    cout << "\n--- Casting Demonstration ---" << endl;
    cout << n1 << " cast to int: " << int1 << endl;
    cout << n2 << " cast to int: " << int2 << endl;
    
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

