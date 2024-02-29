```c#
static void Main(string[] args)
{
	feladat1();
	programozasitetelek();
	matrixGyakorlas();
	Console.ReadKey();
}

private static void matrixGyakorlas()
{
	/*
	 Gyűjtsük be 5 csapat 7 meccsének az eredményeit:
	0-->döntetlen (1 pont), 1-->nyert (3 pont), 2-->vesztett (0 pont)
	 */
	int[,] csapatok = new int[5, 7];
	Random r = new Random();
	for (int i = 0; i < csapatok.GetLength(0); i++)
	{
		for (int j = 0; j < csapatok.GetLength(1); j++)
		{
			csapatok[i, j] = r.Next(3);
			string eredmeny = "";
			switch (csapatok[i,j])
			{
				case 0: eredmeny="döntetlent"; break;
				case 1: eredmeny="Győzelem"; break;
				case 2: eredmeny="Vereség"; break;
			}
			Console.Write($"{eredmeny,15}");
		}
		Console.WriteLine();
	}

	// hány csapat vesztett a 7. hónapban
	int hetedikHonapVesztesDbszam = 0;
	for (int i = 0; i < csapatok.GetLength(0); i++)
	{
		int utolsoMeccsAdata = csapatok[i, csapatok.GetLength(1) - 1];
		if (utolsoMeccsAdata == 2) hetedikHonapVesztesDbszam++;
	}
	Console.WriteLine(hetedikHonapVesztesDbszam);

	string[] csapatNevek = new string[]
	{
		"Újpest",
		"Fradi",
		"DVSC",
		"DVTK",
		"DEAC"
	};

	// melyik csapatnak mennyi pontja van
	for (int i = 0; i < csapatok.GetLength(0); i++)
	{
		int osszpont = 0;
		for (int j = 0; j < csapatok.GetLength(1); j++)
		{
			switch (csapatok[i,j])
			{
				case 0: osszpont += 1; break;
				case 1: osszpont += 3; break;
			}
		}
		Console.WriteLine($"{csapatNevek[i]}: {osszpont}pont");
	}

	// mennyi győztes meccset játszott a DVSC
	int gyoztesMeccsekSzama = 0;
	for (int i = 0; i < csapatok.GetLength(1); i++)
	{
		if (csapatok[2, i] == 1) gyoztesMeccsekSzama++;
	}
	Console.WriteLine($"DVSC győztes meccsei: {gyoztesMeccsekSzama}");

	// volt-e olyan csapat akinek csak győzelme van
	bool vanCsakGyoztes = false;
	for (int i = 0; vanCsakGyoztes==false  && i < csapatok.GetLength(0); i++)
	{
		int szamlalo = 0;
		for (int j = 0; j < csapatok.GetLength(1); j++)
		{
			if (csapatok[i, j] == 1)
				szamlalo++;
		}
		if (szamlalo == 7) vanCsakGyoztes = true;
	}
	Console.WriteLine(vanCsakGyoztes ? "van" : "nincs");

	// volt-e olyan csapat aki legalább 3x győzött
	bool vanLeglabb3Gyozelem = false;
	for (int i = 0; vanLeglabb3Gyozelem == false && i < csapatok.GetLength(0); i++)
	{
		int szamlalo = 0;
		for (int j = 0; j < csapatok.GetLength(1); j++)
		{
			if (csapatok[i, j] == 1)
				szamlalo++;
		}
		if (szamlalo >=3) vanLeglabb3Gyozelem = true;
	}
	Console.WriteLine(vanLeglabb3Gyozelem ? "van" : "nincs");

	// melyik csapatnak mennyi az átlag pontjai/meccs
	for (int i = 0; i < csapatok.GetLength(0); i++)
	{
		int osszpontszam = 0;
		for (int j = 0; j < csapatok.GetLength(1); j++)
		{
			switch (csapatok[i, j])
			{
				case 0: osszpontszam += 1; break;
				case 1: osszpontszam += 3; break;
			}
		}
		double atlagPerMeccs = osszpontszam / 7.0;
		Console.WriteLine($"{csapatNevek[i],10} pontszám átlaga / meccs: {Math.Round(atlagPerMeccs)}");
	}
}

private static void programozasitetelek()
{
	int[] tomb = new int[] { 1, 2, 3, 4, 5 };
	string[] mondoka = new string[] { "béka", "ül", "a", "fűben" };
	// összegzés: tömb elemeit összeadja / konkatenáció (összefűzés)
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
	}
	Console.WriteLine(osszeg); // összeg
	string osszefuzes = "";
	for (int i = 0; i < mondoka.Length; i++)
	{
		osszefuzes += mondoka[i] + " ";
	}
	Console.WriteLine(osszefuzes); // string literál képződik

	// megszámlálás: FELTÉTEL mentén számolja meg, mennyi felel meg neki
	int parosSzamokDb = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		if (tomb[i] % 2 == 0) parosSzamokDb++;
	}
	Console.WriteLine(parosSzamokDb);

	// eldöntés: FELTÉTEL mentén döntse el, hogy VAN-e
	// benne olyan elem, ha igen lépjen ki a ciklusból
	bool van = false;
	for (int i = 0; van==false && i < tomb.Length; i++)
	{
		if (tomb[i] % 2 == 0) van = true;
	}
	Console.WriteLine(van ? "van" : "nincs");
}

private static void feladat1()
{
	// egy 14 fős csoportban AAF dolgozatot íratott a tanár minden hónapban.
	// eltelt 4 hónap. Mindenki kapott egy-egy jegyet [1,5]-ben minden dolgozatra.
	int[,] osztaly = new int[14, 4];
	Random r = new Random();
	for (int i = 0; i < osztaly.GetLength(0); i++) // 14
	{
		for (int j = 0; j < osztaly.GetLength(1); j++) //4
		{
			osztaly[i, j] = r.Next(5) + 1;
			Console.Write($"{osztaly[i,j],5}");
		}
		Console.WriteLine();
	}

	// - melyik tanulónak mennyi az átlaga
	double osszesAtlag = 0;
	int mennyiOtosTanulo = 0;
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		int osszeg = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			osszeg += osztaly[i, j];
		}
		double atlag = osszeg / 4.0;
		osszesAtlag += atlag;
		if (atlag >= 4.6) mennyiOtosTanulo++;
		Console.WriteLine($"{i+1}. az átlaga: {atlag:0.00}");
	}

	// - mennyi az osztályátlag
	double osztalyAtlag = osszesAtlag / 14;
	Console.WriteLine($"{osztalyAtlag:0.00}");

	// - mennyi tanuló áll 5-re (4.6tól)
	Console.WriteLine(mennyiOtosTanulo);

	// - mennyi tanuló van az osztályátlag alatt
	int osztalyatlagAlattiTanulokSzama = 0;
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		int ossz = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			ossz += osztaly[i, j];
		}
		double atlag = ossz / 4.0;
		if (atlag < osztalyAtlag)
		{
			osztalyatlagAlattiTanulokSzama++;
		}
	}
	Console.WriteLine(osztalyatlagAlattiTanulokSzama);

	// - van-e olyan tanuló aki bukásra áll? (1.6 alatt)
	bool vanE = false;
	for (int i = 0; vanE==false && i < osztaly.GetLength(0); i++)
	{
		int ossz = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			ossz += osztaly[i, j];
		}
		double atlag = ossz / 4.0;
		if (atlag < 1.6) vanE = true;
	}
	Console.WriteLine(vanE ? "van" : "nincs");

	// - van-e olyan tanuló aki csak egyest szerzett a 4 hónap alatt?
	bool vanE2 = false;
	for (int i = 0; vanE2 == false && i < osztaly.GetLength(0); i++)
	{
		int ossz = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			ossz += osztaly[i, j];
		}
		double atlag = ossz / 4.0;
		if (atlag == 1) vanE2 = true;
	}
	Console.WriteLine(vanE2 ? "van" : "nincs");

	// - van-e olyan tanuló akinek az első jegye és az utolsó jegye megyegyezik
	bool vanE3 = false;
	for (int i = 0; vanE3 == false && i < osztaly.GetLength(0); i++)
	{
		int elsoJegy = osztaly[i, 0];
		int utolsoJegy = osztaly[i, osztaly.GetLength(1) - 1];
		if (elsoJegy == utolsoJegy) vanE3 = true;
	}
	Console.WriteLine(vanE3 ? "van" : "nincs");
}
```