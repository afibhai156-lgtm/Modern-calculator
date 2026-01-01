# Modern-#include<iostream>
#include<cmath>
#include<iomanip>
using namespace std;

double memory = 0;
double lastResult = 0;  // Changed name to avoid conflict

int main()
{
    double a, b;
    int choice;
    
    cout << "Welcome to Mimi`s Calculator" << endl;

    do {
        cout << "Available operations" << endl;
        cout << "would you like " << endl;
        cout << "1. ➕ addition" << endl;
        cout << "2. ➖ subtraction" << endl;
        cout << "3. ✖️ multiplication" << endl;
        cout << "4. ➗ division" << endl;
        cout << "5. 💪 power (a^b)" << endl;
        cout << "6. square root (√a)" << endl;
        cout << "7. modolus (a%b)" << endl;
        cout << "8. percentage (%)" << endl;
        cout << "9. memory store" << endl;
        cout << "10. memory recall" << endl;
        cout << "11. scientific functions "<< endl;
        cout << "12. Exit" << endl;
        cout << "enter your choice between 1 to 12" << endl;
        cin >> choice;
        
        switch(choice) {
            case 1:
                cout << "enter first num" << endl;
                cin >> a;
                cout << "second num" << endl;
                cin >> b;
                lastResult = a + b;
                cout << a << "➕" << b << "= " << lastResult << endl;
                break;
                
            case 2: 
                cout << "enter first num" << endl;
                cin >> a;
                cout << "enter second num" << endl;
                cin >> b;
                lastResult = a - b;
                cout << a << "➖ " << b << "=" << lastResult << endl;
                break;
                
            case 3:
                cout << "enter first num" << endl;
                cin >> a;
                cout << "enter second num" << endl;
                cin >> b;
                lastResult = a * b;
                cout << a << "✖️" << b << "=" << lastResult << endl;
                break;
                
            case 4:
                cout << "enter first num" << endl;
                cin >> a;
                cout << "enter second num" << endl;
                cin >> b;
                if(b != 0) {
                    lastResult = a / b;
                    cout << a << "➗ " << b << "=" << lastResult << endl;
                } else {
                    cout << "Error! cannot divided by zero" << endl;
                }
                break;
                
            case 5:
                cout << "enter base" << endl; 
                cin >> a;
                cout << "enter exponent" << endl;
                cin >> b;
                lastResult = pow(a, b);
                cout << "result: " << lastResult << endl;
                break;
                
            case 6:  // FIXED - input before condition
                cout << "enter number: ";
                cin >> a;
                if(a >= 0) {
                    lastResult = sqrt(a);
                    cout << "√" << a << " = " << lastResult << endl;
                } else {
                    cout << "❌ error cannot calculate square of negative number" << endl;
                }
                break;
                
            case 7:
                cout << "enter first num" << endl;
                cin >> a;
                cout << "enter second num" << endl;
                cin >> b;
                if(b != 0) {
                    lastResult = fmod(a, b);
                    cout << a << " % " << b << " = " << lastResult << endl;
                } else {
                    cout << "❌ Error cannot calculate with zero" << endl;
                }
                break;
                
            case 8:  // FIXED - added break
                cout << "enter obtained value: ";
                cin >> a;
                cout << "enter total value: ";
                cin >> b;
                if(b != 0) {
                    lastResult = (a / b) * 100;
                    cout << "Percentage: " << lastResult << "%" << endl;
                } else {
                    cout << "Error! Total cannot be zero" << endl;
                }
                break;
                
            case 9:
                memory = lastResult;
                cout << "Memory stored: " << memory << endl;
                break;
                
            case 10:  // FIXED - added input
                cout << "Memory value: " << memory << endl;
                cout << "Would you like to use this value? (1=Yes, 0=No): ";
                int useMemory;
                cin >> useMemory;
                if(useMemory == 1) {
                    a = memory;
                    cout << "enter second num: ";
                    cin >> b;
                    cout << "Memory value " << memory << " used as first number" << endl;
                }
                break;
                
            case 11:
                cout << "Scientific Calculation 🧮" << endl;
                cout << "1. sin(x)  2. cos(x)  3. tan(x)" << endl;
                cout << "4. log(x)  5. log10(x)  6. absolute value" << endl;
                cout << "choose function (1-6): ";
                int sciChoice;
                cin >> sciChoice;
                cout << "enter value: ";
                cin >> a;
                
                switch(sciChoice) {
                    case 1:
                        lastResult = sin(a);
                        cout << "sin(" << a << ") = " << lastResult << endl;
                        break;
                    case 2:
                        lastResult = cos(a);
                        cout << "cos(" << a << ") = " << lastResult << endl;
                        break;
                    case 3:
                        lastResult = tan(a);
                        cout << "tan(" << a << ") = " << lastResult << endl;
                        break;
                    case 4:
                        if(a > 0) {
                            lastResult = log(a);
                            cout << "ln(" << a << ") = " << lastResult << endl;
                        } else {
                            cout << "❌ Error: logarithm of non-positive number" << endl;
                        }
                        break;
                    case 5:
                        if(a > 0) {
                            lastResult = log10(a);
                            cout << "log10(" << a << ") = " << lastResult << endl;
                        } else {
                            cout << "❌ Error: logarithm of non-positive number" << endl;
                        }
                        break;
                    case 6:
                        lastResult = abs(a);
                        cout << "|" << a << "| = " << lastResult << endl;
                        break;
                    default:
                        cout << "❌ Invalid choice!" << endl;
                }
                break;
                
            case 12:
                cout << "Thanks for using Mimi's calculator! 👋" << endl;
                break;
                
            default:
                cout << "Invalid choice! Please enter (1-12)" << endl;
        }
        
        if(choice != 12 && choice != 10 && choice != 9) {
            cout << "Last result: " << lastResult << endl;
        }
        
    } while(choice != 12);
    continue;
    return 0;
}