# Gold-
int string arrays with random selection in c++
//Example of int string Arrays with random selection CGalicia 1-5-2015

#include <cstdlib>

#include <ctime>

#include <iostream>

#include <string> 

#include <Windows.h>

using namespace std; 

int main () 

{    system("cls");

string name[10] = { "Hani    " ,  "Marwan     " ,  "Fayez     " ,  "Ahmadinejad ",  "Mohand    " ,  "Khalid    " ,  "Ahmed      " , "Majed    " ,  "Nawaf    " ,  "Salem    "}; 
 
int gold[10] = {3,   4,   9,   0,   1,   2,   3,   4,   5,  7};

int health[10] = {35, 44, 90, 95, 10, 20, 30, 40, 50,  49};

int strenght[10] = { 4  ,  5  , 7  ,  8  ,  9  ,  6  ,  2  ,  1  , 0  , 3}; 

int counter = 0;

int mine;

//print arrays 

SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE), 6);
 cout <<"\n \n Name \t";
cout << " Gold \t";

cout << "\t Health \t";

cout << "\t Strength \n";



for (counter=0; counter<10; counter++)


{     cout<<name[counter]<<" \t";  

      cout <<gold[counter]<<"\t";

	  cout <<health[counter]<<"\t";

	  cout <<strenght[counter]<<""; 

cout<< "\n\n";
}

//random number generator

unsigned seed, randomNum;

int pick;

seed = ((unsigned int) time (0));

srand(seed);
    
     randomNum = rand () % 9;

	 pick =(int)randomNum; 
	 //Display Random Name, gold, health and strenght 

	 cout <<"The characther is " << name[pick]<<"\n";

	 cout<<"The ammount of gold possessed by " << name[pick]<<" is " <<gold[pick]<< " units \n";

	 cout<<"The ammount of health for " << name[pick] <<" is " <<health[pick]<< " units \n";

	 cout<<"The amount of strenght for " << name[pick] <<" is " << strenght[pick]<< " units \n";
	 
	 cout<<"choose a character (0-9):"; 
	 
	 cin>> mine;
	 cout<<"My Characther is " << name[mine] <<"\n";

	 cout <<"The characther is " << name[pick]<<"\n";

	 cout<<"The ammount of gold possessed by " << name[mine]<<" is " <<gold[pick]<< " units \n";

	 cout<<"The ammount of health for " << name[mine] <<" is " <<health[pick]<< " units \n";

	 cout<<"The amount of strenght for " << name[mine] <<" is " << strenght[pick]<< " units \n";

	 //Fight Until someone is deceased

	 cout<<"\n\n\n now for a fight to the death muahahaha....."<<endl;
  
	 while (health[mine] != 0 && health[pick] !=0)

  {
	    int p1, p2; //choose a randum #'s based on each players strength 

	  p1=1+rand()%strenght[mine];

	  p2=1+rand()%strenght[pick];

	  cout<< name[mine]<<"strikes with a force of"<<p1<<endl;

	  cout<< name[pick]<<"hits with a force of"<<p2<<endl;

	  if (p1>p2) //if my characther's # is larger, my characther loses 1 health
	  
	  {
		  cout <<name[pick] <<" loses health!"<< endl;
		  
		  health[pick]--;
	  }
	  else if (p2>p1) //If other characther's # is larger, my characther loses 1 health 

      {
		cout << name[mine] <<"Loses health!"<<endl;  
		health[mine]--;
		  
	  }
	  else 
	  {
	  
	  cout<<"Parry is successful - no health lost!"<< endl; //if tie no one dies 
	  } 
	  
	  cout<<"\n\n"<<name[mine]<<"health ="<<health[mine]<<"\t"<<name[pick]<<"health ="<<health[pick]
	   <<endl; //display the new health for both players
	     
	  system("pause"); 
      }
         cout<<"Game ends!"<<endl; //When someone has zero health - declare the winner (drops out of loop) 
         
		 if (health[mine]>health[pick])
			 
			 cout<<name[mine]<<" I'm the captain now...\n"<<endl;

		 if (health[pick]>health[mine])
         
		 cout<<name[pick]<<" Wins the battle!\n"<<endl;

		 system("pause");
     return 0; 

}






