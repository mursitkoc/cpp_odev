#### Bir stringin başka bir *string*'in sola döndürülmüş hali olup olmadığını sınayan

```
#include <string>

bool is_lest_rotate(const std::string &s1, const std::string &s2);

```

#### işlevini tanımlayınız.

#### İşlev eğer *s2* stringi *s1* stringinin sola döndürülmesiyle elde edilebiliyorsa *true* değere aksi halde *false* değere geri dönmeli.


```
//İşlev eğer s2 stringi s1 stringinin sola döndürülmesiyle 
//elde edilebiliyorsa true değere aksi halde false değere geri dönmeli.
#include <string>
#include <iostream>
#include<cctype>

using namespace std;

const string s1{ "asla" };
const string s2{ "alsa" };

bool is_lest_rotate(const std::string& s1, const std::string& s2)
{
	string temp{s2};
	reverse(temp.begin(), temp.end());
	return temp == s1 ? true : false;
}


int main()
{
	std::cout << boolalpha << is_lest_rotate(s1, s2);
}
```
