```c#
static void Main(string[] args)
{
	// ismetles();
	// vektorokIsm();
	// matrixIsm();

	// PROGRAMOZÁSI TÉTELEK
	// gyakran használt algoritmusok a programozásban
	// tömbökkel kapcsolatos algoritmus (általában)


	// osszegzesTetele();
	// osszegzesTetele1Feladat();

	// megszamlalasTetele();
	// megszamlalasTetele1Feladat();

	// eldontesTetele();
	// eldontesTetele1Feladat();
	komplex();
	Console.ReadKey();
}

/// <summary>
/// iskolai versenyen 2 10 fős csoport vett részt. 
/// mindenki kapott [1,10] pontszámot;
/// - melyik csoport mennyi pontot szerzett, melyik csoport lett az első helyezett
/// - mennyi tanuló szerzett az első csoportból 1 pontot.
/// - volt-e a kettes csoportban aki 10 pontot szerzett
/// </summary>
private static void komplex() 
{
	// kövi órán megnézzük
}

/// <summary>
/// EZ EGY DOKUMENTÁCIÓS KOMMENT
/// </summary>
private static void eldontesTetele1Feladat()
{
	// adott egy string van-e benne szám
	string szov = "az 1. napom";
	bool vanBenne = false;
	for(int i=0; vanBenne==false && i<szov.Length ; i++) // i++ is segít abban hogy hamissá váljon a feltétel
	{
		if (szov[i] >= '0' && szov[i] <= '9')
		{
			vanBenne = true; // az egyik kilépésifeltételünk
		}
	}
	Console.WriteLine((vanBenne == true) ? "van" : "nincs" + " benne");
}

private static void eldontesTetele()
{
	// van-e a tömbben egy adott tulajdonságú elem
	// ha talál egy ilyet az algoritmus akk kilép a ciklusból

	int[] tomb = new int[3];
	tomb[0] = 2;
	tomb[1] = -3;
	tomb[2] = 3;

	// VAN-e benne nullától kisebb elem
	bool vanBenne = false;
	int i = 0;
	while (vanBenne==false && i<tomb.Length)
	{
		if (tomb[i] < 0) vanBenne = true;
		i++;
	}
	if (vanBenne == true) Console.WriteLine("van benne");
	else Console.WriteLine("nincs benne");

	vanBenne = false;
	for (int index=0; vanBenne == false && i < tomb.Length ; index++ ) if (tomb[i] < 0) vanBenne = true;
	Console.WriteLine((vanBenne==true)?"van":"nincs"+" benne");
}

private static void megszamlalasTetele1Feladat()
{
	// 12 elemű tömb, [-50,50]. írjuk ki az értékeket egy sorban
	// mennyi a negatív és mennyi a pozitív
	Random r = new Random();
	int[] tomb = new int[12];
	int negSzamlalo = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(101) - 50; //[-50,50]
		Console.Write($"{tomb[i],5}");
		// Console.Write($"{tomb[i]}\t");
		// Console.Write($"{tomb[i]} ");
		if (tomb[i] < 0) negSzamlalo++;
	}
	Console.WriteLine();
	Console.WriteLine($"Pozitív: {tomb.Length-negSzamlalo}db");
	Console.WriteLine($"Negatív: {negSzamlalo}db");
}

private static void megszamlalasTetele()
{
	// mennyi olyan elem van amely egy bizonyos feltételnek megfelel
	// összeg=összeg+1;
	// összeg+=1;
	// összeg++;

	char[] karTomb = new char[4];
	karTomb[0] = 'T';
	karTomb[1] = 'O';
	karTomb[2] = 'L';
	karTomb[3] = 'L';

	// mennyi 'L' betű van benne
	int szamlalo = 0;
	for (int i = 0; i < karTomb.Length; i++)
	{
		if (karTomb[i] == 'L') szamlalo++;
	}
	Console.WriteLine(szamlalo);
}

private static void osszegzesTetele1Feladat()
{
	// 12 egész szám [0,100], írjuk ki az elemeit egy sorba
	// majd 3 tizedes pontosan az átlagukat is adjuk meg

	Random r = new Random();
	int[] tomb = new int[12];
	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(101); //[0,100]
		Console.Write($"{tomb[i],5}");
		osszeg += tomb[i];
	}
	Console.WriteLine();
	double avg = osszeg / (double)tomb.Length;
	Console.WriteLine($"átlaguk: {Math.Round(avg,3)}");
}

private static void osszegzesTetele()
{
	// a tömb elemeinek az összege
	// összeg=összeg+a tömb aktuális eleme
	// összeg+=a tömb aktuális eleme

	int[] tomb = new int[3];
	tomb[0] = 10;
	tomb[1] = 10;
	tomb[2] = 10;

	int osszeg = 0;
	for (int i = 0; i < tomb.Length; i++)
	{
		osszeg += tomb[i];
		// vagy:
		// osszeg =osszeg+ tomb[i];
	}
	Console.WriteLine($"a tömb eleminek az összege: {osszeg}");

	// karakter tömbbel ugyan ez
	char[] karakterT = new char[3];
	karakterT[0] = 'P';
	karakterT[1] = 'A';
	karakterT[2] = 'P';

	int ossz = 0;
	for (int i = 0; i < karakterT.Length; i++)
	{
		ossz += karakterT[i];
	}

	// stringgel ugyan ez
	string karakterek = "PAP";
	int ossz2 = 0;
	for (int i = 0; i < karakterek.Length; i++)
	{
		ossz2 += karakterek[i];
	}
	Console.WriteLine(ossz2); // számot-->255

	// karaktertömbből stringet gyártani, ez már összefűzés, konkatenáció
	// futtatsd le, nézd meg mit ír ki
	char[] amibol = new char[] { 'P', 'A', 'P' };
	string amibe = "";
	for (int i = 0; i < amibol.Length; i++)
	{
		amibe += amibol[i]; // konkatenáció, összefűzés
	}
	Console.WriteLine(amibe); //szöveget--->PAP
}

private static void matrixIsm()
{
	int[,] matrix = new int[3, 3]; // 3 sor 3 oszlop
	// töltsük fel [1,10] random számokkal
	Random r = new Random();
	for (int i = 0; i < matrix.GetLength(0); i++) // sorokat pörgeti végig, azaz a vektorokat
	{
		for (int j = 0; j < matrix.GetLength(1); j++) // egy-egy vektor elemein megy végig (oszlop)
		{
			matrix[i, j] = r.Next(10)+1; // [1,10]
			Console.Write($"{matrix[i,j],5}");
		}
		Console.WriteLine(); // segít abban hogy táblázatos alakban jelenjen meg
	}
}

private static void vektorokIsm()
{
	// [0,10]-ban töltsük fel az
	// 5 elmű int tömbünket, majd írassuk ki
	// EGY sorban az értékeit
	Random r = new Random();
	int[] tomb = new int[5];
	for (int i = 0; i < tomb.Length; i++)
	{
		tomb[i] = r.Next(11);
		Console.Write($"{tomb[i],5}");
	}
	for (int i = 1; i <= 10; i++) Console.WriteLine(); // dinamikusan készítettünk 10 sortörést is :D
	
}

/// <summary>
/// ez egy nagyon szuper metódus használd nyugodtan
/// </summary>
private static void ismetles()
{
	// tömbök előnye h nem kell 3 értékhez három változót léltre hoznom
	// hanem használhatok tömböt is, segít abban hogy egy változóban le tudjak
	// hivatkozni tetszőleges hosszúságú éréket
	int sz1 = 6;
	int sz2 = 7;
	int sz3 = 5;

	int[] tomb = new int[3];
	// ha primitív típusú a tömb alapból a memóriában 0 értékekkel töltődik fel
	// primitív típsu: int, double, char, bool
	for (int i = 0; i < tomb.Length; i++)
	{
		Console.WriteLine(tomb[i]);
	}
}
```