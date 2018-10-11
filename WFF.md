# Assignment-1
WFF program
/*
Roz Teves
2665530
CIS-7
*/

#include <iostream>
#include <string>

using namespace std;

bool contain(string s, char c);

int main()
{
	char c = ' ';
	string s;
	bool w = contain(s, c);

	cout << "Valid connectors: ! ^ c ->" << endl;
	cout << "Capital Letters Only\n";
	cout << "True = Valid WFF\n";
	cout << "False = Invalid WFF\n";
	cout << "---------------------------\n\n";

	do
	{
		cout << "Enter a statement: ";
		getline(cin, s);
		//cout << contain(s, c) << " "; //shows value of T(1) or F(0)

		if (contain(s, 'v'))
		{
			c = 'v';
			cout << "True\n" << endl;
		}
		else if (contain(s, '!'))
		{
			c = '!';
			cout << "True\n" << endl;
		}
		else if (contain(s, '^'))
		{
			c = '^';
			cout << "True\n" << endl;
		}
		else if (contain(s, '->'))
		{
			c = '->';
			cout << "True\n" << endl;
		}
		else
		{
			cout << "False\n" << endl;
		}

	} while (s != "quit"); // quit program

	return 0;
}

bool contain(string s, char c)
{
	for (int i = 0; i < s.length(); i++)
	{
		if (s[i] == c)
		{
			return i;
		}
	}
	return false;
}

//Invalid WFF equal to '0' and "False"
//Valid WFF equal '1' and "True"
//First valid WFF will equal '0' but will be "True'
//Must enter statement with same connector again for value to equal '1' and be "True"
