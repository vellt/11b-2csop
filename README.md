```c#
// tömbök előnye, hogy nem kell rengeteg változót létrehoznom, hanem egy
// változóban letudok tárolni mindent, csak egy mutatóval [index] lehivatkozom
// az adott elemét. Ez a mutató/index 0-tól a tömb.Length-1ig tud lehivatkozni 
// tömbbéli elemeket
int sz1 = 12;
int sz2 = 33;
int sz4 = 12;

// int tömb létrehozása. KÖTELEZŐ megadni a tömb hosszát
int hossz = 3;
int[] tomb = new int[hossz];
// így tudunk egy-egy elemét lehivatkozni
tomb[0] = 12;
tomb[1] = 33;
tomb[2] = 12;

// az előző hivatkozást megtehetjük dimanikusabban is for ciklussal
// 0-tól meg 3ig, amit vagy a hossz változóval kapunk meg vagy a 
// tomb.Length-1el
for (int i = 0; i < hossz; i++)
{
	// dinamikusan feltöltjük a tömb minden elemét konzolból
	tomb[i] = Convert.ToInt32(Console.ReadLine());
}


// Ha létre hozunk egy tömbböt, alapértelmezetten nullákkal tölti fel minden elemét
// primitív típus: int, double, bool, char
// összetett típus: string, ez referenciát tárol kicsit másképpen működik

// hozzunk létre egy 5 elemű string tömbböt és töltsük fel
// konzolból bekért ruhaneműkkel
string[] szekreny = new string[4];
for (int i = 0; i < szekreny.Length; i++)
{
	Console.Write("helyezd a szekrénybe: ");
	szekreny[i] = Console.ReadLine();
}
// majd ha feltöltöttük kiíratjuk a ruhásszekrény tartalmát
Console.WriteLine("szekrény tartalma:");
for (int i = 0; i < szekreny.Length; i++)
{
	Console.WriteLine($"- {szekreny[i]}");
}

// mátrix/két dimenziós tömb--------------------------------------------

int[,] matrix = new int[5,6];
// GetLength(0)-->5, azaz mennyi vektorból/1dim tömbböl épül fel a mátrix
// GetLength(1)-->6, azaz mennyi elemű egy egy vektora/1dim tömbje

// töltsük fel az elkészített mátrixot [-10,10]-es intervallumú számokkal
Random r = new Random();
for (int i = 0; i < matrix.GetLength(0); i++)
{
	for (int j = 0; j < matrix.GetLength(1); j++)
	{
		matrix[i, j] = r.Next(21)-10; //[-10, 10]
	}
}
// kiíratjuk a mátrix tartalmát ügyelve annak mátrixos nézetére
for (int i = 0; i < matrix.GetLength(0); i++)
{
	for (int j = 0; j < matrix.GetLength(1); j++)
	{
		Console.Write($"{matrix[i, j]}\t");
	}
	Console.WriteLine();
}
Console.WriteLine(matrix[0, 1]); // 0. sor, 1. oszlop
// 1. indexű sor 3. indexű elemét hivatkozom le (bal felső sarokban kezdem a számolást)
Console.WriteLine(matrix[1, 3]);

// hozzunk létre egy n elemű int tömbböt, az n értékét kérje be konzolból
// majd töltsük fel [50,100]-es intervallumban lévő számokkal
int darabSzam = Convert.ToInt32(Console.ReadLine());
int[] randomTomb = new int[darabSzam];
Random r = new Random();
for (int i = 0; i < randomTomb.Length; i++)
{
	randomTomb[i] = r.Next(51)+50; //50,100
}
// majd írassuk ki egymás mellé az értékeket tabulátorokkal elválasztva
for (int i = 0; i < randomTomb.Length; i++)
{
	Console.Write($"{randomTomb[i]}\t");
}

// töltsünk fel egy 5 elemű tömböt konzolról bekért számokkal
Console.WriteLine("tömb feltöltés");
int[] tomb = new int[5];
for (int i = 0; i < tomb.Length; i++)
{
	Console.Write($"{i+1}. szám: ");
	tomb[i] =Convert.ToInt32(Console.ReadLine());
}
// majd számoljuk meg, hogy mennyi pozitív és mennyi negatív szám van benne
int pozitivSzamlalo = 0;
int negativSzamlalo = 0;
for (int i = 0; i < tomb.Length; i++)
{
	if (tomb[i] >= 0) pozitivSzamlalo++;
	else negativSzamlalo++;
}
Console.WriteLine($"Ennyi pozitív: {pozitivSzamlalo}");
Console.WriteLine($"Ennyi pozitív: {negativSzamlalo}");


// 5 elemű int tömböt töltsünk fel [10,50] intervallumban véletlenszerűen
// legnagyobb és legkisebb érték?
int[] tomb2 = new int[5];
Random random = new Random();
// feltöltöttük [10,50] intervallumbéli számokkal
for (int i = 0; i < tomb2.Length; i++)
{
	tomb2[i] = random.Next(41)+10;
}
// kiírattuk a tömb tartalmát egymás mellé szóközökkel elválasztva
for (int i = 0; i < tomb2.Length; i++)
{
	Console.Write($"{tomb2[i]} ");
}
Console.WriteLine();
// megkerestük a legkisebbet és a legnagyobbat
int max = tomb2[0];
int min = tomb2[0];
for (int i = 0; i < tomb2.Length; i++)
{
	// összevetem hogy vajon a jelenlegi maximum értéktöl a tömb i. eleme nagyobb?
	// mert ha igen, akkor legyen az az új max érték
	if (max<tomb2[i])
	{
		max = tomb2[i];
	}
	// ugyan az a logika mint a max-nél, csak itt azt nézzük,
	// hogy az aktuális min-nél van-e kisebb a tömbben
	if (min > tomb2[i])
	{
		min = tomb2[i];
	}
}
// kiíratom a maximum értéket
Console.WriteLine(max);

Console.ReadKey();
```