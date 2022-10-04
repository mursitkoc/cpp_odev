#### Aşağıdaki C++ programı hakkında yorum yapınız:

+ sentaks hatası
+ tanımsız davranış
+ derleyiciye göre değişir
+ ekrana şunu yazar: 

```
#include <iostream>

int main() 
{
	int ival = 1;
	const int &r = ival > 0 ? ival : 1;
	ival = 5;
	std::cout << ival << r;
}
```

[ödev cevabı](https://vimeo.com/433201294)
