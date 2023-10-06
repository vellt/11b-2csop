```c#
//---------------------------------------------------------
// logikai operátorok:
// ==, !=, >, <, <=, >=, 
// logikai kapuk:
// AND (és): &&
// OR (vagy): ||
// NOT (negáció): !



bool logika = ((1>0) || (0==7) || (0<-1)); //true
bool negacio = !logika; // false;

/*
 * Írjunk egy kifejezést, amely azt ellenőrzi, hogy egy
 * adott szám páros ÉS pozitív is!
 */

Console.WriteLine("Add meg az x értékét:");
int x = Convert.ToInt32(Console.ReadLine());

if((x%2==0) && (x >= 0))
{
	Console.WriteLine($"Ez az {x} szám az páros és pozitív is");
}
else if ((x % 2 == 0) || (x >= 0))
{
	Console.WriteLine($"Ez az {x} szám vagy páros vagy pozitív");
}else if (!(x % 2 == 0) && !(x >= 0)){
	// ezek azok a számok, amik 0tól kissebbek
	// és práratlanok IS!
	Console.WriteLine($"Ez az {x} szám páratlan és negatív");
}


// alakítsuk át összetett logikai kifejezéssé
Console.WriteLine("Add meg az y értékét:");
int y = Convert.ToInt32(Console.ReadLine());

if (y > (16 % 2) && y < (((17 % 2) + 3) % 2) + (6 / 3))   //1 
{
	Console.WriteLine("FEJ");
}
//-1 -->Math.Pow(2,3)-9
// 1--->(Math.Sqrt(16)-3)
else if (y > (Math.Pow(2, 3) - 9) && y < (Math.Sqrt(16) - 3))  //0
{
	Console.WriteLine("ÍRÁS");
}

/*
 Írjunk egy kif, amely azt ellenőrzi, hogy egy szám osztható 3mal,
vagy 5-tel, de nem mindkettővel
 */

Console.WriteLine("Add meg az z értékét:");
int z = Convert.ToInt32(Console.ReadLine());
if (((z % 3 == 0) || (z % 5 == 0)) && !((z % 3 == 0) && (z % 5 == 0)))
{
	Console.WriteLine("A \"z\" egy olyan szám ami osztható 3mal és 5el, de nem mindkettővel");
} // A "z" egy olyan 

/*
 Írj egy kifejezést, amely azt ellenőrzi, hogy egy adott évszám szökőév-e. 
(Egy évszám szökőév, ha osztható 4-gyel, de nem osztható 100-zal)
 */
Console.WriteLine("Add meg az évszámot! megmondom h szökőév-e");
int evszam = Convert.ToInt32(Console.ReadLine());
if(evszam%4==0 && !(evszam % 100 == 0))
{
	Console.WriteLine("Igen, ez egy olyan évszám, amely szökőév");
}

//Switch-------------------------------------------------------------
Console.WriteLine("Add meg a 06 utáni telefonszámod: ");
string teloszam = Console.ReadLine();
if (teloszam.Length == 9)
{
	// valid telefonszám
	if (teloszam[0] == '3') Console.WriteLine("Telekom");
	else if (teloszam[0] == '2') Console.WriteLine("Yettel");
	else if (teloszam[0] == '7') Console.WriteLine("Vodafon");
	else if(teloszam[0] == '5') Console.WriteLine("Digi");
	else Console.WriteLine("Nem ismerem ezt a szolgáltatót");

	switch (teloszam[0]) //3
	{
		case '3': Console.WriteLine("Telekom"); break;
		case '2': Console.WriteLine("Yettel"); break;
		case '7': Console.WriteLine("Vodafon"); break;
		case '5': Console.WriteLine("Digi"); break;
		default: Console.WriteLine("Nem ismerem ezt a szolgáltatót"); break;
	}
}
else Console.WriteLine("nem valid telószám");

/*
	Írjunk egy programot, amely bekéri a hónap 
	számát (1-12), majd kiírja a hónap nevét
	a megadott szám alapján. If-else-->switch
 */
Console.WriteLine("Add meg a hónap számát!");
int honap = Convert.ToInt32(Console.ReadLine());
if (honap == 1) Console.WriteLine("Január");
else if (honap == 2) Console.WriteLine("Február");
else if (honap == 3) Console.WriteLine("Március");
else if (honap == 4) Console.WriteLine("Április");
else if (honap == 5) Console.WriteLine("Május");
else if (honap == 6) Console.WriteLine("Június");
else if (honap == 7) Console.WriteLine("Július");
else if (honap == 8) Console.WriteLine("Augusztus");
else if (honap == 9) Console.WriteLine("Szeptember");
else if (honap == 10) Console.WriteLine("Október");
else if (honap == 11) Console.WriteLine("November");
else if (honap == 12) Console.WriteLine("December");
else Console.WriteLine("Nincs ilyen hónap");

switch (honap)
{
	case 1: Console.WriteLine("Január"); break;
	case 2: Console.WriteLine("Február"); break;
	case 3: Console.WriteLine("Március"); break;
	case 4: Console.WriteLine("Április"); break;
	case 5: Console.WriteLine("Május"); break;
	case 6: Console.WriteLine("Június"); break;
	case 7: Console.WriteLine("Július"); break;
	case 8: Console.WriteLine("Augusztus"); break;
	case 9: Console.WriteLine("Szeptember"); break;
	case 10: Console.WriteLine("Október"); break;
	case 11: Console.WriteLine("November"); break;
	case 12: Console.WriteLine("December"); break;
	default: Console.WriteLine("Nincs ilyen hónap");break;
}

```