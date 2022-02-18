# SingleLinkedList

Реализация Single linked list.

# Использование
Для использования необходима установка и настройка требуемых компонентов.

Пример использования:
```
#include "single_linked_list.h"

#include <iostream>
#include <random>
#include <numeric>

int main() {
    SingleLinkedList<int> l{ 1, 2, 3, 4, 5, 6 };

    std::vector<SingleLinkedList<int>::Iterator> v(l.GetSize());
    std::iota(v.begin(), v.end(), l.begin());

    std::shuffle(v.begin(), v.end(), std::mt19937{ std::random_device{}() });

    std::cout << "Contents of the list: ";
    for (auto n : l) std::cout << n << ' ';
    std::cout << '\n';

    std::cout << "Contents of the list, shuffled: ";
    for (auto i : v) std::cout << *i << ' ';
    std::cout << '\n';
}
```
Больше примеров использования и тесты показаны в tests.cpp

# Системные требования

1. C++17 (STL)
2. GCC (MinGW-w64) 11.2.0

# Планы по доработке

1. Добавить возможность создание контейнера из определенного количества элементов, инициализированных значением определенным значением.
2. Добавить возможность создания пустого контейнера с определенным размером.
3. Реализовать методы std::list, не реализованные в контейнере.
