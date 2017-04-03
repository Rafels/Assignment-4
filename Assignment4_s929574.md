# Assignment 4

### Rafael Gallegos S929574

## Exercise 1

#### Write a class to contain the following information about towns: the name (a sequence ofcharacters); the population (an integer); and a Boolean value (i.e. true or false) whichindicates whether the town has an airport or not. Make the three data members private. Include a constructor that initialises the data members.

This program uses string in order to get the name of the town. The class town has three private variables and one constructor which sets the three 
variables. In main the program creates the object and sets the variables. It does not print out the variables as this is done in the next assignment.

### The Code

```c++
#include <iostream>
#include <string>
using namespace std;

class Towns
{
private:
	string name;
	int population;
	bool airport;
public:
	Towns(string n, int p, bool a);
};

Towns::Towns(string n, int p, bool a)
{
	name = n;
	population = p;
	airport = a;
}

int main()
{
	
	Towns myTown("Andeby", 1024, 1);

	return 0;
}
```
## Exercise 2
#### Now add three new member functions to the towns class that assign values to the three datamembers. Also add a member function to print out all the information about a town. Themember functions should all be publicly accessible. Write a main() function which declaresthree town objects and assigns the following values to them: Name: Oslo Bergen Lillestrøm Population: 1019000 275100 14000 Airport: TRUE TRUE FALSE After assigning values to the three objects, the program should print the details of both tothe screen.

This program is quite similar to the first exercise, the difference is that it includes several other function which able us to write to the private variables.
These functions are setpop(int p), setAir(bool a) and nameTown(string n). The last function is displayTowns(void), which prints out the variables values in a
certain format. In main thre object are initialized and displayed according to the assignment.

### The code:
```c++
#include <iostream>
#include <string>
using namespace std;

class Towns
{
private:
	string name;
	int population;
	bool airport;
public:
	Towns(string n, int p, bool a);
	void nameTown(string n);
	void setPop(int p);
	void setAir(bool a);
	void displayTown(void);
};

Towns::Towns(string n, int p, bool a)
{
	name = n;
	population = p;
	airport = a;
}
void Towns::nameTown(string n)
{
	name = n;
}
void Towns::setPop(int p)
{
	population = p;
}
void Towns::setAir(bool a)
{
	airport = a;
}
void Towns::displayTown(void)
{
	cout<<"Name: "<<name<<endl;
	cout<<"Population: "<<population<<endl;
	cout<<"Airport: ";
	if (airport == 1)
	{
		cout<<"True"<<endl;
	}else if(airport == 0)
	{
		cout<<"False"<<endl;
	}
}


int main()
{
	Towns town1("",0,0);
	Towns town2("",0,0);
	Towns town3("",0,0);
	town1.nameTown("Oslo");
	town2.nameTown("Bergen");
	town3.nameTown("Lillestr\233m");
	town1.setPop(1019000);
	town2.setPop(275100);
	town3.setPop(14000);
	town1.setAir(1);
	town2.setAir(1);
	town3.setAir(0);
	town1.displayTown();
	town2.displayTown();
	town3.displayTown();

	return 0;
}
```
### The Results
```
Name: Oslo
Population: 1019000
Airport: True
Name: Bergen
Population: 275100
Airport: True
Name: Lillestr¢m
Population: 14000
Airport: False
```
## Exercise 3
#### Write a class called Point. The class should have two private float data members x and y. Write two constructors: one default constructor that initialises the data members to 0, and one that takes two arguments and uses them to initialise the two data members. Also write the following member functions: void SetXY (float, float) assigns the two arguments to the two data members float GetX () returns the value of the x data member float GetY () returns the value of the y data member void Move (float, float) moves the point by the specified amount void Display () displays the values of the arguments Write a main function that allows the user to enter the x and y coordinates of two Point objects and then calculates and prints the equation of the straight line that joins the two points. A straight line is defined by the equation y = mx + c, so the values of m and c can be calculated as follows: m = (y2 – y1) / (x2 – x1) c = y1 - mx1

This program consist of the class point, which takes an x and a y-value in order to create the point. The class hass two private variables, two constructors and five member functions.
the functions are used to set the values, get the values, move them and display them. In Main the class is used to calculate the function for the line between two points.
The function is then displayed in the output.

### The code:

```c++
#include <iostream>

using namespace  std;

class Point
{
private:
	float x,y;
public:
	Point();
	Point(float a, float b);
	void SetXY(float a,float b);
	float GetX();
	float GetY();
	void Move(float a,float b);
	void Display();
};

Point::Point(void)
{
	x = 0;
	y = 0;
}
Point::Point(float a,float b)
{
	x = a;
	y = b;
}
void Point::SetXY(float a, float b)
{
	x = a;
	y = b;
}
float Point::GetX()
{
	return x;
}
float Point::GetY()
{
	return y;
}
void Point::Move(float a, float b)
{
	x = x+a;
	y = y+b;
}
void Point::Display()
{
	cout<<"X = "<<x<<" and Y = "<<y<<endl;
}
int main()
{

	float o,p;
	float m,c;
	cout<<"For the first point."<<endl;
	cout<<"Enter the x-value."<<endl;
	cin>>o;
	cout<<"Enter the y-value."<<endl;
	cin>>p;
	Point point1(o,p);
	cout<<"For the second point."<<endl;
	cout<<"Enter the x-value."<<endl;
	cin>>o;
	cout<<"Enter the y-value."<<endl;
	cin>>p;
	Point point2(o,p);
	
	m = (point2.GetY()-point1.GetY())/(point2.GetX()-point1.GetX());
	c = point1.GetY() - m*point1.GetX();
	cout<<"The function for the line between the point ";
	point1.Display();
	cout<<"and the point ";
	point2.Display();
	cout<<"is ";
	cout<<"y = "<<m<<"x + "<<c<<endl;
	return 0;
}
```
### The Results
```
For the first point.
Enter the x-value.
1
Enter the y-value.
1
For the second point.
Enter the x-value.
2
Enter the y-value.
2
The function for the line between the point X = 1 and Y = 1
and the point X = 2 and Y = 2
is y = 1x + 0
```
## Exercise 4
#### Now write a new class called Triangle. A triangle consists of 3 points. The Triangle classshould have one default constructor and another constructor that initialises the three points of the triangle. It should also have a member function that calculates the area of the triangle according to the formula where a, b and c are the lengths of the three sides, and s is half of the sum of the three sides. Write a main function that inputs three points from the user, and prints out the area of the triangle they form.

This program uses the triangle class, and the triangle class uses a slighly modified version og the Point class from the previous exercise.
The tringle class uses three points to create a triangle, the float Area() function is then used to calculate the area of the triangle. In Main the user is promted to input three point in order to create the
three point objects, the object are then used to initialize the triangle class, and finaly the area is calculated and displayed.

### The Code
```c++
#include <iostream>
#include <cmath>
#include "Point.h"
using namespace std;

class Triangle
{
private:
	float a,b,c;
	Point p1,p2,p3;
public:
	Triangle();
	Triangle(Point p1, Point p2, Point p3);
	void SetSides(Point p1,Point p2,Point p3);
	float Area();
};

Triangle::Triangle()
{
	cout<<"Object Constructed"<<endl;
}

Triangle::Triangle(Point p1,Point p2,Point p3)
{
	cout<<"Points are initialized"<<endl<<"A\t";
	p1.Display();
	cout<<"B\t";
	p2.Display();
	cout<<"C\t";
	p3.Display();
}
void Triangle::SetSides(Point p1,Point p2,Point p3)
{
	a = p1.lengthTwoPoints(p2);
	b = p2.lengthTwoPoints(p3);
	c = p3.lengthTwoPoints(p1);
}
float Triangle::Area()
{
	float area,s;
	s = (a+b+c)/2;
	area = sqrt(s*(s-a)*(s-b)*(s-c));
	return area;
}


int main()
{
	Point p1,p2,p3;
	cout<<"Enter the first point."<<endl;
	p1.SetPoint();
	cout<<"Enter the second point."<<endl;
	p2.SetPoint();
	cout<<"Enter the third point."<<endl;
	p3.SetPoint();

	Triangle myTri(p1,p2,p3);
	myTri.SetSides(p1,p2,p3);
	cout<<"The area of the triangle is "<<myTri.Area()<<endl;

	return 0;
}
```
### The Results:
```
Enter the first point.
Enter the x-value.
1
Enter the y-value.
1
Enter the second point.
Enter the x-value.
1
Enter the y-value.
2
Enter the third point.
Enter the x-value.
2
Enter the y-value.
1
Points are initialized
A       X = 1 and Y = 1
B       X = 1 and Y = 2
C       X = 2 and Y = 1
The area of the triangle is 0.5
```
## Exercise 5
#### A video shop needs to store information about the films it stocks. It has two types of film: video-cassettes and DVDs. Create a Film class that has two public data members title (a char*) and length (an int). Next create two classes called Cassette and DVD that are both derived from Film. The Cassette class should contain an extra public data member called condition (an enum type that can take the values perfect, good, average or poor). The DVD class should contain an extra public data member called region (an int). Both Cassette and DVD should have an extra public member function called Print that displays all data members. Write a short main function that creates objects to store information about two films and then displays the information to the screen: “Titanic” (a DVD, 180 minutes long, region 1) and “Kezkaza Welafen” (a video cassette, 100 minutes long, good condition). 

The class Film is used to create two public child functions, one called DVD and one called Cassette. The film class has two public variables title and length, which
are inherated by DVD and Cassette. The DVD class has one extra variable called int region and one member function which prints the name, length and region.
The Cassette class has an enumerator variable and the memberfunction which prints the results. In order to use the enumerator, an object must be created, this object is called cass.
In main the titles are put in a character array and then pointed to the objects title, the length are set, the region(for DVD) and the condition(for cassette) are set and then printed out using 
the print function for each class.

### The Code:
```c++
#include <iostream>
#include <string>
using namespace std;

class Film
{
public:
	char* title;
	int length;
};

class DVD: public Film
{
public:
	int region;
	void print();
};
class Cassette: public Film
{
public:
	enum condition
	{
		perfect,
		good,
		avarage,
		poor,
	};
	condition cass;
	void print();
};
void Cassette::print(void)
{
	cout<<"\""<<this->title<<"\"";
	cout<<"(a video cassette, "<<this->length<<"minutes long, ";
	switch(cass)
	{
		case perfect:
		cout<<"perfect";
		break;
		case good:
		cout<<"good";
		break;
		case avarage:
		cout<<"avarage";
		break;
		case poor:
		cout<<"poor";
		break;
	}
	cout<<" condition)."<<endl;

}
void DVD::print(void)
{
	cout<<"\""<<this->title<<"\"(a DVD,"<<this->length<<" minutes long, region "<<this->region<<")"<<endl;

}

int main()
{
	char name2[100] = "Titanic";
	char name1[100] = "Kezkaza Welafen";
	Cassette film1;
	DVD film2;

	film1.title = name1;
	film1.length = 100;
	film1.cass = film1.good;
	
	film2.title = name2;
	film2.length = 180;
	film2.region = 1;


	film1.print();
	film2.print();


	return 0;
}
```
### The Results:
```
"Kezkaza Welafen"(a video cassette, 100minutes long, good condition).
"Titanic"(a DVD,180 minutes long, region 1)
```
## Exercise 6
#### Create the ZooAnimal inheritance hierarchy shown below. Every animal in the hierarchy should have a char* data member called name. Every Bear, Koala or Panda should have an int data member called gestationPeriod. Every Fish or Shark should have a float data member called speed. Every animal in the hierarchy should include a function called feedingTime() that prints out details of when an animal should be fed. The actual feeding time will be different for each animal but every animal should have a feeding time. Every type of bear should include a function called makenoise() that prints out the noise made by the animal. The actual noise made will be different for each type of bear. Fish do not make any noise.

This program uses the ZooAnimal class which is used to spawn two subclasses which again spawn their own subclasses. The mother class has one protected 
variable char* name in order to keep the animals name safe. The subclasses have to have functions in order to access the protected variables.
The  class also has a function to set the feeding time and a function to get the name. The Bear class inherits the public functions from the mother class but also adds the gestation function and the makenoise function. The fish class has the speed function but is otherwise a 
direct inheritance of the mother class. The subclasses of the Bear Class, Panda and Koala have their own noise variables which hold the specifik sound each bear makes.

In main the Panda Class i tested and then displayed in order to check the functionality of the mother function and all the child classes.

### The Code
```c++
#include <iostream>
#include <string>
using namespace std;

class ZooAnimal
{
protected:
	char* name;
public:
	void feedingTime(int t);
	ZooAnimal(char* n){
		name = n;
	}
	char* getname(void)
	{
		return name;
	}
};
void ZooAnimal::feedingTime(int t)
{
	cout<<"The animal should be fed at: "<<t<<". O'clock."<<endl;
}
class Bear: public ZooAnimal
{
public:
	Bear(char* n) : ZooAnimal(n)
	{
		name = n;
	}
	int gestationPeriod;
	void makenoise(string n);
};
void Bear::makenoise(string n)
{
	cout<<"The bear makes the following noise: \""<<n<<"\""<<endl;
}
class Koala: public Bear
{
public:
	string noise{"GGHzeeeeaa!!!"};
};
class Panda: public Bear
{
public:
	Panda(char* n) : Bear(n)
	{
		name = n;
	}

	string noise{"Grfuuue!!!"};
};
class Fish: public ZooAnimal
{
public:
	float speed;
};
class Shark: public Fish
{
public:
};
int main()
{
	char name[] = "Pete";
	Panda panda1(name);
	panda1.gestationPeriod = 9;
	cout<<"This bear is called "<<panda1.getname()<<"."<<endl;
	panda1.makenoise(panda1.noise);
	cout<<"This bears gestation period is "<<panda1.gestationPeriod<<" months."<<endl;
	panda1.feedingTime(5);
	return 0;
}
```
### The Results
```
This bear is called Pete.
The bear makes the following noise: "Grfuuue!!!"
This bears gestation period is 9 months.
The animal should be fed at: 5. O'clock.
```
## Exercise 7
#### Write a C++ program to create two files named abc.txt which contains the text I love C++ Programming and def.txt which contains the text I love Java Programming. Now, copy the contents of these two files to a new file named xyz.txt. Finally, display the appropriate message on successful completion of the task, for exmaple: “the contents of file abc.txt and def.txt are successfully copied to xyz.txt”.

This program is quite simple and uses the fstream and ofstream functions in order to read and write to the text files. In order to complete the assignment, the 
files mus first be opened in order to write to them, closed and then opened again in order to read from them. Using a while-loop the text files are read from and write to the final text file.
A message is then displayed when the program finishes, it does not check the actual file though.

### The Code
```c++
#include <iostream>
#include <fstream>

using namespace std;

int main()
{
	char ch;
	ofstream file1;
	ifstream file2;
	ofstream file3;
	file3.open("xyz.txt");

	file1.open("abc.txt");
	file1 << "I love C++ Programming"<<endl;
	file1.close();
	file1.open("def.txt");
	file1 << "I love Java Programming"<<endl;
	file1.close();

	file2.open("abc.txt");
	while(!file2.eof())
	{
		file2.get(ch);
		file3<<ch;
	}
	file2.close();
	file2.open("def.txt");
	while(!file2.eof())
	{
		file2.get(ch);
		file3<<ch;
	}
	file2.close();
	file3.close();
	cout<<"The contents of file abc.txt and def.txt are successfully copied to xyz.txt"<<endl;
	return 0;
}
```
## The Results
```
The contents of file abc.txt and def.txt are successfully copied to xyz.txt
```
