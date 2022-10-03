#### Aşağıdaki C++ programı hakkında yorum yapınız

+ sentaks hatası var ise, hatayı ve hatanın nedenini belirtiniz.
+ tanımsız davranış var ise nedenini belirtiniz.
+ standart çıkış akımına ne yazdırılacağını belirtiniz.


```
//prog6.cpp

#include <iostream>

int main()
{
	int a[] = { 10, 20, 30, 40 };
	auto p = a;
	auto &r = p;
	++r;
	++p;

	std::cout << *r << "\n";
	
}
```
