```c#
static void Main(string[] args)
{
	feladat1();
	feladat2();
	matrixIsm();
	feladat3();
	Console.ReadKey();
}

private static void matrixIsm()
{
	int[,] matrix = new int[2,4];
	Random r = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++) // sorokat nézem végig
	{
		for (int j = 0; j < matrix.GetLength(1); j++)
		{
			// mátrix i. sorának j. elemébe helyezek egy random értéket
			matrix[i, j] = r.Next(10); // [0,9]
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

private static void feladat3()
{
	// egy 14 fős csoportban AAF dolgozatot íratott a tanár minden hónapban.
	// eltelt 4 hónap. Mindenki kapott egy-egy jegyet [1,5]-ben minden dolgozatra.

	// - mennyi az osztályátlag
	// - mennyi tanuló áll 5-re (4.6tól)
	// - melyik tanulónak mennyi az átlaga
	// - mennyi tanuló van az osztályátlag alatt

	// - van-e olyan tanuló aki bukásra áll? (1.6 alatt)
	// - van-e olyan tanuló aki csal egyest szerzett a 4 hónap alatt?
	// - van-e olyan tanuló akinek az első jegye és az utolsó jegye megyegyezik
	int[,] osztaly = new int[14, 4];
	Random r = new Random();
	for (int i = 0; i < osztaly.GetLength(0); i++) // végig megy a tanulókon
	{
		for (int j = 0; j < osztaly.GetLength(1); j++) // egy-egy tanuló havi jegyein megy végig
		{
			osztaly[i, j] = r.Next(5)+1;
		}
	}
	// tanulók kiíratása alatta a jegyek lebontása hónapra vonatkozóan
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		Console.WriteLine($"{i+1}.tanuló jegyei:");
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			Console.WriteLine($"\t-{j+1}.hónapban: {osztaly[i, j]}");
		}
	}
	// - mennyi az osztályátlag
	double osztalyOsszeg = 0;
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		int tanuloOsszeg = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			tanuloOsszeg += osztaly[i, j];
		}
		int jegyekSzama = osztaly.GetLength(1);
		double tanuloAtlaga = ((double)tanuloOsszeg / jegyekSzama);
		osztalyOsszeg += tanuloAtlaga;
	}
	int tanulokSzama = osztaly.GetLength(0);
	double osztalyAtlag = osztalyOsszeg / tanulokSzama;
	Console.WriteLine($"osztály átlag: {Math.Round(osztalyAtlag,2)}");

	// - mennyi tanuló áll 5-re (4.6tól)
	int otosreAlloTanulok = 0;
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		int tanuloJegyeiOsszeg = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			tanuloJegyeiOsszeg += osztaly[i, j];
		}
		int jegyekSzama = osztaly.GetLength(1);
		double tanuloAtlaga = tanuloJegyeiOsszeg / (double)jegyekSzama;
		if (tanuloAtlaga >= 4.6) otosreAlloTanulok++;
	}
	Console.WriteLine($"ennyi db tanuló áll 5-re: {otosreAlloTanulok}");

	// - melyik tanulónak mennyi az átlaga
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		int tanuloOsszesJegye = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			tanuloOsszesJegye += osztaly[i, j];
		}
		int jegyekSzama = osztaly.GetLength(1);
		double tanuloAtlaga = tanuloOsszesJegye / (double)jegyekSzama;
		Console.WriteLine($"A(z) {i+1}. tanuló átlaga: {tanuloAtlaga}");
	}

	// - mennyi tanuló van az osztályátlag alatt
	int tanulokAzOsztalyatlagAlatt = 0;
	for (int i = 0; i < osztaly.GetLength(0); i++)
	{
		int tanuloOsszesJegye = 0;
		for (int j = 0; j < osztaly.GetLength(1); j++)
		{
			tanuloOsszesJegye += osztaly[i, j];
		}
		int jegyekSzama = osztaly.GetLength(1);
		double tanuloAtlaga = tanuloOsszesJegye / (double)jegyekSzama;
		if (tanuloAtlaga < osztalyAtlag) tanulokAzOsztalyatlagAlatt++;
	}
	Console.WriteLine($"Az osztályátalag alatt {tanulokAzOsztalyatlagAlatt}db tanuló van.");

}

private static void feladat1()
{
	/*
	 12 hónapon keresztül tettünk félre változó mennyiségű
	összeget. 
	- mennyi összeget tettünk félre egy évben
	- mennyi pénzt tettünk félre havonta átlagosan
	 */

	int[] malacpersely = new int[12];
	Random random = new Random();
	int osszeg = 0;
	for (int i = 0; i < malacpersely.Length; i++)
	{
		malacpersely[i] = random.Next(20000);
		osszeg = osszeg + malacpersely[i];
	}
	Console.WriteLine($"ennyit tettunk felre egy evben: {osszeg}");
	Console.WriteLine($"atlagosan havonta: {Math.Round(osszeg / 12.0, 2)}");


}

private static void feladat2()
{

	// véletlen 10 elemű számsorozat [-10,10] 
	int[] szamsorozat = new int[10];
	Random random = new Random();
	for (int i = 0; i < szamsorozat.Length; i++)
	{
		szamsorozat[i] = random.Next(21) - 10;
		Console.Write($"{szamsorozat[i]} ");
	}
	Console.WriteLine();

	// -mennyi páratlan szám van(megszámlálás)
	int paratlanszamlalo = 0;
	for (int i = 0; i < szamsorozat.Length; i++)
	{
		if (szamsorozat[i] % 2 != 0)
		{
			paratlanszamlalo++;
		}
	}
	Console.WriteLine($"Páratlan számok: {paratlanszamlalo}");

	//  - mennyi 10nél kisebb (megszámlálás)
	int tizesszamlalo = 0;
	for (int i = 0; i < szamsorozat.Length; i++)
	{
		if (szamsorozat[i]<10)
		{
			tizesszamlalo++;
		}
	}
	Console.WriteLine($"Enyi tíznél kisebb szám van: {tizesszamlalo}");

	// -mennyi az átlaguk(összegzés)
	int osszeg = 0;
	for (int i = 0; i < szamsorozat.Length; i++)
	{
		osszeg += szamsorozat[i];
	}
	Console.WriteLine($"Átlag:{Math.Round(osszeg/(double)szamsorozat.Length, 2)}");

	// - van-e benne negatív szám (eldöntés)
	bool vanE = false;
	int index = 0;
	while (vanE==false && index<szamsorozat.Length)
	{
		if (szamsorozat[index++]<0) vanE = true;
	}
	Console.WriteLine((vanE ? "Van" : "Nincs")+" benne negatív szám");

	// -van - e az átlagtól nagyobb szám benne. (megszámlálás + eldöntés)
	int osszeg2 = 0;
	for (int i = 0; i < szamsorozat.Length; i++)
	{
		osszeg2 += szamsorozat[i];
	}
	double atlag = osszeg2/szamsorozat.Length;
	bool vanEh = false;
	int index2 = 0;
	while (vanEh==false && index2<szamsorozat.Length)
	{
		if (szamsorozat[index2++] > atlag) vanEh = true;
	}
	Console.WriteLine((vanEh ? "Van" : "Nincs")+ " benne az átlagtól nagyobb szám");
}
```