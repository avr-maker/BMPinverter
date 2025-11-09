


## OpenBMP

Изучаем как работают `.bmp` файлы.

**Чтобы подключить файл:**
```cpp
#include "obmp.h"
```

**Пример работы программы:**
```cpp
OpenBMP obmp = OpenBMP(argv[1]);
std::cout << "Shape(y, x): " << obmp.shape();

obmp.mirror("vertical");
OpenBMP other = obmp.rgb2gray();

obmp.save("object.bmp");
other.save("other.bmp");
```

Реализованные методы:

| Название метода | Описание |
|----|----|
|`std::pair<int, int> shape`| возвращает размерность изображения в формате `(height, width)`|
|`void invert(const std::string& method)`|Инвертирование изображения. Принимает параметр `method` = `arithmetic` или `method` = `bitwise_not`|
|`OpenBMP arith_invert()`|арифметическое инвертирование с созданием нового объекта|
|`OpenBMP bitwise_not()`|побитовое инвертирование изображения с созданием нового объекта|
|`void grayscale()`|переводим изображение в grayscale|
|`OpenBMP rgb2gray()`|создаем новый объект из текущего изображения в grayscale|
|`void mirror(const std::string& method)`|Отзеркалить изображение.  Принимает параметр `method` = `vertical`|
|`void save(const std::string& filename)`|Сохранить изображение в файл `filename`|
