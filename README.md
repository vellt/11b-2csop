```c#
static void Main(string[] args)
{
	ketdimenziosTombokAlgoritmizalasa();
	egydimenziosTombokAlgoritmizalasa();
	Console.ReadKey();
}

private static void egydimenziosTombokAlgoritmizalasa()
{
	Console.WriteLine("Adja meg a tömb hosszát");
	int n = Convert.ToInt32(Console.ReadLine());
	string[] tomb = new string[n];
	Console.WriteLine("Add meg az adatokat:");
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = Console.ReadLine();
	}
	// a.) 
	bool van = false;
	for (int i = 0; van==false && i < tomb.Length; i++)
	{
		string szoveg = tomb[i];
		for (int j = 0; van=false && j < szoveg.Length; j++)
		{
			if (szoveg[j] == 'a') van = true;
		}
	}
	Console.WriteLine(van ? "van" : "nincs");

	// b.)
	int[] egyediErtekek = new int[tomb.Length];
	int index = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		int szovegHossza = tomb[i].Length;
		van = false;
		for (int j = 0; van==false&& j < egyediErtekek.Length; j++)
		{
			if (egyediErtekek[j] == szovegHossza) van = true;
		}
		if (van == false)
		{
			egyediErtekek[index++] = szovegHossza;
		}
	}
	if (index != tomb.Length)
	{
		Console.WriteLine("nem tartalmaz a tömb eltérő hosszúságú szöv. adatot");
	}
	else
	{
		Console.WriteLine("A tömb eltérő hosszúságú szöv. adatokat tartalmaz");
	}

	// c.)
	for (int i = 0; i < tomb.Length; i++)
	{
		string szoveg = tomb[i];
		for (int j = 0; j < szoveg.Length; j++)
		{
			if(szoveg[j]>='A' && szoveg[j] <= 'Z')
			{
				Console.Write((char)(szoveg[j]+32));
			}
			else
			{
				Console.Write(szoveg[j]);
			}
		}
		Console.WriteLine();
	}
}

private static void ketdimenziosTombokAlgoritmizalasa()
{
	Random r = new Random();
	int[,] homerseklet = new int[12, 30];
	// [-10,10]
	double osszAtlag = 0;
	for (int i = 0; i < homerseklet.GetLength(0); i++) // 12
	{
		int egyHonapOsszHomerseklete = 0;
		for (int j = 0; j < homerseklet.GetLength(1); j++) //30
		{
			homerseklet[i, j] = r.Next(21)-10; // [-10,10]
			egyHonapOsszHomerseklete += homerseklet[i, j];
		}
		double atlag = egyHonapOsszHomerseklete / (double)homerseklet.GetLength(1);
		osszAtlag += atlag;
		Console.WriteLine($"{i + 1}. hónap átlaghőmérséklete: {atlag:0.00}");
	}
	double evesAtlagHom = osszAtlag / homerseklet.GetLength(0);
	Console.WriteLine($"éves átlaghőm.: {evesAtlagHom:0.00}");

	bool van = false;
	for (int i = 0;van==false && i < homerseklet.GetLength(0); i++)
	{
		int osszHomerseklet = 0;
		for (int j = 0; j < homerseklet.GetLength(1); j++)
		{
			osszHomerseklet += homerseklet[i, j];
		}
		double atlag = (double)osszHomerseklet / homerseklet.GetLength(1);
		if (atlag < -3)
		{
			van = true;
		}
	}
	Console.WriteLine(van ? "van" : "nincs");
}
```