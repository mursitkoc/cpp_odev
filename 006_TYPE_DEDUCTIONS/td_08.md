#### Aşağıdaki C++ programı hakkında yorum yapınız

+ sentaks hatası var ise, hatayı ve hatanın nedenini belirtiniz.
+ tanımsız davranış var ise nedenini belirtiniz.
+ standart çıkış akımına ne yazdırılacağını belirtiniz.


```
//prog4.cpp

#include <iostream>

int main()
{
	int x = 10;
	const int &cr = x;
	auto &r = cr;
	++r;

	std::cout << "x = " << x << "\n";
}
```
