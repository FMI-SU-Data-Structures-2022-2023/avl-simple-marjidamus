[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-f4981d0f882b2a3f0472912d15f9806d57e124e0fc890972558857b51b24a6f9.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=9677314)
# Балансиране на дървета... и как това ни помага...

## Преди това обаче, какъв е генералният проблем ако не го правим

## Да се завърти дърво наляво
## Да се завърти дърво надясно

## А има ли други възможности за ротация?

## Да се имплементира AVL дърво



## СДП Авгурст месец 2022г.

Елементите на двоично дърво представяме чрез структури от вида:

struct node {
   int data;   // Стойност съхранена в елемента
   node* left; // Ляв наследник или nullptr, ако няма такъв
   node* right; // Десен наследник или nullptr, ако няма такъв
};
За определеност в задачата ще считаме, че в едно двоично наредено дърво елементите се нареждат така, че отляво на всеки възел има по-малки от него елементи, а вдясно -- по-големи или равни. Също, че може да има повторения .

Реализирайте дадените по-долу функции. Погрижете се да няма изтичане на памет, а също и за случая, в който заделянето на памет не успее.

А) node* toTree(const int* sorted_data, size_t size)
Получава сортиран в нарастващ ред масив sorted_data съдържащ size на брой числа. Създава балансирано по тегло двоично наредено дърво, в което са записани елементите на масива. Елементите на дървото да се заделят с new. Връща като резултат корена на дървото. Ако на функцията се подаде празен масив, да връща като резултат nullptr. Сложността да бъде не повече от O(size).

Б) void release(node* tree)
Освобождава паметта заета от елементите на дървото с корен tree. Изтриването да става с delete.

В) size_t toArray(node* tree, int* output)
Получава указател към корена на двоично наредено дърво. Записва елементите на дървото в масива output така, че да са сортирани в нарастващ ред. Това трябва да се получи чрез подходящо обхождане на дървото. В решението НЕ МОЖЕ да се използва отделно сортиране на масива. Функцията да връща броя на елементите, които е записала в output. Може да считате, че в output ще има поне толкова място, че да може в него да се съберат елементите на дървото.

Г) main
Демонстрирайте работата на функциите в кратка програма, която:

Създава примерен сортиран масив sample и го извежда на екрана.
Преобразува sample до двоично наредено дърво.
Преобразува дървото обратно до нов масив result
Извежда result на екрана.
