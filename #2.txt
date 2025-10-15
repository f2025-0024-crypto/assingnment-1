#include<iostream>
#include <iomanip>
using namespace std;

int main()
{
    cout << "The main function is running successfully." << endl;
    
    double obtainedMarks[5], totalMarks[5];
    double totalObtained = 0, totalMaximum = 0;
    cout << "Enter marks for 5 subjects:" << endl;
    for(int i = 0; i < 5; i++) {
        cout << "Subject " << (i + 1) << " - Obtained marks: ";
        cin >> obtainedMarks[i];
        cout << "Subject " << (i + 1) << " - Total marks: ";
        cin >> totalMarks[i];
        if(cin.fail() || obtainedMarks[i] < 0 || totalMarks[i] <= 0 || obtainedMarks[i] > totalMarks[i]) {
            cout << "Invalid input! Please enter valid marks." << endl;
            return 1;
        }
        totalObtained += obtainedMarks[i];
        totalMaximum += totalMarks[i];
    }
    
    double percentage = (totalObtained / totalMaximum) * 100;
    cout << fixed << setprecision(2);
    cout << "\n====== RESULTS ======" << endl;
    cout << "Total Obtained Marks: " << totalObtained << "/" << totalMaximum << endl;
    cout << "Percentage: " << percentage << "%" << endl;
    
    if(percentage >= 90) {
        cout << "Grade: A" << endl;
    }
    else if(percentage >= 80) {
        cout << "Grade: B" << endl;
    }
    else if(percentage >= 70) {
        cout << "Grade: C" << endl;
    }
    else if(percentage >= 60) {
        cout << "Grade: D" << endl;
    }
    else if(percentage >= 50) {
        cout << "Grade: E" << endl;
    }
    else {
        cout << "Grade: Fail" << endl;
    }
    
    return 0;
}