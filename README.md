```c#
// 10-től 1-ig while ciklussal listázzuk ki a 
// számokat


int szamlalo =11;
while (szamlalo!=1)
{
	Console.WriteLine(--szamlalo);
}


// 1-20 ig az összes páratlant

int szamlalo = 1;
while (szamlalo!=21)
{
	if(szamlalo % 2 != 0)
	{
		Console.WriteLine(szamlalo);
	}
	szamlalo++;
}


// 1-20 ig az összes párost ami egyben 5-el is osztható

int szamlalo = 0;
int darabSzamlalo = 0;
while (szamlalo!=20)
{
	szamlalo++;
	if(szamlalo % 2== 0 && szamlalo % 5 == 0)
	{
		Console.WriteLine(szamlalo);
		darabSzamlalo++;
	}
}
Console.WriteLine($"ennyi db páros és 5el osztható szám volt: {darabSzamlalo}");


// 1-30ig az összes páratlant írja ki,
// és azok négyzetgyökét 2 tizedesre 
// kerekítve


int szamlalo = 1;
while (szamlalo!=31)
{
	if (szamlalo % 2 != 0)
	{
		Console.WriteLine($"{szamlalo} négyzetgyöke: {Math.Sqrt(szamlalo):0.00}");
		Console.WriteLine($"{szamlalo} négyzetgyök: {Math.Pow(szamlalo, 1.0/2.0):0.00}");
	}
	szamlalo++;
}


// faktoriális kiszámoló alkalmazás

Console.WriteLine("add meg a fakotiálist");
int fakt = Convert.ToInt32(Console.ReadLine());

long faktorialisSzorzat = fakt;
while (fakt!=1)
{
	fakt--;
	faktorialisSzorzat = faktorialisSzorzat * fakt;
	
}

Console.WriteLine(faktorialisSzorzat);



// kérjen be a felhasználótól egy számot addig, amíg 0-t nem adunk meg,
// ezek a bekért számokat pedig folyamatosan adja össze


Console.WriteLine("Adj meg egy számot");
int felh =1_2_3_4000000;
int szumma = 0;
while (felh!=0)
{
	felh= Convert.ToInt32(Console.ReadLine());
	szumma = szumma + felh;
}
Console.WriteLine(szumma);


// 3 random számot  [-60, 120] 
Random random = new Random();
int szam1 = random.Next(181) - 60;
int szam2 = random.Next(181) - 60;
int szam3 = random.Next(181) - 60;

Console.WriteLine($"{szam1} {szam2} {szam3}");


// csökkenő

if (szam1<szam2)
{
	int temp = szam2;
	szam2 = szam1;
	szam1 = temp;
}
if (szam1 < szam3)
{
	int temp = szam3;
	szam3 = szam1;
	szam1 = temp;
}
if (szam2 < szam3)
{
	int temp = szam2;
	szam2 = szam3;
	szam3 = temp;
}
Console.WriteLine($"{szam1} {szam2} {szam3}");
Console.WriteLine($"legnagyobb: {szam1}");

Console.ReadKey();
```