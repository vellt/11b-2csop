```c#
Random random = new Random();
int sz = random.Next(10); // [0,9]
// [2,8]
int sz1 = random.Next(7) + 2;
// [5,10]
int sz2 = random.Next(6) + 5;
// [-2,2]
int sz3 = random.Next(5) - 2;
// [-50,50]
int sz4 = random.Next(101)-50;
// [-20,-10]
int sz5 = random.Next(11)-20;
// [-100,-50]
int sz6 = random.Next(51) - 100;


// generáljunk 3 random számot generáljunk, és
// írjuk ki azok értékeit! [-200,100]
Random random1 = new Random();
int szam1 = random1.Next(301)-200;
int szam2 = random1.Next(301)-200;
int szam3 = random1.Next(301)-200;
Console.WriteLine($"{szam1} {szam2} {szam3}");

// mennyi a páros és páratlan
int parosSzamlalo = 0;
int paratlanSzamlalo = 0;
if (szam1 % 2 == 0) parosSzamlalo++;
else paratlanSzamlalo++;

if (szam2 % 2 == 0) parosSzamlalo++;
else paratlanSzamlalo++;

if (szam3 % 2 == 0) parosSzamlalo++;
else paratlanSzamlalo++;

Console.WriteLine($"páros: {parosSzamlalo}\npáratlan: {paratlanSzamlalo}");

//mennyi a pozitív és mennyi a negatív
int pozitivSzamlalo = 0;
int negativSzamlalo = 0;
if (szam1 >= 0) pozitivSzamlalo++;
else negativSzamlalo++;

if (szam2 >= 0) pozitivSzamlalo++;
else negativSzamlalo++;

if (szam3 >= 0) pozitivSzamlalo++;
else negativSzamlalo++;

Console.WriteLine($"negatív: {negativSzamlalo}\npozitív: {pozitivSzamlalo}");

// válozó értékeinek a megcserélése
Console.WriteLine($"{szam1} {szam2} {szam3}");
int temp = szam1;
szam1 = szam2;
szam2 = temp;
Console.WriteLine($"{szam1} {szam2} {szam3}");


// rendezd csökkenő sorrendbe a számokat!
if (szam1 < szam2)
{
	int temp1 = szam1;
	szam1 = szam2;
	szam2 = temp1;
}
if (szam1 < szam3)
{
	int temp1 = szam1;
	szam1 = szam3;
	szam3 = temp1;
}
if (szam2 < szam3)
{
	int temp1 = szam2;
	szam2 = szam3;
	szam3 = temp1;
}
Console.WriteLine($"{szam1} {szam2} {szam3}");

// while ciklusok
// elöl tesztelős (while): CSAK akkor fut le, ha a feltétel igaz, majd utánna addig ismétli magát AMÍG a feltétel igaz
// hátul tesztelős(do while): 1x lefut, majd utánna addig ismétli magát AMÍG a feltétel igaz

int szam = 6;
while (szam!=6)
{
	Console.WriteLine("A feltétel igaz, while");
}

do
{
	Console.WriteLine("A feltétel igaz, do while");
} while (szam!=6);

// íratsd ki a számokat 1-10ig, a while ciklus segítséglvel
int szamlalo = 0;
while (szamlalo!=10)
{
	szamlalo++;
	Console.Write($"{szamlalo}, ");
}
Console.WriteLine();

//  Írjuk ki a páros számokat 2-20 között, while segítségével
int szamalalo2 = 0;
while (szamalalo2!=20)
{
	szamalalo2++;
	if (szamalalo2 % 2 == 0)
	{
		Console.WriteLine(szamalalo2);
	}
}

// 10-->1ig csökkentsük folyamatosan
int szamlalo2 = 11;
while (szamlalo2!=1)
{
	szamlalo2--;
	Console.WriteLine(szamlalo2);
}


// írjunk egy programot ami kiszámolja egy szám
// faktoriálisát (!), pl 3!-->3*2*1-->6
int faktorialis = 5;
int szamlalo3 = faktorialis;
while (szamlalo3!=1)
{
	szamlalo3--;
	faktorialis = szamlalo3 * faktorialis;
 
}
Console.WriteLine($"A 3 faktoriális értéke {faktorialis}");

/*
 irjunk egy programot, ami bekér a 
felhasználótól egy 0tól nagyobb
(egész-->int) számot
és kiírja az annál kisebb, de 0tól nagyobb
páratlan (egész) számok összegét
 */
Console.WriteLine("Addj meg egy 0tól nagyobb számot");
int felh = Convert.ToInt32(Console.ReadLine());
int szamlalo10 = felh;
int osszeguk = 0;
while (szamlalo10!=1)
{
	szamlalo10--;
	if (!(szamlalo10 % 2 == 0)) 
	{
		Console.WriteLine($"páratlan: {szamlalo10}");
		osszeguk = osszeguk + szamlalo10;
	}
}
Console.WriteLine($"Összegük: {osszeguk}");

/*
 Írjunk egy programot, amely kiírj az első N prímszámot.
N-->amit bekérünk a felhasználótol
 */
Console.WriteLine("mennyi primszám legyen?");
int m = Convert.ToInt32(Console.ReadLine());
int n = 1; // akt szám, amit vizsgálunk, h prim-e
int primszamok = 0; // ahány db prim számot találtunk

Console.WriteLine("------------------");
while (m != primszamok)
{
	n++;
	int osztojaE = 0; // amivel elosztjuk a számot
	int osztoSzamlalo = 0; // amennyi db oaztója van az adott számnak
	while (osztojaE != n)
	{
		osztojaE++;
		if (n % osztojaE == 0) osztoSzamlalo++;
	}
	if (osztoSzamlalo == 2)
	{
		primszamok++;
		Console.WriteLine(n);
	}

}


// ha csak azt szeretnénk megnézni, hogy egy szám az prim-e
int szamAmiLehetHogyPrim = 7; // megnézzük, hogy  7 osztója-e
int ezASzamOsztojaE = 0; // amivel elosztjuk a számot
int amennyiOsztojaVan = 0; // amennyi db oaztója van az adott számnak
while (ezASzamOsztojaE != szamAmiLehetHogyPrim)
{
	ezASzamOsztojaE++;
	if (szamAmiLehetHogyPrim % ezASzamOsztojaE == 0) amennyiOsztojaVan++;
}
if (amennyiOsztojaVan == 2) Console.WriteLine($"A(z) {szamAmiLehetHogyPrim} szám az prím");
else Console.WriteLine($"A(z) {szamAmiLehetHogyPrim} szám nem prím");




Console.ReadKey();
```