# AP-homework1
#include <iostream>
#include <string>

using namespace std;

#define Decryt 'd'
#define Encrypt 'e'
string shift(const string &input, int shift)
{
    string result;
    for (char c : input)
    {
        if ( c == ' ')
        {
            result += ' ';
        }
        else
        {
            result += static_cast<char>(static_cast<int>(c) + shift);
        }
    }
    return result;
}
int main()
{
    char Order;
    int key;
    string message;
    cout << "please enter your mesaege:";
    getline(cin, message);
    while (true)
    {
        cout << "please enter your key:";
        cin >> key;
        if (key > 1 && key < 25)
        {
            break;
        }
        else
        {
            cout << "Invalid input. Please enter a valid integer for the key (1-25).\n";
        }
    }
    cout << "Please enter your order ('e' for encrypt, 'd' for decrypt): ";
    cin >> Order;
    if (Order == 'e')
    {

        string shiftedString = shift(message, key);
        cout << "" << shiftedString << endl;
    }
    else if (Order == 'd')
    {
        string shiftedString = shift(message, -key);
        cout << "" << shiftedString << endl;
    }
    else
    {
        cout << "Invalid order!";
    }
    return 0;
}
