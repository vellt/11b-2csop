```c#
static void Main(string[] args)
{
	// printeljük ki, mit látunk?
	int sz1 = 65;
	int sz2 = 76;
	int sz3 = 77;
	int sz4 = 65;
	Console.WriteLine($"{sz1} {sz2} {sz3} {sz4}");

	// és most?
	Console.WriteLine($"{(char)sz1} {(char)sz2} {(char)sz3} {(char)sz4}");

	// az 'a' kódbeli értéke (ASCII kódtáblabeli azonosítója-->dec)
	Console.WriteLine((int)'a'); // 97
	// az 'A' kódbeli értéke (ASCII kódtáblabeli azonosítója-->dec)
	Console.WriteLine((int)'A'); // 65
	// mi van akkor ha az 'a', azaz 97-ből, 32-t elveszünk? Pontosan 65-t kapunk-->A betű 
	Console.WriteLine((char)('a'-32)); // A

	// A kisbetűs angolszász abc kiíratása, ehhez meg kell keresni
	// az 'a' és a 'z' azonosítóját, amit korábban megtettünk
	for (int i = 97; i <= 122; i++)
	{
		Console.WriteLine((char)i);
	}

	// A nagybetűs angolszász abc kiíratása (32-vel eltolva kisbetűsöket kapunk)
	for (int i = 97 - 32; i <= 122 - 32; i++)
	{
		Console.WriteLine((char)i);
	}


	// szöveg (string) mint tömb -----------------------------------
	string beka = "beka";
	Console.WriteLine(beka.Length); // 4 <--szöveg hossza
	Console.WriteLine(beka[0]);// 'b' <--- az 1. indexet adja vissza
	Console.WriteLine((int)beka[0]);// 98-as indexű ASCII kód

	// Kérd be a neved kisbetűsen, és alakítsd át nagybetűssé
	Console.WriteLine("Add meg a neved");
	string nev = Console.ReadLine();
	for (int i = 0; i < nev.Length; i = i + 1)
	{
		Console.Write((char)(nev[i] - 32)); // -32-el eltolva nagybetűset kapunk
	}
	Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott név után tesz egy sortörést


	// A bekért szöveg összes magánhangzóját alakítsuk át i-betűvé
	Console.WriteLine("Adj meg egy szöveget");
	string szoveg = Console.ReadLine();
	for (int i = 0; i < szoveg.Length; i++)
	{

		if (
			szoveg[i] == 'a' ||
			szoveg[i] == 'e' ||
			szoveg[i] == 'u' ||
			szoveg[i] == 'o'
			)
		{
			Console.Write('i'); // az magánhangzók helyére i-betűt
		}
		else
		{
			Console.Write(szoveg[i]); // minden másra az eredeti betűt íratjuk ki
		}
	}

	// nem mindegy a konstanst hogyan írjuk, meglehet nézni, hogy mi van akkor ha a szám körül
	// "" van vagy '' vagy pedig nincs semmi vagy pedig a szám után egy .0 van, ezek mind mást típust eredményeznek
	Console.WriteLine('6'.GetType()); // char
	Console.WriteLine("6".GetType()); // string
	Console.WriteLine(6.GetType()); // int
	Console.WriteLine(6.0.GetType()); // double

	// A bekért szöveg minden második karakterét írjuk ki
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (i % 2 != 0)
		{
			Console.Write(szoveg[i]);
		}
		
	}
	Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott név után tesz egy sortörést


	// A bekért szöveget az 5. karaktertöl írjuk ki
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (i >= 5)
		{
			Console.Write(szoveg[i]);
		}

	}
	Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott név után tesz egy sortörést

	// A bekért szöveget vizsgáljuk meg, hogy van-e benne 't' karakter
	for (int i = 0; i < szoveg.Length; i++)
	{
		if (szoveg[i] == 't')
		{
			Console.WriteLine("van benne t");
		}
	}
   

	// legyen egy valami változónk amelyben az összes magánhangzót alakítsuk át i-betűssé
	string valami = "kerekpar"; // pl kerekpar-->kirikpir
	for (int i = 0; i < valami.Length; i++)
	{
		if(
			valami[i] == 'a' ||
			valami[i] == 'e' ||
			valami[i] == 'o' ||
			valami[i] == 'u'
		  )
		{
			Console.Write("i");  // az magánhangzók helyére i-betűt
		}
		else
		{
			Console.Write(valami[i]);  // minden másra az eredeti betűt íratjuk ki
		}
	}
	Console.WriteLine(); // erre azért van szüksége mert igy végül a kiíratott név után tesz egy sortörést



	// konzolos függvények, metódusok--------------------------------------------------------------------------
	
	// az ablak címét be lehet állítani
	Console.Title = "ez az én appom";
	
	// be lehet állítani a konzol méretét is
	Console.SetWindowSize(50, 50);
	
	// be lehet állítani a háttér színét
	Console.BackgroundColor = ConsoleColor.Blue;
	// mivel a ConsoleColor az egy Enum típus, ezért számmal is le lehet hivatkozni
	// (Az enum típus egy felsorolás típus más szóval, így minden egyes eleme számként is lehivatkozható)
	Console.BackgroundColor = (ConsoleColor)9; // ezzel ugyan úgy kékre állítja a háttérszínt, mert a blue értéke a felsorolás típusban 9-es. Ez megtekinhető egyébként ha rákattulunk a ConsoleColorral Ctrl lenyomásával
	// ConsoleColor enum elemei:
	/*
		public enum ConsoleColor
		{
			Black = 0,
			DarkBlue = 1,
			DarkGreen = 2,
			DarkCyan = 3,
			DarkRed = 4,
			DarkMagenta = 5,
			DarkYellow = 6,
			Gray = 7,
			DarkGray = 8,
			Blue = 9,
			Green = 10,
			Cyan = 11,
			Red = 12,
			Magenta = 13,
			Yellow = 14,
			White = 15
		}
	 */

	// sipoltatás
	// Console.Beep(frekvencia, időtartam);
	for (int i = 1; i <= 10; i++)
	{
		Console.Beep(400+(i*400), 1000); // folyamatosan növeli a hangtartományt (frekvenciát)
		System.Threading.Thread.Sleep(200); // 2 ms késleltetés
	}

	//minden egyes gomb lenyomásra lekérjük, hogy milyen karaktert tárol a gomb
	// most már tudjuk, hogy minden karakternek van ASCII kódbeli értéke
	// ahhoz minden kattintáskor hozzá adunk egy 1000-s értéket, így kapunk egy A-betű lenyomásakor 1097-es értéket
	// amit megszólaltatunk
	for (; true;) // végtelen ciklus, mindig igaz, nincs kilépő feltételünk
	{
		char karakter = Console.ReadKey().KeyChar;
		Console.Beep(karakter+1000, 1000);
	}

	// Másodpercenként változtatjuk a háttér szinét, kihaszálva azt a tényt, hogy az enum értékek számmal is helyettesíthetőek
	// az i mindig egy uj indexet ad vissza, és 15-ig megy, ennyi ConsoleColor elem van
	for (int i = 0; i <= 15; i++)
	{
		Console.BackgroundColor = (ConsoleColor)i;
		Console.WriteLine("hello");
		System.Threading.Thread.Sleep(1000);

		Console.Clear(); // törli az eddigi képernyő tartalmat
	}
	
	// zöld szövegszín
	Console.ForegroundColor = ConsoleColor.Green;
	Console.WriteLine("ez egy zöld szinű szöveg");

	// vissza állítja a szinbeállításokat az eredetire
	Console.ResetColor();
	
	// tömb---------------------------------------------------------------------------------
	
	// tömb szintaxisa
	// típus [] tombnevet = new típus [tömb hossza (elemszám)];

	// 6 elemű tömb, ami 6db int típust tárol
	int[] szamok = new int[6];

	// írtunk egy metódust (szamokKiiratasa) amelynek átadjuk a 'szamok'
	// tömböt paraméterként, majd ott körbe járja és kiíratja a tömb tartalmát
	szamokKiiratasa(szamok);

	// írtunk egy függvényt (szamokFeltoltese), amelynek az a feladata,
	// hogy a 'szamok' tömbnek értékül adjon egy [10,19] random számokkal
	// elkészített tömböt
	szamok = szamokFeltoltese();

	// újrahasznosítás, mivel az előző feladatrészben készítettünk egy tömböt,
	// amit feltöltöttünk különféle értékekkel, azt jó lenne megint kiíratni
	// tehát paraméterül, újra átadom a 'szamok' tömböt, és a metódus kiíratja minden elemét
	szamokKiiratasa(szamok);

	
	Console.ReadKey();
}

// egy függvény, amelynek nincs paramétere, viszont visszatérési értéke egy int[] típus,
// amivel kötlező visszatérnie, feladata, hogy feltölt egy temp tömböt random számokkal, 
// majd azzal a return kulcsszó segítségével visszatér
static int [] szamokFeltoltese()
{
	int[] temp = new int[6];
	Random r = new Random();
	for (int i = 0; i < temp.Length; i++)temp[i] = r.Next(10) + 10;
	return temp;
}

// egy metódus, amelynek van egy paramétere, amely int[] típust vár kötelezően
// feladata, hogy körbejárja a paraméterként kapott valtozó tartalmát
static void szamokKiiratasa(int[] szamok)
{
	for (int i = 0; i < szamok.Length; i++) Console.WriteLine(szamok[i]);
}
```