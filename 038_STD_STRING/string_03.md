#### Aşağıdaki işlevleri tanımlayınız ve kendi yazacağınız test kodu (kodları) ile test ediniz:

```
std::string opposite_case(const std::string &s);
```

işlev parametresi ile aldığı yazıdaki 
 + küçük harflerin yerinde aynı karakterlerin büyüğü olan
 + büyük harflerin yerinde aynı karakterlerin küçüğü olan

bir string döndürecek.

```
std::string remove_chars(const std::string &source, const std::string &scars);

```

İşlevin geri dönüş değeri olan *string*'in değeri source *string*'i içinden *scars* stringinin karakterlerinin silinmiş hali olacak.
<br>Örnek (parantezler yazılara dahil değil)

*source*           : (ankaranin tasina bak gozlerimin yasina bak) <br>
*scars*            : (kain ) <br>
*geri dönüş değeri*: (rtsbgozlermysb)

```
std::string trim(const std::string &source);
```

işlevin geri dönüş değeri olan string source stringinin başındaki ve sonundaki boşluk karakterlerinin silinmiş hali olacak:

```
(     necati ergin     )  ->  (necati ergin)
```

parantezler yazıya ait değil.

```
//işlev parametresi ile aldığı yazıdaki
//
//küçük harflerin yerinde aynı karakterlerin büyüğü olan
//büyük harflerin yerinde aynı karakterlerin küçüğü olan
//bir string döndürecek.
#include <string>
#include <iostream>
#include<cctype>

using namespace std;
string s{ "mursitKOC" };

std::string opposite_case(std::string& s)
{
	for (auto idx = s.begin(); idx <= s.end(); idx++)
	{
		isupper(*idx) ? *idx = tolower(*idx) : *idx = toupper(*idx);
	}
	return s;
}

int main()
{
	cout << opposite_case(s);
}
```

```
//İşlevin geri dönüş değeri olan string'in değeri source string'i içinden scars stringinin karakterlerinin silinmiş hali olacak.
//Örnek(parantezler yazılara dahil değil)
//
//source : (ankaranin tasina bak gozlerimin yasina bak)
//scars : (kain)
//geri dönüş değeri : (rtsbgozlermysb)
#include <string>
#include <iostream>
#include<cctype>

std::string source{ "ankaranin tasina bak gozlerimin yasina bak" };
std::string scars{ "kain" };

std::string remove_chars(const std::string& source, const std::string& scars)
{
	std::string temp{};
	for(size_t pos = 0; pos<source.size(); ++pos)
	{
		if (auto t = source.find_first_not_of(scars,pos); t != source.npos&&source[t]!=' ') {
			temp.push_back(source[t]);
			pos = t;
		}
	}
	return temp;
}

int main()
{
	std::cout << remove_chars(source,scars);	
}
```


```
//işlevin geri dönüş değeri olan string source stringinin başındaki ve 
//sonundaki boşluk karakterlerinin silinmiş hali olacak :
//(			necati ergin	)  ->  (necati ergin)
#include <string>
#include <iostream>
#include<cctype>

using namespace std;

std::string source{ "			necati ergin	" };

std::string trim(const std::string& source)
{
	string temp{ source };
	while (temp.front() == ' ' || temp.back() == ' ' || temp.front() == '\t' || temp.back() == '\t')
	{
		if (temp.back() == ' ' || temp.back() == '\t') temp.pop_back();
		if (temp.front() == ' ' || temp.front() == '\t') temp.erase(0, 1);
	}
	return temp;
}

int main()
{
	std::cout << trim(source);
}
```
