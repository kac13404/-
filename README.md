Задача: Написать программу, которая из имеющегося массива строк формирует новый массив из строк, длина которых меньше, либо равна 3 символам. Первоначальный массив можно ввести с клавиатуры, либо задать на старте выполнения алгоритма. При решении не рекомендуется пользоваться коллекциями, лучше обойтись исключительно массивами.

Примеры:
1. [“Hello”, “2”, “world”, “:-)”] → [“2”, “:-)”]
2. [“1234”, “1567”, “-2”, “computer science”] → [“-2”]
3. [“Russia”, “Denmark”, “Kazan”] → []

Решение:
1. Просим пользователя ввести количество элементов массива:
```HTML
Console.Write("Введите количество элементов массива: ");
int array1 = Convert.ToInt32(Console.ReadLine());
string[] stringArray = new string[array1];
```
2. Просим пользователя ввести сами элементы массива:
```HTML
void array(string[] stringArray)
{
    for (int i = 0; i < stringArray.Length; i++)
    {
        Console.WriteLine($"Введите {i + 1} элемент массива");
        stringArray[i] = Console.ReadLine();
    }
}
```
3. Производится перебор элементов массива, где отбирается элемент <= 3 символам:
```HTML
string[] symbol(string[] stringArray)
{
    int n = 0;
    for (int i = 0; i < stringArray.Length; i++)
    {
        if (stringArray[i].Length <= 3)
            n++;
    }
    string[] rez = new string[n];
    int j = 0;
    for (int i = 0; i < stringArray.Length; i++)
    {
        if (stringArray[i].Length <= 3)
        {
            rez[j] = stringArray[i];
            j++;
        }
    }
    return rez;
}
```
4. Вывод результата:
```HTML
void printA(string[] stringArray)
{
    Console.Write("[");
    for (int i = 0; i < stringArray.Length; i++)
    {
        Console.Write($"'{stringArray[i]}', ");
    }
    Console.Write("]");
}
array(stringArray);
printA(symbol(stringArray));
```
