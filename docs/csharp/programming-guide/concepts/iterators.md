---
title: Procesar una iteración mediante colecciones en C#
description: Aprenda a usar un iterador para recorrer colecciones como listas y matrices. Los iteradores se consumen desde el código cliente mediante una instrucción foreach o una consulta LINQ.
ms.date: 08/14/2018
ms.assetid: c93f6dd4-e72a-4a06-be1c-a98b3255b734
ms.openlocfilehash: 310fff68a242812620357517c212ddd5f053775c
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104258"
---
# <a name="iterators-c"></a>Iteradores (C#)

Un *iterador* puede usarse para recorrer colecciones como listas y matrices.

Un método iterador o un descriptor de acceso `get` realiza una iteración personalizada en una colección. Un iterador usa la instrucción [yield return](../../language-reference/keywords/yield.md) para devolver cada elemento de uno en uno. Cuando se alcanza una instrucción `yield return`, se recuerda la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.

Para consumir un método iterador desde código de cliente, use una instrucción [foreach](../../language-reference/keywords/foreach-in.md) o una consulta de LINQ.

En el ejemplo siguiente, la primera iteración del bucle `foreach` hace que continúe la ejecución del método de iterador `SomeNumbers` hasta que se alcance la primera instrucción `yield return`. Esta iteración devuelve un valor de 3, y la ubicación actual del método de iterador se conserva. En la siguiente iteración del bucle, la ejecución del método iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `yield return`. Esta iteración devuelve un valor de 5, y la ubicación actual del método de iterador se vuelve a conservar. El bucle se completa al alcanzar el final del método iterador.

```csharp
static void Main()
{
    foreach (int number in SomeNumbers())
    {
        Console.Write(number.ToString() + " ");
    }
    // Output: 3 5 8
    Console.ReadKey();
}

public static System.Collections.IEnumerable SomeNumbers()
{
    yield return 3;
    yield return 5;
    yield return 8;
}
```

El tipo de valor devuelto de un método de iterador o descriptor de acceso `get` puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.

Puede usar una instrucción `yield break` para finalizar la iteración.

> [!NOTE]
> En todos los ejemplos de este tema, excepto en el ejemplo de iterador simple, incluya directivas [using](../../language-reference/keywords/using-directive.md) para los espacios de nombres `System.Collections` y `System.Collections.Generic`.

## <a name="simple-iterator"></a>Iterador simple

El ejemplo siguiente tiene una única instrucción `yield return` que está dentro de un bucle [for](../../language-reference/keywords/for.md). En `Main`, cada iteración del cuerpo de la instrucción `foreach` crea una llamada a la función de iterador, que continúa a la instrucción `yield return` siguiente.

```csharp
static void Main()
{
    foreach (int number in EvenSequence(5, 18))
    {
        Console.Write(number.ToString() + " ");
    }
    // Output: 6 8 10 12 14 16 18
    Console.ReadKey();
}

public static System.Collections.Generic.IEnumerable<int>
    EvenSequence(int firstNumber, int lastNumber)
{
    // Yield even numbers in the range.
    for (int number = firstNumber; number <= lastNumber; number++)
    {
        if (number % 2 == 0)
        {
            yield return number;
        }
    }
}
```

## <a name="creating-a-collection-class"></a>Creación de una clase de colección

En el ejemplo siguiente, la clase `DaysOfTheWeek` implementa la interfaz <xref:System.Collections.IEnumerable>, que requiere un método <xref:System.Collections.IEnumerable.GetEnumerator%2A>. El compilador llama implícitamente al método `GetEnumerator`, que devuelve un <xref:System.Collections.IEnumerator>.

El método `GetEnumerator` devuelve las cadenas de una en una mediante la instrucción `yield return`.

```csharp
static void Main()
{
    DaysOfTheWeek days = new DaysOfTheWeek();

    foreach (string day in days)
    {
        Console.Write(day + " ");
    }
    // Output: Sun Mon Tue Wed Thu Fri Sat
    Console.ReadKey();
}

public class DaysOfTheWeek : IEnumerable
{
    private string[] days = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };

    public IEnumerator GetEnumerator()
    {
        for (int index = 0; index < days.Length; index++)
        {
            // Yield each day of the week.
            yield return days[index];
        }
    }
}
```

En el ejemplo siguiente se crea una clase `Zoo` que contiene una colección de animales.

La instrucción `foreach` que hace referencia a la instancia de clase (`theZoo`) llama implícitamente al método `GetEnumerator`. Las instrucciones `foreach` que hacen referencia a las propiedades `Birds` y `Mammals` usan el método iterador con el nombre `AnimalsForType`.

```csharp
static void Main()
{
    Zoo theZoo = new Zoo();

    theZoo.AddMammal("Whale");
    theZoo.AddMammal("Rhinoceros");
    theZoo.AddBird("Penguin");
    theZoo.AddBird("Warbler");

    foreach (string name in theZoo)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Whale Rhinoceros Penguin Warbler

    foreach (string name in theZoo.Birds)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Penguin Warbler

    foreach (string name in theZoo.Mammals)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Whale Rhinoceros

    Console.ReadKey();
}

public class Zoo : IEnumerable
{
    // Private members.
    private List<Animal> animals = new List<Animal>();

    // Public methods.
    public void AddMammal(string name)
    {
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Mammal });
    }

    public void AddBird(string name)
    {
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Bird });
    }

    public IEnumerator GetEnumerator()
    {
        foreach (Animal theAnimal in animals)
        {
            yield return theAnimal.Name;
        }
    }

    // Public members.
    public IEnumerable Mammals
    {
        get { return AnimalsForType(Animal.TypeEnum.Mammal); }
    }

    public IEnumerable Birds
    {
        get { return AnimalsForType(Animal.TypeEnum.Bird); }
    }

    // Private methods.
    private IEnumerable AnimalsForType(Animal.TypeEnum type)
    {
        foreach (Animal theAnimal in animals)
        {
            if (theAnimal.Type == type)
            {
                yield return theAnimal.Name;
            }
        }
    }

    // Private class.
    private class Animal
    {
        public enum TypeEnum { Bird, Mammal }

        public string Name { get; set; }
        public TypeEnum Type { get; set; }
    }
}
```

## <a name="using-iterators-with-a-generic-list"></a>Uso de iteradores con una lista genérica

En el ejemplo siguiente, la clase genérica <xref:System.Collections.Generic.Stack%601> implementa la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>. El método <xref:System.Collections.Generic.Stack%601.Push%2A> asigna valores a una matriz de tipo `T`. El método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> devuelve los valores de la matriz con la instrucción `yield return`.

Además del método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> genérico, el método <xref:System.Collections.IEnumerable.GetEnumerator%2A> no genérico también debe implementarse. Esto es porque <xref:System.Collections.Generic.IEnumerable%601> se hereda de <xref:System.Collections.IEnumerable>. La implementación no genérica aplaza la implementación genérica.

El ejemplo usa iteradores con nombre para admitir distintas formas de recorrer en iteración la misma colección de datos. Estos iteradores con nombre son las propiedades `TopToBottom` y `BottomToTop`, y el método `TopN`.

La propiedad `BottomToTop` usa un iterador en un descriptor de acceso `get`.

```csharp
static void Main()
{
    Stack<int> theStack = new Stack<int>();

    //  Add items to the stack.
    for (int number = 0; number <= 9; number++)
    {
        theStack.Push(number);
    }

    // Retrieve items from the stack.
    // foreach is allowed because theStack implements IEnumerable<int>.
    foreach (int number in theStack)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3 2 1 0

    // foreach is allowed, because theStack.TopToBottom returns IEnumerable(Of Integer).
    foreach (int number in theStack.TopToBottom)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3 2 1 0

    foreach (int number in theStack.BottomToTop)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 0 1 2 3 4 5 6 7 8 9

    foreach (int number in theStack.TopN(7))
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3

    Console.ReadKey();
}

public class Stack<T> : IEnumerable<T>
{
    private T[] values = new T[100];
    private int top = 0;

    public void Push(T t)
    {
        values[top] = t;
        top++;
    }
    public T Pop()
    {
        top--;
        return values[top];
    }

    // This method implements the GetEnumerator method. It allows
    // an instance of the class to be used in a foreach statement.
    public IEnumerator<T> GetEnumerator()
    {
        for (int index = top - 1; index >= 0; index--)
        {
            yield return values[index];
        }
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        return GetEnumerator();
    }

    public IEnumerable<T> TopToBottom
    {
        get { return this; }
    }

    public IEnumerable<T> BottomToTop
    {
        get
        {
            for (int index = 0; index <= top - 1; index++)
            {
                yield return values[index];
            }
        }
    }

    public IEnumerable<T> TopN(int itemsFromTop)
    {
        // Return less than itemsFromTop if necessary.
        int startIndex = itemsFromTop >= top ? 0 : top - itemsFromTop;

        for (int index = top - 1; index >= startIndex; index--)
        {
            yield return values[index];
        }
    }

}
```

## <a name="syntax-information"></a>Información sobre la sintaxis

Un iterador se puede producir como un método o como un descriptor de acceso `get`. Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un finalizador estático.

Debe existir una conversión implícita desde el tipo de expresión en la instrucción `yield return` al argumento de tipo para el valor `IEnumerable<T>` devuelto por el iterador.

En C#, un método iterador no puede tener ningún parámetro `in`, `ref` o `out`.

En C#, `yield` no es una palabra reservada y solo tiene un significado especial cuando se usa antes de una palabra clave `return` o `break`.

## <a name="technical-implementation"></a>Implementación técnica

Aunque un iterador se escribe como un método, el compilador lo traduce a una clase anidada que es, en realidad, una máquina de estados. Esta clase realiza el seguimiento de la posición del iterador mientras el bucle `foreach` continúe en el código de cliente.

Para ver lo que hace el compilador, puede usar la herramienta Ildasm.exe para ver el código de lenguaje intermedio de Microsoft que se genera para un método de iterador.

Cuando crea un iterador para una [clase](../../language-reference/keywords/class.md) o [struct](../../language-reference/builtin-types/struct.md), no necesita implementar la interfaz <xref:System.Collections.IEnumerator> completa. Cuando el compilador detecta el iterador, genera automáticamente los métodos `Current`, `MoveNext` y `Dispose` de la interfaz <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.

En cada iteración sucesiva del bucle `foreach` (o la llamada directa a `IEnumerator.MoveNext`), el cuerpo de código del iterador siguiente se reanuda después de la instrucción `yield return` anterior. Después continúa con la siguiente instrucción `yield return` hasta que se alcanza el final del cuerpo del iterador, o hasta que se encuentra una instrucción `yield break`.

Los iteradores no admiten el método <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType>. Para volver a recorrer en iteración desde el principio, se debe obtener un nuevo iterador. Una llamada a <xref:System.Collections.IEnumerator.Reset%2A> en el iterador devuelto por un método de iterador inicia una excepción <xref:System.NotSupportedException>.

Para obtener más información, vea la [Especificación del lenguaje C#](~/_csharplang/spec/classes.md#iterators).

## <a name="use-of-iterators"></a>Uso de iteradores

Los iteradores permiten mantener la simplicidad de un bucle `foreach` cuando se necesita usar código complejo para rellenar una secuencia de lista. Esto puede ser útil si quiere hacer lo siguiente:

- Modificar la secuencia de lista después de la primera iteración del bucle `foreach`.

- Evitar que se cargue totalmente una lista grande antes de la primera iteración de un bucle `foreach`. Un ejemplo es una búsqueda paginada para cargar un lote de filas de tabla. Otro ejemplo es el método <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, que implementa iteradores en .NET.

- Encapsular la creación de la lista en el iterador. En el método iterador, puede crear la lista y después devolver cada resultado en un bucle.

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [foreach, in](../../language-reference/keywords/foreach-in.md)
- [yield](../../language-reference/keywords/yield.md)
- [Utilizar foreach con matrices](../arrays/using-foreach-with-arrays.md)
- [Genéricos](../generics/index.md)
