# FILE-HANDELING#include <iostream>
#include <fstream>

using namespace std;

int main()
{
	//Open a file for input and output + append mode
	fstream file;
	file.open("scores.txt",ios::out | ios::app | ios::in);
		
	//check whether file opened successfully or not
	if(!file.good())
		return 10;
	
	
	string names[10];
	int scores[10];
	
	cout<<"Enter Your Name : ";
	cin>>names[0];
	
	cout<<"Enter your score : ";
	cin>>scores[0];
	
	//Write data in variables onto the file
	file<<names[0]<<endl;
	file<<scores[0]<<endl;
	
	
	//(move cursor)
	file.clear();
	file.seekg(0,ios::beg);
		
	string name;
	int score; 
	
	//Reading from file
	file>>name;
	file>>score;
	
	while (!file.eof())
	{		
		cout<<name<<endl;
		cout<<score<<endl;
		
		file>>name;
		file>>score;
	}

	
	//close file
	file.close();
	
	return 0;
}
