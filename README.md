```c#
static void Main(string[] args)
{
	// összegzés, megszámlálás, eldöntés
	// kiválasztás (eldöntés tétele, de egyben megadja az elem indexét)
	// állítsunk elő 10 egész számot [-50,50]-ból. Az elemeket írjuk ki egy sorban a konzolra.
	// Írjuk ki az első pozitív szám értékét és indexét, ha van ilyen. Ha nincs írjuk ki, hogy nincs ilyen
	feladat1();
	Console.ReadKey();

}

private static void feladat1()
{
	Random r = new Random();
	int[] tomb = new int[10];
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(101) - 50; //-50,50
		Console.Write($"{tomb[i],-5}");
	}
	Console.WriteLine();

	// kiv. tétele
	int index = 0;
	bool van = false;
	for (int i = 0; van == false && i < tomb.Length; i++)
	{
		if (tomb[i] % 2 == 0)
		{
			van = true;
			index = i;
		}
	}
	if (van)
	{
		Console.WriteLine($"Van. Ez pedig az {index}. eleme a tömbnek ami {tomb[index]}");
	}
	else
	{
		Console.WriteLine("nincs ilyen elem");
	}

}
```