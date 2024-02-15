```c#
static void Main(string[] args)
{
	// Programozási tételek/ nevezetes algoritmusok
	// ISMÉTLÉS
	osszegzesTetele();
	megszamlalasTetele();
	eldontesTetele();
	matrix();
	// feladatok
	komplex();
	komplex1();
	komplex2();
	komplex3();
	Console.ReadKey();
}

private static void komplex3()
{
	int[] tomb = new int[] { 3, 8, -2, 5, 0, 10, -7, 4, 9 };

	feladat1(tomb);
	feladat2(tomb);
	feladat3(tomb);
	feladat4(tomb);
}

/// <summary>
/// mennyi az átlaguk
/// </summary>
private static void feladat4(int[] tomb)
{
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
	}
	double atlag = osszeg / (double)tomb.Length;
	Console.WriteLine(Math.Round(atlag,2));
}

/// <summary>
/// van-e benne pozitív szám
/// </summary>
private static void feladat3(int[] tomb)
{
	bool vanE = false;
	int i = 0;
	while (vanE == false && i < tomb.Length)
	{
		if (tomb[i] >= 0) vanE = true;
		i++;
	}
	Console.WriteLine(vanE ? "van" : "nincs" + "benne pozitív szám");
}

/// <summary>
/// van-e benne páros szám
/// </summary>
private static void feladat2(int[] tomb)
{
	bool vanE = false;
	int i = 0;
	while (vanE==false && i<tomb.Length)
	{
		if (tomb[i] % 2 == 0) vanE = true;
		i++;
	}
	Console.WriteLine(vanE?"van":"nincs" +"benne páros szám");
}

/// <summary>
/// páratlan számok darabszám
/// </summary>
private static void feladat1(int[] tomb)
{
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 2 != 0) szamlalo++;
	}
	Console.WriteLine(szamlalo);
}

private static void komplex2()
{
	string[] tomb = new string[] { "alma", "körte", "narancs", "szilva", "Mandarin" };
	feladat1(tomb);
	feladat2(tomb);
	feladat3(tomb);
	feladat4(tomb);
	feladat5(tomb);
}

/// <summary>
/// mennyi az átlagos hosszuk a szövegeknek
/// 2 tizedesre
/// </summary>
private static void feladat5(string[] tomb)
{
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i].Length;
	}
	double atlag = osszeg / (double)tomb.Length;
	Console.WriteLine(Math.Round(atlag, 2));
}

/// <summary>
///  nagybetűvel kezdődő szavak száma
/// </summary>
private static void feladat4(string[] tomb)
{
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if(tomb[i][0]>='A' && tomb[i][0] <= 'Z')
		{
			szamlalo++;
		}
	}
	Console.WriteLine(szamlalo);
}

/// <summary>
/// van-e páros hosszúságú szó
/// </summary>
private static void feladat3(string[] tomb)
{
	bool vanE = false;
	int i = 0;
	while (vanE==false && i<tomb.Length)
	{
		if (tomb[i].Length % 2 == 0) vanE = true;
		i++;
	}
	if (vanE) Console.WriteLine("volt páros hosszúságú szó");
	else Console.WriteLine("nem volt olyan");
}

/// <summary>
/// van-e szilva a tömbben
/// </summary>
private static void feladat2(string[] tomb)
{
	bool vanE = false;
	int i = 0;
	while (vanE==false && i<tomb.Length)
	{
		if (tomb[i] == "szilva") vanE = true;
		i++;
	}
	if (vanE) Console.WriteLine("Van szilva benne");
	else Console.WriteLine("nincs benne szilva");
}

/// <summary>
/// mennyi legalább 5 karakteres szó van benne
/// </summary>
private static void feladat1(string[] tomb)
{
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb.Length >= 5) szamlalo++;
	}
	Console.WriteLine(szamlalo);
}

private static void komplex1()
{
	string szoveg = "CASIC nevu kinai ceg megdonti a " +
		"vasutipar rekordjait. Keszul az 1000km/h-s vonat.";
	// mennyi betű van benne
	// mennyi szám van benne
	// van-e benne /-jel
	// mennyi kisbetű van benne
	// hány százaléka szám a teljes szövegnek, 2 tizedesre kerekítve
	feladat1(szoveg);
	feladat2(szoveg);
	feladat3(szoveg);
	feladat4(szoveg);
	feladat5(szoveg);
}

/// <summary>
///  hány százaléka szám a teljes szövegnek, 2 tizedesre kerekítve
/// </summary>
private static void feladat5(string szoveg)
{
	int szamDarab = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if(szoveg[i]>='0' && szoveg[i] <= '9')
		{
			szamDarab++;
		}
	}

	double szazalek = Math.Round((szamDarab / (double)szoveg.Length)*100, 2);
	Console.WriteLine($"karakter szám százalék: {szazalek}%");
}

/// <summary>
/// mennyi kisbetű van benne
/// </summary>
private static void feladat4(string szoveg)
{
	int szamlalo = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] >= 'a' && szoveg[i] <= 'z') szamlalo++;
	}
	Console.WriteLine(szamlalo);
}

private static void feladat3(string szoveg)
{
	bool vanE = false;
	int i = 0;
	while (vanE==false && i<szoveg.Length)
	{
		if (szoveg[i] == '/')
		{
			vanE = true;
		}
		i++;
	}
	if (vanE) Console.WriteLine("van / jel");
	else Console.WriteLine("nincs / jel");
}

private static void feladat2(string szoveg)
{
	int szamlalo = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] >= '0' && szoveg[i] <= '9') szamlalo++;
	}
	Console.WriteLine(szamlalo);
}

/// <summary>
/// mennyi betű van benne
/// </summary>
private static void feladat1(string szoveg)
{
	int szamlalo = 0;
	for (int i = 0; i < szoveg.Length; i++)
	{
		if(
			(szoveg[i]>='a' && szoveg[i]<='z') || 
			(szoveg[i] >= 'A' && szoveg[i] <= 'Z')
		)
		{
			szamlalo++;
		}
	}
}

/// <summary>
/// iskolai versenyen 2 10 fős csoport vett részt. 
/// mindenki kapott [1,10] pontszámot;
/// - melyik csoport mennyi pontot szerzett, 
/// melyik csoport lett az első helyezett
/// - mennyi tanuló szerzett az első csoportból 1 pontot.
/// - volt-e a kettes csoportban aki 10 pontot szerzett
/// </summary>
private static void komplex()
{
	int[,] matrix = feltolt();
	feladat1(matrix);
	feladat2(matrix);
	feladat3(matrix);
}

private static int[,] feltolt()
{
	int[,] matrix = new int[2, 10];

	Random r = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			matrix[i, j] = r.Next(10) + 1;

		}
	}
	return matrix;
}

/// <summary>
/// volt-e a kettes csoportban aki 10 pontot szerzett
/// </summary>
private static void feladat3(int[,] matrix)
{
	bool voltE = false;
	int i = 0;
	while (voltE==false && i<matrix.GetLength(1))
	{
		if (matrix[1, i] == 10)
		{
			voltE = true;
		}
		i++;
	}
	if (voltE) Console.WriteLine("volt olyan akinek 10 pontja volt");
	else Console.WriteLine("nem volt olyan a második csoportban");
}

// - mennyi tanuló szerzett az első csoportból 1 pontot.
private static void feladat2(int[,] matrix)
{
	int szamlalo = 0;
	for (int i = 0; i < matrix.GetLength(1); i++)
	{
		if (matrix[0, i] == 1) szamlalo++;
	}
	Console.WriteLine(szamlalo);
}

/// <summary>
/// melyik csoport mennyi pontot szerzett, 
/// melyik csoport lett az első helyezett
/// </summary>
private static void feladat1(int[,] matrix)
{
	int elsoCsoportOsszeg = 0;
	int masodikCsooportOsszeg = 0;
	for (int i = 0; i < matrix.GetLength(1); i++)
	{
		elsoCsoportOsszeg += matrix[0, i];
		masodikCsooportOsszeg+= matrix[1, i];
	}
	Console.WriteLine($"Elsőcsoport összeg: {elsoCsoportOsszeg}");
	Console.WriteLine($"Másodikcsoport összeg: {masodikCsooportOsszeg}");
	if (elsoCsoportOsszeg > masodikCsooportOsszeg)
	{
		Console.WriteLine("Az elso csoport nyert");
	}
	else if (elsoCsoportOsszeg < masodikCsooportOsszeg)
	{
		Console.WriteLine("A masodik csoport nyert");
	}
	else Console.WriteLine("Dontetlen");
}

/// <summary>
/// mátrix--> az a 2 dimenziós tömb
/// </summary>
private static void matrix()
{
	int[,] matrix = new int[5,4];
	Random r = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			matrix[i, j] = r.Next(11); //[0,10]
		}
	}
	// kiíratás
	for (int i = 0; i < matrix.GetLength(0); i++)
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			Console.Write($"{matrix[i, j]} ");
		}
		Console.WriteLine();
	}
}

/// <summary>
/// VAN-e benne a feltételnek megfelelő elem. Ha igen, lépjen ki a ciklusból
/// </summary>
private static void eldontesTetele()
{
	int[] tomb = new int[] { 1, 3, 5, 6, 7, 8, 9, 10 };
	bool vanE = false;
	int i = 0;
	while (vanE==false && i<tomb.Length)
	{
		if (tomb[i] == 3)
		{
			vanE = true;
		}
		i++;
	}
	if (vanE == true) Console.WriteLine("volt benne 3-as");
	else Console.WriteLine("nem volt benne 3-as");
}

/// <summary>
/// megszámláljuk azokat az elemeit a tömbnek amik egy feltételnek megfelelnek
/// </summary>
private static void megszamlalasTetele()
{
	int[] tomb = new int[] { 3, 3, 2, 1 };
	int szamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] == 3) szamlalo++;
	}
	Console.WriteLine(szamlalo);
}

/// <summary>
/// össze kell adni a tömb értékeit
/// </summary>
private static void osszegzesTetele()
{
	int[] tomb = new int[3];
	tomb[0] = 3;
	tomb[1] = 3;
	tomb[2] = 3;

	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
	}
	Console.WriteLine(osszeg); // 9

	// konkatenáció / szövegösszefűzés
	string osszeg1 = "";
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg1 += tomb[i];
	}
	Console.WriteLine(osszeg1); // 333
}
```