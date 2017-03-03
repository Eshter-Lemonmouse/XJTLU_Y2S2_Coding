#include <iostream>
#include <vector>

using namespace std;

int get_number(vector<int> vessel)
{
	//using namespace std;
	char tag = '0';
	int element = 0;
	//bool flag = 1;
	cin.get(tag);

	rewind(stdin);
	if (tag >= '0'&&tag <= '9')
	{
		element = tag - '0';
		vessel.push_back(element);
		return 1;
	}
	else if (tag == 'q')
	{
		return 1;
	}
	else
	{
		cout << "invalid, try again." << endl;
		return 0;
	}
}

//bool same_vec(vector<int> a, vector<int> b)
//{

//}

int main(void)
{
	//using namespace std;
	vector<int> a;
	int flag = 0;
	cout << "please input number, press q to quit." << endl;
	while (!flag)
	{
		flag = get_number(a);
	}
	cout << a[0]<<endl;

	return 0;
}
