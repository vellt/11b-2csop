```c#
// jegykalkulátor program
while (true)
{
	Console.WriteLine("Add meg a százalékot: ");
	int szazalek = Convert.ToInt32(Console.ReadLine());
	int erdemjegy = 1;
	if (szazalek >= 86) erdemjegy = 5;
	else if (szazalek >= 71) erdemjegy = 4;
	else if (szazalek >= 56) erdemjegy = 3;
	else if (szazalek >= 40) erdemjegy = 2;
	else erdemjegy = 1;

	switch (erdemjegy)
	{
		case 5: Console.WriteLine("Jeles (5)"); break;
		case 4: Console.WriteLine("Jó (4)"); break;
		case 3: Console.WriteLine("Közepes (3)"); break;
		case 2: Console.WriteLine("Elégséges (2)"); break;
		default: Console.WriteLine("Elégtelen (1)"); break;
	}
}

// logikai operátorok:
// >, <, !=, ==, <=, >=
// logikai kapuk:
// NOT (negáció): ! (Shift + 4)
// OR (vagy): || (altgr + w)
// AND (és): && (altgr + c)

// vissztérési értékük: logikai típus: igaz/hamis
// bool--> true/false

/*
 * Írjunk egy kifejezést, amely azt ellenőrzi, hogy egy
 * adott szám páros ÉS pozitív is!
 */

Console.WriteLine("Add meg az x értékét");
int x = Convert.ToInt32(Console.ReadLine());

if ((x % 2 == 0) && (x >= 0))
{
	Console.WriteLine("Páros és Pozitív");
}
if (!(x % 2 == 0) && (x >=0))  
{
	Console.WriteLine("Páratlan és Pozitív");
}
if ((x % 2 == 0) && !(x >= 0))
{
	Console.WriteLine("Páros és Negatív");
}
if (!(x % 2 == 0) && !(x >= 0))
{
	Console.WriteLine("Páratlan és Negatív");
}
if (!((x % 2 == 0) && (x >= 0))) 
{
	Console.WriteLine("Páratlan és Negatív");
}


// SWITCH -------------------------------------------------------------
/*
 kérje be a 06 utáni részt és állapítsa meg, hogy a telefonszám valid-e,
ha igen, akkor mondja meg milyen szolgáltatóhoz tartozik
 */

Console.WriteLine("Kérelek add meg a telefonszamot: ");
string teloszam = Console.ReadLine();
// if else-el
if (teloszam.Length == 9)
{
	Console.WriteLine("Ez egy valid szam");
	if (teloszam[0] == '2') Console.WriteLine("Yettel");
	else if (teloszam[0] == '3') Console.WriteLine("Telekom");
	else if (teloszam[0] == '7') Console.WriteLine("Vodafon");
	else if (teloszam[0] == '1') Console.WriteLine("Spam");
	else Console.WriteLine("nem ismerem ezt a szolgáltatót");
}
else Console.WriteLine("Nem valid szam");
// switch-el
switch (teloszam.Length)
{
	case 9:
		Console.WriteLine("Ez egy valid teloszám");
		switch (teloszam[0])
		{
			case '2': Console.WriteLine("Yettel");break;
			case '3': Console.WriteLine("Telekom");break;
			case '7': Console.WriteLine("Vodafon");break;
			case '1': Console.WriteLine("spam");break;
			default: Console.WriteLine("Nem ismerem ezt a szolgáltatót");break;
		}
		break;
	default: Console.WriteLine("Nem valid szám");break;
}

// RANDOM ----------------------------------------------------
// objektumot Random osztályból, ezt példányosításnak hívják
// példányosítás a new kulcsszóval történik, hatására egy objektum képződik
/// ez az objektum tartalmazza az adott osztály teljes funkcionalitását
Random random = new Random();
int szam1 = random.Next(6); // 0tól 5ig generál
int szam2 = random.Next(31)+20; // [20,50] egy param
int szam3 = random.Next(20,51); // [20, 50] két param

// [0,99]
int rsz1 = random.Next(100);
// [0,100]
int rsz2 = random.Next(101);
// [0,49]
int rsz3 = random.Next(50);
// [-50,50]
int rsz4 = random.Next(101)-50;
//  [1,60]
int rsz5 = random.Next(60) + 1;
// [-100,100]
int rsz6 = random.Next(201)-100;
// [-15,-5]
int rsz7 = random.Next(11)-15;


// dolgozat feladatok átnézése -----------------------------------------------

// 1. feladat
Console.WriteLine("Add meg az életkorod");
int eletkor = Convert.ToInt32(Console.ReadLine());
// if-else hármas operandussal
Console.WriteLine((eletkor >= 18) ? "fogyaszthat alkoholt" : "nem");

// 2. feladat
Console.WriteLine("add meg az szám1 értékét");
int sz1 = Convert.ToInt32(Console.ReadLine());
Console.WriteLine("Add meg a szám2 értékét");
double sz2 = Convert.ToInt32(Console.ReadLine());
// if-else hármas operandussal
Console.WriteLine((sz1 < sz2) ? Math.Round(sz1 / sz2, 3) : Math.Round(sz2 / sz1, 3));


// 3. feladat
Console.WriteLine("Add meg az x értékét");
int sz3 = Convert.ToInt32(Console.ReadLine());
Console.WriteLine($"{Math.Round(Math.Pow(sz3, 1 / 30.0), 2)}");

// 4. feladat
Console.WriteLine("Add meg az a oldal hosszát");
double a = Convert.ToDouble(Console.ReadLine());
Console.WriteLine("Add meg a magasságot is");
double m = Convert.ToDouble(Console.ReadLine());
Console.WriteLine(Math.Round(a * m, 4));
Console.WriteLine(Math.Round(4 * a, 4));

// random feladatok------------------------------------------------------------------

/*
	Készítsünk egy számkitalálós programot! A gép véletlenszerűen találjon ki egy számot
	1 és 6 között. A felha.tól kérjünk be egy számot (tippet), majd mondjuk meg neki, ha 
	sikerült eltalálnia ammire a gép gondolt, ha nem írjuk ki a gép mire gondolt!
 */


Random random1 = new Random();
int gep = random.Next(6)+1;
Console.WriteLine("Tippelj (1-6)");
int tipp = Convert.ToInt32(Console.ReadLine());
Console.WriteLine((gep == tipp) ? "eltaláltad" : $"NEM. Amire én gondoltam: {gep}");


// készítsünk 2 random [-50,20] számot!
// számoljuk ki az összegét, kivonását, szorzatát, osztását

Random random3 = new Random();
double szamm1 = random3.Next(71)-50;
int szamm2 = random3.Next(71)-50;

Console.WriteLine(szamm2+szamm1);
Console.WriteLine(szamm2-szamm1);
Console.WriteLine(szamm2*szamm1);
Console.WriteLine(szamm2/szamm1);

/* Kő, papír, olló */
// 1--> kő, 2--> papír, 3-->olló
//[1,3] if else, felh be kell kérni, és összevetni a géppel
// AND

Random random10 = new Random();
int gepSzam = random10.Next(3) + 1;
Console.WriteLine("Adj egy számot (1-3)[kő, papír, olló]");
int felhSzam = Convert.ToInt32(Console.ReadLine());
// kiíratom a gép mire gondolt
Console.Write("Gép: ");
switch (gepSzam)
{
	case 1: Console.WriteLine("KŐ"); break;
	case 2: Console.WriteLine("Papír"); break;
	case 3: Console.WriteLine("Olló"); break;
}
// kiíratom, hogy a felh. mire gondolt
Console.Write("Felh: ");
switch (felhSzam)
{
	case 1: Console.WriteLine("KŐ"); break;
	case 2: Console.WriteLine("Papír"); break;
	case 3: Console.WriteLine("Olló"); break;
}

if (gepSzam == felhSzam) Console.WriteLine("Döntetlen");
else if (gepSzam==1 && felhSzam==3 
	|| gepSzam==2 && felhSzam==1 
	|| gepSzam==3 && felhSzam == 2
	) Console.WriteLine("gép győzött");
else Console.WriteLine("én nyertem");
```