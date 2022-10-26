#### *filename* isimli *std::string* nesnesi bir dosyanın ismini tutuyor. Aşağıdaki işlemleri gerçekleştirecek kodları yazınız.

+ Dosyanın uzantısı yok ise uzantısı *.jpg* olsun.  *(hasan) -> (hasan.jpg)*
+ Dosyanın uzantısı *".gif"* ise uzantısını *".png"* olarak değiştirin.  *(necati.gif) -> (necati.png)*
+ Dosyanın uzantısı *".xls"* ise uzantısını silin. *(aleyna.xls) -> (aleyna)*

```
//#### *filename* isimli *std::string* nesnesi bir dosyanın ismini tutuyor. 
//Aşağıdaki işlemleri gerçekleştirecek kodları yazınız.

//Dosyanın uzantısı yok ise uzantısı * .jpg * olsun. * (hasan) -> (hasan.jpg) *
#include <string>
#include <iostream>
#include<algorithm>

using namespace std;
string file{ "hasan" };

int main()
{
	if (file[file.size() - 4] != '.')
	{
		file.append(".jpg");
	}

	cout << file;	
}
```
```
//#### *filename* isimli *std::string* nesnesi bir dosyanın ismini tutuyor. 
//Aşağıdaki işlemleri gerçekleştirecek kodları yazınız.

//+ Dosyanın uzantısı *".gif"* ise uzantısını *".png"* olarak değiştirin.  *(necati.gif) -> (necati.png)*
#include <string>
#include <iostream>
#include<algorithm>

using namespace std;
string file{ "hasan.gif" };

int main()
{
	if (file.ends_with(".gif"))
	{
		file.replace(file.size()-4,4,".png");
	}

	cout << file;	
}
```
```
//#### *filename* isimli *std::string* nesnesi bir dosyanın ismini tutuyor. 
//Aşağıdaki işlemleri gerçekleştirecek kodları yazınız.

//+ Dosyanın uzantısı *".xls"* ise uzantısını silin. *(aleyna.xls) -> (aleyna)*
#include <string>
#include <iostream>
#include<algorithm>

using namespace std;
string file{ "hasan.xls" };

int main()
{
	if (file.ends_with(".xls"))
	{
		int n = 4;
		while (n--)
		{
			file.pop_back();
		}
	}

	cout << file;	
}
```
