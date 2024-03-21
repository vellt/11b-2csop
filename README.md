```c#
static void Main(string[] args)
{
	masodikOra();
	harmadik();
	Console.ReadKey();
}

private static void harmadik()
{
	// Állítson elő N elemű vektort. Elemeit[-10, 10] - ban
	// töltse fel majd írja ki a képernyőre egy sorban!
	// Az N értékét a felhasználótól kérje be!
	Console.WriteLine("Add meg a tömb hosszát");
	int N = Convert.ToInt32(Console.ReadLine());
	int[] vektor = new int[N];
	Random r = new Random();
	for (int i = 0; i < vektor.Length; i++)
	{
		vektor[i] = r.Next(21) - 10; //[-10,10]
		Console.Write($"{vektor[i],-5}");
	}
	// Van-e a számok között 0, ha igen,
	// akkor a vektor hanyadik helyén található?
	int index = -1;
	for (int i = 0; index==-1 && i < vektor.Length; i++)
	{
		if (vektor[i] == 0) index = i;
	}
	Console.WriteLine(index);

	// melyik volt a pozitív számok közül a legnagyobb?
	int maxIndex = 0;
	for (int i = 1; i < vektor.Length; i++)
	{
		if (vektor[i]>=0 && vektor[i]>vektor[maxIndex])
		{
			maxIndex = i;
		}
	}
	Console.WriteLine(vektor[maxIndex]);


	// Páros vagy páratlan számból van több?
	int paratlanszamok = 0;
	int parosszamok = 0;

	for (int i = 0; i < vektor.Length; i++)
	{
		if (vektor[i] % 2 == 0)
		{
			parosszamok++;
		}
		else
		{
			paratlanszamok++;
		}
	}
	if (paratlanszamok > parosszamok)
	{
		Console.WriteLine("A Páratlan számokból van több.");
	}
	else if (paratlanszamok < parosszamok)
	{
		Console.WriteLine("A Páros számokból van több.");
	}
	else
	{
		Console.WriteLine("Mindkettőből ugyan annyi van.");
	}
	// Mennyi átlag alatti érték van a vektorban?
	int ossz = 0;
	for (int i = 0; i < vektor.Length; i++)
	{
		ossz += vektor[i];
	}
	double atlag = ossz / (double)vektor.Length;
	int db = 0;
	for (int i = 0; i < vektor.Length; i++)
	{
		if (vektor[i] < atlag) db++;
	}
	Console.WriteLine(db);
	// adja meg a negatív számok átlagát!
}

private static void masodikOra()
{
	Random r = new Random();
	int[] tomb = new int[10];
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(101) - 50; //[-50,50]
		Console.Write($"{tomb[i],-5}");
	}
	Console.WriteLine();
	// első pozitív számot
	int index = -1;
	for (int i = 0; index == -1 && i < tomb.Length; i++)
	{
		if (tomb[i] >= 0)
		{
			index = i;
		}
	}
	if (index != -1)
	{
		Console.WriteLine(tomb[index]);
	}
	else
	{
		Console.WriteLine("nincs benne pozitív szám");
	}

	// maximum
	int maxIndex = 0;
	for (int i = 1; i < tomb.Length; i++)
	{
		if (tomb[i] >= tomb[maxIndex])
		{
			maxIndex = i;
		}
	}
	Console.WriteLine(tomb[maxIndex]);
}
```