```c#
/*
 összetett logikai kifejezések
if else-->switch
egy paraméteres randommal való műveletek
3 vagy több elem növekvő/csökkenő sorrendbe való rendezése
while/do while
 */

// mi az ami átalakítható switch-é

// ha olyat látunk egy if feltételben hogy ==

// az egyenlőségvizsgálat (==) jobb oldalán konstansnak kell lennie

// ha olyat látunk hogy egymás alatt if() if() if()... van az nem átalakítható
// case case case esetekként TELJES FUNKCIONALITÁSSAL

int ora = 10;
if (ora == 10)
{
	Console.WriteLine(10);
}
else if (ora == 11)
{
	Console.WriteLine(11);
} else
{
	Console.WriteLine("hat ilyen nincs");
}


switch (ora)
{
	case 10:
		Console.WriteLine(10);
		break;
	case 11:
		Console.WriteLine(11);
		break;
	default:
		Console.WriteLine("hat ilyen nincs");
		break;
}


// kövi
int a = 7;
int b = 8;
int c = 10;
if (a == b)
{
	Console.WriteLine("a és b egyenlő");
}else if (a == c)
{
	Console.WriteLine("a és c egyenlő");
}else
{
	Console.WriteLine("a nem egyenlő b-vel de c-vel sem");
}
// nem alakítható át, de azért felírom, a case-nél hibát mutat
switch (a)
{
	case b: //<-- nem tud a case változót kezelni
		Console.WriteLine("a és b egyenlő");
		break;
	case c:
		Console.WriteLine("a és c egyenlő");
		break;
	default:
		Console.WriteLine("a nem egyenlő b-vel de c-vel sem");
		break;
}

int a2 = 7;
int b2 = 8;
int c2 = 10;
if (a2 == 8)
{
	Console.WriteLine("a és b egyenlő");
}
else if (a2 == 10)
{
	Console.WriteLine("a és c egyenlő");
}
else
{
	Console.WriteLine("a nem egyenlő b-vel de c-vel sem");
}
// átalakítható, mert konstansok vannak a feltételben
switch (a2)
{
	case 8: 
		Console.WriteLine("a és b egyenlő");
		break;
	case 10:
		Console.WriteLine("a és c egyenlő");
		break;
	default:
		Console.WriteLine("a nem egyenlő b-vel de c-vel sem");
		break;
}

// kovetkezo

int vegosszeg = 10_000;
string kedvezmeny = "10%";
if (kedvezmeny == "10%") Console.WriteLine(vegosszeg*0.9);
else if (kedvezmeny == "20%") Console.WriteLine(vegosszeg*0.7);
else if (kedvezmeny == "50%") Console.WriteLine(vegosszeg*0.5);
else Console.WriteLine("nállunk nincs ilyen kedvezmény");
// átalakítható
switch (kedvezmeny)
{
	case "10%": Console.WriteLine(vegosszeg * 0.9); break;
	case "20%": Console.WriteLine(vegosszeg * 0.7); break;
	case "50%": Console.WriteLine(vegosszeg * 0.5); break;
	default: Console.WriteLine("nállunk nincs ilyen kedvezmény");break;
}

// kovi
int ora1 = 12;
int perc = 30;

if(ora1==10 && perc== 30)
{

	Console.WriteLine("Még van 2 órám");
}else if (ora == 12)
{
	Console.WriteLine("Még van fél órám");
}else
{
	Console.WriteLine("elkéstem");
}

// az első if-ben lévő perc változó miatt nem alakítható át
// a switch csak egy változónak az eseteit tudja vizsgálni

int erdemjegy = 5;
if (erdemjegy == 5)
{
	Console.WriteLine("Jeles");
}
if (erdemjegy == 4)
{
	Console.WriteLine("Jó");
}
if (erdemjegy == 3)
{
	Console.WriteLine("közepes");
}
// ez nem alakítható át teljes funkcionalitással
// mert nem else if-es csatolásban van

// igy már átalakítható lenne:
if (erdemjegy == 5)
{
	Console.WriteLine("Jeles");
}
else if (erdemjegy == 4)
{
	Console.WriteLine("Jó");
}
else if (erdemjegy == 3)
{
	Console.WriteLine("közepes");
}





// 3 random random számot kell generálni, [-100, 50]
// kiírni a generált értékéket
// csökkenőbe való rendezés
// kiíratni megint az értékeket

// mennyi a páratlan mennyi a páros

// mennyi a pozitív mennyi a negatív

// legkisebbet emeljük a négyzetre

Random random = new Random();
int szam1 = random.Next(151)-100;
int szam2 = random.Next(151)-100;
int szam3 = random.Next(151)-100;
Console.WriteLine($"{szam1} {szam2} {szam3}");
if(szam1 < szam2)
{
	// csere
	int temp = szam2;
	szam2 = szam1;
	szam1 = temp;
}
if(szam1 < szam3)
{
	// csere
	int temp = szam1;
	szam1 = szam3;
	szam3 = temp;
}
if (szam2 <szam3)
{
	// csere
	int temp = szam2;
	szam2 = szam3;
	szam3 = temp;
}
Console.WriteLine($"{szam1} {szam2} {szam3}");
// legkisebb szám négyzete
Console.WriteLine(Math.Pow(szam3,2));
Console.WriteLine(szam3*szam3);

// legkisebb/legnagyobb-->2tizedes
double hanyados = Convert.ToDouble(szam3) / szam1;
Console.WriteLine(Math.Round(hanyados, 2));
Console.WriteLine($"{hanyados:0.00}");

//ciklusok

// kérjen be 2 számot, és azok adataival 
// képezzen egy ciklust
// ami megmondja hogy mettől meddig léptesse 
// a ciklust
// kiíratni csak azokat a számokat írassuk ki
// amik párosak

Console.WriteLine("Add meg az x értékét");
int x = Convert.ToInt32(Console.ReadLine()); // kisebb

Console.WriteLine("Add meg az y értékét");
int y = Convert.ToInt32(Console.ReadLine()); // nagyobb

while (x!=y)
{
	if(x%2==0) Console.WriteLine(x);
	x++;
}

// 1-20 fut, kiírja minden szám négyzetét 
// 2-->4
int szamlalo = 1;
while (szamlalo!=21)
{
	Console.WriteLine($"{szamlalo}-->{Math.Pow(szamlalo,2)}");
	szamlalo++;
}

// 6%
// számolja ki az éves középhőmérséjkletet miután a felhasználótól
// bekérte az összes hónap átlag hőmérsékletét
int honap = 1;
int osszHomerseklet = 0;
while (honap != 13)
{
	int honapHomerseklete = Convert.ToInt32(Console.ReadLine());
	osszHomerseklet = osszHomerseklet + honapHomerseklete;
	honap++;
}
Console.WriteLine($"Az éves középhőmérséklet: {osszHomerseklet / 12.0}");
```