#include <iostream>
#include <stack>
#include <string>
#include <sstream>
#include <math.h>

using namespace std;

bool checkOperator(const string &input);
void calculateRPN(const string &input, stack<double> &rpnStack);

int main()
{
    stack<double> rpnStack;
    string input;
    double number;

    cout << "==================================" << endl;
    cout << "Reverse Polish Notation Calculator" << endl;
    cout << "==================================\n" << endl;

    cout << "Please enter a postfix expression one variable at a time..." << endl;
    cout << "Enter 'C' to calculate\n" << endl;

        while (true)
        {
            cout << ">>" ;
            cin >> input;

            if(istringstream(input) >> number) //take numerical input if double add to stack
            {
                rpnStack.push(number);
            }

            else if(checkOperator(input)) //if not double check if operator
            {
                calculateRPN(input, rpnStack); //call calculation function
            }

            else if(input == "q" && "Q") //
            {
                cout << "RPN Calculator Aborting Operations..." << endl;
                return 0;
            }

            else if(input == "c" && "C") //if c or C is input calculate RPN on the stack
            {
                if(rpnStack.size() < 1)
                {
                    cout << "There is no postfix on the stack, enter a postfix..." << endl;
                }

                if(rpnStack.size() == 1)
                {
                    cout << "\nYour Reverse Polish Notation Calculation: " << rpnStack.top() << endl;
                        rpnStack.pop();

                    cout << "=======================================================" << endl;
                    cout << "Enter your next postfix expression or enter 'Q' to quit" << endl;
                    cout << "=====================================================\n" << endl;
                }

                if (rpnStack.size() > 1)
                {
                    cout << "Too many Operands to perform calculation" << endl;

                    while (!rpnStack.empty())
                    {
                        rpnStack.pop();
                    }
                    cout << "Enter a new postfix..." << endl;
                }
            }

            else
            {
                cout << "Invalid Input" << endl;
            }
        }
}

/*************************************************
* Checking for operator                          *
*************************************************/
bool checkOperator(const string &input)
{
    string operators[] = {"-", "+", "*", "/", "sqrt"};

    for(int i = 0; i < 5; i++)
    {
        if(input == operators[i])
        {
            return true;
        }
    }

    return false;
}

/*************************************************
* RPN Calculation Function                       *
*************************************************/
void calculateRPN(const string &input, stack<double> &rpnStack)
{
  double firstValue, secondValue, result;

    if (input == "-") //subtraction logic
    {
        if (!rpnStack.empty())
        {
            secondValue = rpnStack.top();
            rpnStack.pop();
                if (!rpnStack.empty())
                {
                    firstValue = rpnStack.top();
                    rpnStack.pop();

                    result = firstValue - secondValue;
                    rpnStack.push(result);
                }
                else if (rpnStack.empty())
                {
                    cout << "Stack Underflow! You need more operands for this operation" << endl;
                    while (!rpnStack.empty())
                    {
                        rpnStack.pop();
                    }
                    cout << "Enter a new postfix..." << endl;
                }
        }

    }

    else if (input == "+") //addition logic
    {
        if (!rpnStack.empty())
        {
            secondValue = rpnStack.top();
            rpnStack.pop();
                if (!rpnStack.empty())
                {
                    firstValue = rpnStack.top();
                    rpnStack.pop();

                    result = firstValue + secondValue;
                    rpnStack.push(result);
                }
                else if (rpnStack.empty())
                {
                    cout << "Stack Underflow! You need more operands for this operation" << endl;
                    while (!rpnStack.empty())
                    {
                        rpnStack.pop();
                    }
                    cout << "Enter a new postfix..." << endl;
                }
        }
    }

    else if (input == "*") //multiplication logic
    {
        if (!rpnStack.empty())
        {
            secondValue = rpnStack.top();
            rpnStack.pop();
                if (!rpnStack.empty())
                {
                    firstValue = rpnStack.top();
                    rpnStack.pop();

                    result = firstValue * secondValue;
                    rpnStack.push(result);
                }
                else if (rpnStack.empty())
                {
                    cout << "Stack Underflow! You need more operands for this operation" << endl;
                    while (!rpnStack.empty())
                    {
                        rpnStack.pop();
                    }
                    cout << "Enter a new postfix..." << endl;
                }
        }
    }

    else if (input == "/") //division logic
    {
        if (!rpnStack.empty())
        {
            secondValue = rpnStack.top();
            rpnStack.pop();
            if (secondValue == 0)
            {
                cout << "Error: You cannot divide by a value by 0" << endl;

                    while (!rpnStack.empty())
                    {
                        rpnStack.pop();
                    }
                    cout << "enter a new postfix..." << endl;
            }
            else if (!rpnStack.empty())
            {
                firstValue = rpnStack.top();
                rpnStack.pop();

                result = firstValue / secondValue;
                rpnStack.push(result);
            }
            else if (rpnStack.empty())
            {
                cout << "Stack Underflow! You need more operands for this operation" << endl;

                    while (!rpnStack.empty())
                    {
                        rpnStack.pop();
                    }

                cout << "Enter a new postfix..." << endl;
            }
        }
    }

    else if (input == "sqrt") //square root logic
    {
        firstValue = rpnStack.top();
        rpnStack.pop();

        result = sqrt(firstValue);
        rpnStack.push(result);
    }
}

