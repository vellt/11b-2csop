```c#
// egy 'C' karakterből kinyerni az ASCII beli értékét
char karakter = 'C';
Console.WriteLine((int)karakter);

// egy ASCII beli számból kinyerni a karakteres értékét
Console.WriteLine((char)67);

// hogyan alakítjuk át a kisbetűket nagybetűkké
// 1. lépés: meghatározom az 'a' értékét, és az 'A'
//           értékét, majd megnézem a kettő közötti
//           differenciát.
// 2. lépés: ha már tudom hogy -32-t kell elvonnom a kisbetűből
//           hogy nagy betűt kapjak, megtudom határozni,
//           hogy a-->A legyen
Console.WriteLine((int)'A');
Console.WriteLine((int)'a');
Console.WriteLine((char)('a'-32));

// hogyan tudom a szoveg változó 'a' elemét lehivatkozni?
string szoveg = "Kék az ég";
Console.WriteLine(szoveg[4]);
// hogyan tudom a szoveg változó első indexelhető elemét lehivatkozni?
Console.WriteLine(szoveg[0]);
// hogyan tudom a szoveg változó utolsó indexelhető elemét lehivatkozni?
Console.WriteLine(szoveg[szoveg.Length-1]);
Console.WriteLine(); // szeparálás miatt kell, hogy a következő kiíratás jobban elkülönüljön ettől

// (a-z) karaktereket egymás alá
//      (ha egymás mellé kiíratás lenne a feladat akkor 
//      Console.Write()-ot használunk)
for (int i = 'a'; i <= 'z'; i++)
{
	Console.WriteLine((char)(i-32));
}

//szoveg --> forditott sorrend, plusz hagyja el a szóközöket kiíratáskor
for (int i = szoveg.Length-1; i >= 0; i--)
{
	if(szoveg[i]!=' ')
		Console.Write(szoveg[i]);
}

// keressük meg, hogy melyik a legnagyobb
// (ASCII kód) értékű karakter 
szoveg = "EGKEKZA";
int max = 0;
for (int i = 0; i < szoveg.Length; i++) 
{
	int aktualisAscii = szoveg[i];
	if (max < aktualisAscii)
	{
		max = aktualisAscii;
	}
}
Console.WriteLine(max);

// kérj be egy nevet (vezeteknev keresztnev),
// majd képezz belőlle monogrammot, pl:
// kiss pista --> K.P.
Console.WriteLine("Adj meg egy kereszt és egy vezetéknevet(kisbetűkkel)");
string nev = Console.ReadLine();
Console.Write($"{ (char)(nev[0] - 32)}.");
for (int i = 0; i < nev.Length; i++)
{
	if (nev[i] == ' ')
	{
		Console.Write($"{ (char)(nev[i+1] - 32)}.");
	}
}
Console.WriteLine();

// A már bekért nevet tördeljük
// különböző sorokra szóközök mentén
// pl:
// John Doe --> John
//              Doe
for (int i = 0; i < nev.Length; i++)
{
	Console.Write(nev[i]);
	if (nev[i] == ' ')
	{
		Console.WriteLine();
	}
}
```