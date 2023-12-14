```c#
// while ciklus ismétlés
Random random = new Random();
int gep = random.Next(100) + 1;
int felh = 0;
int db = 0;
while (gep!=felh)
{
	Console.WriteLine("Add meg a tipped! ");
	felh = Convert.ToInt32(Console.ReadLine());
	if (gep > felh)
	{
		Console.WriteLine("A gép nagyobb számra gondolt!");
	}
	else if(gep < felh)
	{
		Console.WriteLine("A gép kisebb számra gondolt!");
	}
	db++;
}
Console.WriteLine("Nyertél!");
Console.WriteLine($"ennyi lépés számban sikerült kitalálnod: {db}");

// 5 random szám [0,50]
// egymás mellé szóközökkel elválasztva
for (int i = 0; i < 5; i++)
{
	int szam = random.Next(51);
	Console.Write($"{szam}, ");
}
Console.WriteLine();


// képezzünk 40 random számot [50,99]-ben és egymás mellé csak 8-at írunk ki,
// azaz minden 8. számnál alkalmazzon sortörést
for (int i = 1; i <= 40; i++)
{
	int szam = random.Next(50) + 50;
	Console.Write($"{szam} ");
	if (i % 8 == 0) Console.WriteLine();
}

// készítsen egy oktatóprogramot, amely megkérdezi a felhasználót, hogy
// mennyi feladatot készítsen. A feladatok az osztást, szorzást, kivonást, összeadást gyakoroltassa
// a számok amikkel dolgozzon meg [1,9]-ban legyenek
// egy feladat kiírása, nézzen ki így: 6 + 9 =
// ha a felhasználó által megadott szám az helyes,
// növelje a helyes válaszainak a számát eggyel
// a végén írassa ki hány pontot szerzett a mennyiből
// és adja meg annak az értékét százalékosan is, majd osztályoza le a feladatsorát
Console.WriteLine("OKTATÓ PROGRAM");
Console.WriteLine("hány db feladat legyen?");
int feladatDbSzam = Convert.ToInt32(Console.ReadLine());
int helyesValaszokSzama = 0;
for (int i = 1; i <= feladatDbSzam; i++)
{
	int szam1 = random.Next(9)+1;
	int szam2 = random.Next(9)+1;
	int op = random.Next(4)+1;
	double valasz = 0;
	switch (op)
	{
		case 1:
			Console.Write($"{szam1} + {szam2} = ");
			valasz = Convert.ToInt32(Console.ReadLine());
			if (valasz == szam1 + szam2) helyesValaszokSzama++;
			break;
		case 2:
			Console.Write($"{szam1} - {szam2} = ");
			valasz = Convert.ToInt32(Console.ReadLine());
			if (valasz == szam1 - szam2) helyesValaszokSzama++;
			break;
		case 3:
			Console.Write($"{szam1} * {szam2} = ");
			valasz = Convert.ToInt32(Console.ReadLine());
			if (valasz == szam1 * szam2) helyesValaszokSzama++;
			break;
		case 4:
			Console.Write($"{szam1} / {szam2} = ");
			valasz = Convert.ToDouble(Console.ReadLine());
			if (valasz == (double)szam1 / szam2) helyesValaszokSzama++;
			break;
	}
}

Console.WriteLine($"ennyi pontot szereztél: {helyesValaszokSzama}/{feladatDbSzam}");
double szazalek = (double)helyesValaszokSzama / feladatDbSzam * 100;
Console.WriteLine($"ennyi százalékos lett: {szazalek:0.00}%");

if (szazalek > 90) Console.WriteLine("jeles (5)");
else if (szazalek > 80) Console.WriteLine("jó (4)");
else if (szazalek > 70) Console.WriteLine("közepes (3)");
else if (szazalek > 60) Console.WriteLine("elégséges (2)");
else Console.WriteLine("elégtelen (1)");

Console.ReadKey();
```