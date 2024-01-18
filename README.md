```c#
static void Main(string[] args)
{
	// karakterek, string, mint tömb
	feladat1();
	feladat2();
	feladat3();
	feladat4();
	feladat5();
	feladat6();
	feladat7();
	feladat8();
	feladat9();
	feladat10();
	feladat11();

	//Új téma: számrendszerek közötti váltás-----------------------------------------------------------------------
	feladat12();

	// Új téma: tömbök--------------------------------------------------------------------
	// tömbök fajtái:
	// 1 dimenziós-->vektor
	// 2 dimenziós-->matrix
	// string tömb valójában egy 2 dimenziós tömb:
	string[] szekreny = new string[] { "sapka", "sál" };
	Console.WriteLine(szekreny[0][0]); // s <-- emiatt a tulajdonága miatt 2 dimenziós
	Console.WriteLine(szekreny[0]); // sapka
	feladat13();
	feladat14();
	Console.ReadKey();
}

private static void feladat14()
{
	// töltsön fel egy 10 elemű int tömböt [1,100] random számokkal
	// majd listázza ki
	int[] randomSzamok = new int[10];
	Random random = new Random();
	for (int i = 0; i < randomSzamok.Length; i++)
	{
		randomSzamok[i] = random.Next(100) + 1;
	}
	// itt listázzuk ki az értékeit
	for (int i = 0; i < randomSzamok.Length; i++)
	{
		Console.WriteLine(randomSzamok[i]);
	}
}

private static void feladat13()
{
	// tölsük fel a szekrény tömböt ruhaneműkkel, majd írassuk ki az elemeit
	string[] szekreny1 = new string[4];
	for (int i = 0; i < 4; i++)
	{
		Console.Write("Add meg mi kerüljön a szekrénybe: ");
		szekreny1[i] = Console.ReadLine();
	}
	// itt íratjuk ki az elmeit
	for (int i = 0; i < szekreny1.Length; i++)
	{
		Console.WriteLine(szekreny1[i]);
	}

}

private static void feladat12()
{
	// dec2bin: paraméterben egy 10-es számrendszerbeli számot adunk át a függvénynek
	// és visszatér a 2-es számrendszerbeli értékével
	string bin = dec2bin(40);
	// bin2dec: paraméterben egy 2-es számrendszerbeli szöveget adunk át a függvénynek
	// és visszatér a 10-es számrendszerbeli értékével
	int dec = bin2dec("101000");
	// k
	Console.WriteLine(bin);
	Console.WriteLine(dec);
}

private static void feladat11()
{
	// titkosító, visszafejtő program
	string uzenet = "ASZTAL";
	string titkositottUzenet = titkositas(uzenet, 25);
	string visszafejtettUzenet = visszafejtes(titkositottUzenet, 25);
	Console.WriteLine(uzenet); // Eredeti üzenet
	Console.WriteLine(titkositottUzenet); // Titkosított üzenet
	Console.WriteLine(visszafejtettUzenet); // viisszafejtett üzenet

}

private static int bin2dec(string bin)
{
	int hatvany = bin.Length - 1;
	int dec = 0;
	for (int i = 0; i < bin.Length; i++)
	{
		if (bin[i] == '1') dec += (int)Math.Pow(2, hatvany);
		hatvany--;
	}
	return dec;
}

private static string dec2bin(int dec)
{
	int hatvany = 0;
	for (; Math.Pow(2,hatvany+1)<dec; ) hatvany++;
	int osszeg = 0;
	string bin = "";
	;
	for (int i = hatvany; i >= 0; i--)
	{
		if ((osszeg + (int)Math.Pow(2, i)) <= dec)
		{
			osszeg += (int)Math.Pow(2, i);
			bin += "1";
		}
		else bin += "0";
	}
	return bin;
}

private static string visszafejtes(string titkositottUzenet, int eltolas)
{
	// minden karaktert x értékkel visszatol
	string visszafejtettUzenet = "";
	for (int i = 0; i < titkositottUzenet.Length; i++)
	{
		visszafejtettUzenet += (char)(titkositottUzenet[i] - eltolas);
	}
	;
	return visszafejtettUzenet;
}

private static string titkositas(string uzenet, int eltolas)
{
	// minden karaktert x értékkel eltol
	string rejtjelezettUzenet = "";
	for (int i = 0; i < uzenet.Length; i++)
	{
		rejtjelezettUzenet += (char)(uzenet[i] + eltolas);
	}
	return rejtjelezettUzenet;
}

private static void feladat10()
{
	// írjuk ki a mondatból a második szót
	string mondat = "Az ég kék";
	int spaceSzamlalo = 0;
	for (int i = 0; spaceSzamlalo<2; i++)
	{
		if (spaceSzamlalo == 1 && mondat[i]!=' ')
		{
			Console.Write(mondat[i]);
		}
		if (mondat[i]==' ') spaceSzamlalo++;
	}
}

private static void feladat9()
{
	// írassuk ki fordítva a nevet, és szóköz mentén tördeljük
	string nev2 = "Erős Pista";

	for (int i = nev2.Length-1; i >= 0; i--)
	{
		if (nev2[i]== ' ')
		{
			Console.WriteLine();
		}
		else { Console.Write(nev2[i]); }
	}
}

private static void feladat8()
{
	// ha egy nevet bekérünk szóköz mentén tördeljük

	string nev = "Erős Pista";
	for (int i = 0; i < nev.Length; i++)
	{
		if (nev[i] == ' ')
		{
			Console.WriteLine();
		}
		else
		{
			Console.Write(nev[i]);
		}
	}
}

private static void feladat7()
{
	// kérjünk be egy karaktert és döntsük el, hogy szám-e 

	// karaktert a konzolról úgy tudunk kinyerni, hogy felhasználjuk azt a tényt, hogy
	// minden string i. eleme az karakter. A Console.ReadLine az stringet ad vissza
	char karakter = Console.ReadLine()[0];
	// vagy fogom és meghívom az Convert.ToChar konvertáló függvényt
	char karakter2 = Convert.ToChar(Console.ReadLine());
	// switch-el kicsit hosszasan lehet megoldani
	switch ((int)karakter)
	{
		case 48:
		case 49:
		case 50:
		case 51:
		case 52:
		case 53:
		case 54:
		case 55:
		case 56:
		case 57:
			Console.WriteLine("ez egy szám");
			break;
		default:
			Console.WriteLine("karakter");
			break;
	}
	// if-el könnyebben megoldható hogy egy [48,57] intervallumba
	// ha bele esik a konzolról kinyert karakter, akkor szám, egyébként nem
	if ((int)karakter >= 48 && (int)karakter <= 57)
	{
		Console.WriteLine("ez egy szám");
	}
	else
	{
		Console.WriteLine("karakter");
	}
}

private static void feladat6()
{
	// vizsgáljuk meg, hogy a 'k' betűnek mi az indexe a megadott szövegben, 
	// ha nincs benne, írjuk ki, hogy nem volt benne 'k' betű, ha volt, 
	// akkor, hogy volt benne.
	string varazslat = "abrakadabra";
	int index = -1;
	for (int i = 0; i < varazslat.Length; i++)
	{
		if (varazslat[i] == 'k') index = i;
	}
	if (index == -1)
	{
		Console.WriteLine("nem volt benne 'k' betű");
	}
	else
	{
		Console.WriteLine("volt benne 'k' betű");
	}
}

private static void feladat5()
{
	// járjuk körbe a megadott szöveg minden karakterét,
	// és írjuk ki azok ASCII kódbéli értékeit szóközzel elválasztva egymás mellé
	string sz1 = "ablak";
	for (int i = 0; i < sz1.Length; i++)
	{
		Console.Write($"{(int)sz1[i]} ");
	}
	Console.WriteLine();
}

private static void feladat4()
{
	// ha adott egy mac cím, járjuk körbe a karaktereit,
	// és ahol '-' (kötőjel) van azt cseréljük ':' (kettőspont)-ra
	// minden más karaktert változatlanul írjuk ki
	string mac = "6C-6A-77-44-C8-E3";
	for (int i = 0; i < mac.Length; i++)
	{
		if (mac[i] == '-')
		{
			Console.Write(":");
		}
		else
		{
			Console.Write(mac[i]);
		}
	}
	Console.WriteLine();
}

private static void feladat3()
{
	/*
	 kérjen be egy tetszőleges szöveget. Majd minden második karakterét 
	 írja ki nagybetűsen.
	 */
	string sz = "alma"; // most nem kértem be szöveget, hanem megadtam egyből egy változóba
	for (int i = 0; i < sz.Length; i++)
	{
		if (i % 2 == 0)
		{
			Console.Write(sz[i]);
		}
		else
		{
			Console.Write((char)(sz[i] - 32));
		}
	}
	Console.WriteLine();
}

private static void feladat2()
{
	// kérjen be egy tetszőleges szöveget. Majd csak minden második karakterét 
	// írja ki.
	string sz = "kisebb";
	for (int i = 1; i < sz.Length; i += 2)
	{
		Console.Write(sz[i]);
	}
	Console.WriteLine();
}

private static void feladat1()
{
	/*
	 Kérjen be egy kisbetűs teljes nevet (vezeteknev keresztnev). 
	Majd írja ki a monogramját, nagybetűsen, pontokkal tűzdelve. Bármilyen
	hosszabb, rövidebb névre működjön. pl.: Kiss Pista --> K.P.
	 */
	string teljesNev = Console.ReadLine();
	Console.Write($"{(char)(teljesNev[0] - 32)}.");
	for (int i = 0; i < teljesNev.Length; i++)
	{
		if (teljesNev[i] == ' ')
		{
			Console.WriteLine($"{(char)(teljesNev[i + 1] - 32)}.");
		}
	}
}
```