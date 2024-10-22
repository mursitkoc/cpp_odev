#### Bir std::string nesnesi üzerinde aşağıdaki silme işlemlerini gerçekleştirmeniz gerekiyor:

01. Yazının ilk karakterini silin.
02. Yazının son karakterini silin.
03. Yazının ilk ve son karakterleri dışında tüm karakterlerini silin.
04. Yazının ikinci karakterini silin.
05. Yazının sondan ikinci karakterini silin.
06. idx yazının geçerli bir indeksi olmak üzere yazının *idx* indisli karakterini silin.
07. Yazıdaki ilk *a* karakterini silin.
08. Yazıdaki son *a* karakterini silin.
19. Yazıdaki tüm *a* karakterlerini silin.
10. Yazıdaki ilk *a* karakteri ile başlayan ve son *a* karakteri ile biten yazıyı silin.
11. Yazıdaki ilk *a* karakterinden önce gelen ve sonra gelen *2* karakteri silin.
12. Yazıda bulunan ilk *"kan"* yazısını silin
13. Yazıda bulunan son *"kan"* yazısını silin
14. Yazıda bulunan tüm *"kan"* yazılarını silin
15. Yazıda bulunan ilk rakam karakterini silin
16. Yazıda bulunan son rakam karakterini silin
17. Yazıdaki tüm rakam karakterlerini silin.
18. Yazının uzunluğu 1'den büyükse ve yazının ilk karakteri ile son karakteri aynı ise bunları silin.
19. Yazının uzunluğu 5'ten büyükse ve yazının ilk *3* karakteri ile son *3* karakteri aynı ise bunları silin.
20. Yazıdaki ardışık eşit karakterlerden sadece bir tane kalacak şekilde silme işlemi yapın. *(unique)*
21. Yazıdaki tüm boşluk *(whitespace)* karakterlerini silin.

**Aşağıdaki test kodunu kullanabilirsiniz:**

```
#include <string>
#include <iostream>

void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}

int main()
{
	std::string s{ "aslan kan sever kan olmazsa et sever kan olmasa bir et yer" };


	
	print(s);
	//kod
	print(s);
}


```
```
#include <string>
#include <iostream>

void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}

int main()
{
	std::string s{ "aslan kan sever kan olmazsa et sever kan olmasa bir et yer" };


	
	print(s);
	//kod
	print(s);
}


```
```
//13.
#include <string>
#include <iostream>

void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}

int main()
{
	std::string s{ "aslan kan sever kan olmazsa et sever kan olmasa bir et yer" };

	print(s);
	s.erase(s.rfind("kan"),3);
	print(s);
}
```
```
//14.
#include <string>
#include <iostream>

void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}

int main()
{
	std::string s{ "aslan kan sever kan olmazsa et sever kan olmasa bir et yer" };

	print(s);
	while (s.npos != s.find("kan"))
	{
		s.erase(s.find("kan"), 3);
	}
	print(s);
}
```
```
//15.
#include <string>
#include <iostream>

void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}

int main()
{
	std::string s{ "aslan kan sever kan olmazsa 5 et sever kan7 olmasa bir et yer" };
	
	print(s);
	s.erase(s.find_first_of("1234567890"),1);
	print(s);
}
```
```
//16. Yazıda bulunan son rakam karakterini silin
#include <string>
#include <iostream>

void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}

int main()
{
	std::string s{ "aslan kan sever kan olmazsa 5 et sever kan7 olmasa bir et yer" };
	
	print(s);
	s.erase(s.find_last_of("1234567890"),1);
	print(s);
}
```
```
//17.Yazıdaki tüm rakam karakterlerini silin.
#include <string>
#include <iostream>

void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}

int main()
{
	std::string s{ "aslan kan sever kan olmazsa 5 et sever kan7 olmasa bir et yer" };
	
	print(s);
	while (s.find_first_of("1234567890") != s.npos)
	{
		s.erase(s.find_last_of("1234567890"), 1);
	}
	print(s);
}
```
```
//18. Yazının uzunluğu 1'den büyükse ve yazının ilk karakteri ile son karakteri aynı ise bunları silin.
#include <string>
#include <iostream>

using namespace std;
void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}
//aslan kan sever kan olmazsa 5 et sever kan7 olmasa asla
int main()
{
	std::string s{ "asla" };
	
	print(s);
	
	if (s.length() > 1 && *(s.begin()) == *(s.end() - 1))
	{
		s.pop_back();
		s.erase(0,1);
	}
	print(s);
}
```
```
//19. Yazının uzunluğu 5'ten büyükse ve yazının ilk *3* 
//karakteri ile son *3* karakteri aynı ise bunları silin.
#include <string>
#include <iostream>

using namespace std;
void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}
//aslan kan sever kan olmazsa 5 et sever kan7 olmasa asla
int main()
{
	std::string s{ "asla a asl" };
	
	print(s);
	
	if (s.substr(0,3)==s.substr(s.size()-3,3))
	{
		s.erase(0,3);
		s.erase(s.size() - 3, 3);
	}
	print(s);

}
```
```
//20. Yazıdaki ardışık eşit karakterlerden sadece bir tane kalacak şekilde silme işlemi yapın. *(unique)*
#include <string>
#include <iostream>
#include<algorithm>

using namespace std;
void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}
//aslan kan sever kan olmazsa 5 et sever kan7 olmasa asla
int main()
{
	std::string s{ "aassaassaassaassaassaassaassaasshaklakıyesnsjk" };
	
	print(s);
	
	// remove consecutive (adjacent) duplicates
	auto last = unique(s.begin(), s.end());
	// s now holds {1 2 1 3 4 5 4 x x x}, where 'x' is indeterminate
	s.erase(last, s.end());
	print(s);

}
```
```
//21. Yazıdaki tüm boşluk (whitespace) karakterlerini silin.
#include <string>
#include <iostream>
#include<algorithm>

using namespace std;
void print(const std::string& s)
{
	std::cout << "'" << s << "' [" << s.length() << "]\n";
}

int main()
{
	std::string s{ "aslan kan sever kan olmazsa 5 et sever kan7 olmasa asla" };
	
	print(s);

	for (auto idx = s.begin(); idx < s.end(); ++idx)
	{
		if (*idx == ' ')
			s.erase(idx);
	}

	print(s);
}
```
