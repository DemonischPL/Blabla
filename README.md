#include<iostream>
#include<conio.h>
#include <iomanip>
#include<time.h>
#include<stdlib.h>

using namespace std;

void zaptab (int t[], int n)   //! Ok zapelnia mi tak jak chce ale nie mam odwolania przez wskaznik
{
	srand (time (NULL));
	for (int j=0; j<n; j++)
	{
		t[j]=-99+rand()%201;
	}
}

void poktab(int n, int* t)  
{ 
  int j;
  cout<<"\n Zawartosc tablicy";
  for (j=0; j<n; j++)
  cout<<"\n numer elementu "<< j <<" wartosc "<<*(t+j);
  cout<<endl;
}

float operacja(int n, int* t)                  // Zlicza srednia ale w zadaniu byla mowa "wartosc srednia elementow tablicy nie wieksza od k. Tak wiec potrzebuje wprowadzenia z klawiatury liczby do jakiej ma byc zliczana srednia z posrod tych 20 losowych (od -99 do 99). Tak to rozumiem ale zdj zadania Ci wyslalem na FB. Dodatkowo chodzi o to, zeby sie zliczala tu srednia a sam wynik miala by dokonywac inna operacja cos takiego void wynik (int ile) { cout<<\n Wartosc srednia: "<<ile<<endl; } cos takiego 
{ 
  int j;
  float s;
  cout<<setiosflags(ios::fixed|ios::showpoint)<<setprecision(2);
  for (s=0,j=0; j<n; j++)
  s+=*(t+j);
  s/=n;
  cout<<"\n Wartosc srednia elementu "<<setw(10)<<s<<endl;
  getch();
  return s;
}

void zaptab (int[], int);

int main()
{
float s;
const int N=20;
int tab[N];
zaptab(tab,N);
poktab(N,tab);
s=operacja(N,tab);
getch();
return 0;
}
