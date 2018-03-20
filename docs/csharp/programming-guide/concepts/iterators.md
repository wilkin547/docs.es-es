---
title: Iteradores (C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: c93f6dd4-e72a-4a06-be1c-a98b3255b734
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 48b09368ed0a84dc84793091b819ba7b4b6183f1
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2018
---
# <a name="iterators-c"></a><span data-ttu-id="083a9-102">Iteradores (C#)</span><span class="sxs-lookup"><span data-stu-id="083a9-102">Iterators (C#)</span></span>
<span data-ttu-id="083a9-103">Un *iterador* puede usarse para recorrer colecciones como listas y matrices.</span><span class="sxs-lookup"><span data-stu-id="083a9-103">An *iterator* can be used to step through collections such as lists and arrays.</span></span>  
  
 <span data-ttu-id="083a9-104">Un método iterador o un descriptor de acceso `get` realiza una iteración personalizada en una colección.</span><span class="sxs-lookup"><span data-stu-id="083a9-104">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="083a9-105">Un iterador usa la instrucción [yield return](../../../csharp/language-reference/keywords/yield.md) para devolver cada elemento de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="083a9-105">An iterator method uses the [yield return](../../../csharp/language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="083a9-106">Cuando se alcanza una instrucción `yield return`, se recuerda la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="083a9-106">When a `yield return` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="083a9-107">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="083a9-107">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="083a9-108">Para consumir un método iterador desde código de cliente, use una instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md) o una consulta de LINQ.</span><span class="sxs-lookup"><span data-stu-id="083a9-108">You consume an iterator from client code by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement or by using a LINQ query.</span></span>  
  
 <span data-ttu-id="083a9-109">En el ejemplo siguiente, la primera iteración del bucle `foreach` hace que continúe la ejecución del método de iterador `SomeNumbers` hasta que se alcance la primera instrucción `yield return`.</span><span class="sxs-lookup"><span data-stu-id="083a9-109">In the following example, the first iteration of the `foreach` loop causes execution to proceed  in the `SomeNumbers` iterator method until the first `yield return` statement is reached.</span></span> <span data-ttu-id="083a9-110">Esta iteración devuelve un valor de 3, y la ubicación actual del método de iterador se conserva.</span><span class="sxs-lookup"><span data-stu-id="083a9-110">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="083a9-111">En la siguiente iteración del bucle, la ejecución del método iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `yield return`.</span><span class="sxs-lookup"><span data-stu-id="083a9-111">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="083a9-112">Esta iteración devuelve un valor de 5, y la ubicación actual del método de iterador se vuelve a conservar.</span><span class="sxs-lookup"><span data-stu-id="083a9-112">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="083a9-113">El bucle se completa al alcanzar el final del método iterador.</span><span class="sxs-lookup"><span data-stu-id="083a9-113">The loop completes when the end of the iterator method is reached.</span></span>  
  
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
  
 <span data-ttu-id="083a9-114">El tipo de valor devuelto de un método de iterador o descriptor de acceso `get` puede ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="083a9-114">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="083a9-115">Puede usar una instrucción `yield break` para finalizar la iteración.</span><span class="sxs-lookup"><span data-stu-id="083a9-115">You can use a `yield break` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="083a9-116">Los iteradores se añadieron a C# en Visual Studio 2005.</span><span class="sxs-lookup"><span data-stu-id="083a9-116">Iterators were introduced in C# in Visual Studio 2005.</span></span>  
  
 <span data-ttu-id="083a9-117">**En este tema**</span><span class="sxs-lookup"><span data-stu-id="083a9-117">**In this topic**</span></span>  
  
-   [<span data-ttu-id="083a9-118">Iterador simple</span><span class="sxs-lookup"><span data-stu-id="083a9-118">Simple Iterator</span></span>](#BKMK_SimpleIterator)  
  
-   [<span data-ttu-id="083a9-119">Crear una clase de colección</span><span class="sxs-lookup"><span data-stu-id="083a9-119">Creating a Collection Class</span></span>](#BKMK_CollectionClass)  
  
-   [<span data-ttu-id="083a9-120">Uso de iteradores con una lista genérica</span><span class="sxs-lookup"><span data-stu-id="083a9-120">Using Iterators with a Generic List</span></span>](#BKMK_GenericList)  
  
-   [<span data-ttu-id="083a9-121">Información sobre la sintaxis</span><span class="sxs-lookup"><span data-stu-id="083a9-121">Syntax Information</span></span>](#BKMK_SyntaxInformation)  
  
-   [<span data-ttu-id="083a9-122">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="083a9-122">Technical Implementation</span></span>](#BKMK_Technical)  
  
-   [<span data-ttu-id="083a9-123">Uso de iteradores</span><span class="sxs-lookup"><span data-stu-id="083a9-123">Use of Iterators</span></span>](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  <span data-ttu-id="083a9-124">En todos los ejemplos de este tema, excepto en el ejemplo de iterador simple, incluya directivas [using](../../../csharp/language-reference/keywords/using-directive.md) para los espacios de nombres `System.Collections` y `System.Collections.Generic`.</span><span class="sxs-lookup"><span data-stu-id="083a9-124">For all examples in this topic except the Simple Iterator example, include [using](../../../csharp/language-reference/keywords/using-directive.md) directives for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>  
  
##  <a name="BKMK_SimpleIterator"></a> <span data-ttu-id="083a9-125">Iterador simple</span><span class="sxs-lookup"><span data-stu-id="083a9-125">Simple Iterator</span></span>  
 <span data-ttu-id="083a9-126">El ejemplo siguiente tiene una única instrucción `yield return` que está dentro de un bucle [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="083a9-126">The following example has a single `yield return` statement that is inside a [for](../../../csharp/language-reference/keywords/for.md) loop.</span></span> <span data-ttu-id="083a9-127">En `Main`, cada iteración del cuerpo de la instrucción `foreach` crea una llamada a la función de iterador, que continúa a la instrucción `yield return` siguiente.</span><span class="sxs-lookup"><span data-stu-id="083a9-127">In `Main`, each iteration of the `foreach` statement body creates a call to the iterator function, which proceeds to the next `yield return` statement.</span></span>  
  
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
  
##  <a name="BKMK_CollectionClass"></a> <span data-ttu-id="083a9-128">Crear una clase de colección</span><span class="sxs-lookup"><span data-stu-id="083a9-128">Creating a Collection Class</span></span>  
 <span data-ttu-id="083a9-129">En el ejemplo siguiente, la clase `DaysOfTheWeek` implementa la interfaz <xref:System.Collections.IEnumerable>, que requiere un método <xref:System.Collections.IEnumerable.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="083a9-129">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="083a9-130">El compilador llama implícitamente al método `GetEnumerator`, que devuelve un <xref:System.Collections.IEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="083a9-130">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>  
  
 <span data-ttu-id="083a9-131">El método `GetEnumerator` devuelve las cadenas de una en una mediante la instrucción `yield return`.</span><span class="sxs-lookup"><span data-stu-id="083a9-131">The `GetEnumerator` method returns each string one at a time by using the `yield return` statement.</span></span>  
  
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
  
 <span data-ttu-id="083a9-132">En el ejemplo siguiente se crea una clase `Zoo` que contiene una colección de animales.</span><span class="sxs-lookup"><span data-stu-id="083a9-132">The following example creates a `Zoo` class that contains a collection of animals.</span></span>  
  
 <span data-ttu-id="083a9-133">La instrucción `foreach` que hace referencia a la instancia de clase (`theZoo`) llama implícitamente al método `GetEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="083a9-133">The `foreach` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="083a9-134">Las instrucciones `foreach` que hacen referencia a las propiedades `Birds` y `Mammals` usan el método iterador con el nombre `AnimalsForType`.</span><span class="sxs-lookup"><span data-stu-id="083a9-134">The `foreach` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>  
  
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
  
##  <a name="BKMK_GenericList"></a> <span data-ttu-id="083a9-135">Uso de iteradores con una lista genérica</span><span class="sxs-lookup"><span data-stu-id="083a9-135">Using Iterators with a Generic List</span></span>  
 <span data-ttu-id="083a9-136">En el ejemplo siguiente, la clase genérica `Stack(Of T)` implementa la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="083a9-136">In the following example, the `Stack(Of T)` generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="083a9-137">El método `Push` asigna valores a una matriz de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="083a9-137">The `Push` method assigns values to an array of type `T`.</span></span> <span data-ttu-id="083a9-138">El método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> devuelve los valores de la matriz con la instrucción `yield return`.</span><span class="sxs-lookup"><span data-stu-id="083a9-138">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `yield return` statement.</span></span>  
  
 <span data-ttu-id="083a9-139">Además del método <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> genérico, el método <xref:System.Collections.IEnumerable.GetEnumerator%2A> no genérico también debe implementarse.</span><span class="sxs-lookup"><span data-stu-id="083a9-139">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="083a9-140">Esto es porque <xref:System.Collections.Generic.IEnumerable%601> se hereda de <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="083a9-140">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="083a9-141">La implementación no genérica aplaza la implementación genérica.</span><span class="sxs-lookup"><span data-stu-id="083a9-141">The non-generic implementation defers to the generic implementation.</span></span>  
  
 <span data-ttu-id="083a9-142">El ejemplo usa iteradores con nombre para admitir distintas formas de recorrer en iteración la misma colección de datos.</span><span class="sxs-lookup"><span data-stu-id="083a9-142">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="083a9-143">Estos iteradores con nombre son las propiedades `TopToBottom` y `BottomToTop`, y el método `TopN`.</span><span class="sxs-lookup"><span data-stu-id="083a9-143">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>  
  
 <span data-ttu-id="083a9-144">La propiedad `BottomToTop` usa un iterador en un descriptor de acceso `get`.</span><span class="sxs-lookup"><span data-stu-id="083a9-144">The `BottomToTop` property uses an iterator in a `get` accessor.</span></span>  
  
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
    // foreach is allowed because theStack implements  
    // IEnumerable<int>.  
    foreach (int number in theStack)  
    {  
        Console.Write("{0} ", number);  
    }  
    Console.WriteLine();  
    // Output: 9 8 7 6 5 4 3 2 1 0  
  
    // foreach is allowed, because theStack.TopToBottom  
    // returns IEnumerable(Of Integer).  
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
  
##  <a name="BKMK_SyntaxInformation"></a> <span data-ttu-id="083a9-145">Información sobre la sintaxis</span><span class="sxs-lookup"><span data-stu-id="083a9-145">Syntax Information</span></span>  
 <span data-ttu-id="083a9-146">Un iterador se puede producir como un método o como un descriptor de acceso `get`.</span><span class="sxs-lookup"><span data-stu-id="083a9-146">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="083a9-147">Un iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un finalizador estático.</span><span class="sxs-lookup"><span data-stu-id="083a9-147">An iterator cannot occur in an event, instance constructor, static constructor, or static finalizer.</span></span>  
  
 <span data-ttu-id="083a9-148">Debe existir una conversión implícita desde el tipo de expresión en la instrucción `yield return` al tipo de valor devuelto por el iterador.</span><span class="sxs-lookup"><span data-stu-id="083a9-148">An implicit conversion must exist from the expression type in the `yield return` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="083a9-149">En C#, un método iterador no puede tener ningún parámetro `in`, `ref` o `out`.</span><span class="sxs-lookup"><span data-stu-id="083a9-149">In C#, an iterator method cannot have any `in`, `ref`, or `out` parameters.</span></span>  
  
 <span data-ttu-id="083a9-150">En C#, "yield" no es una palabra reservada y solo tiene un significado especial cuando se usa antes de una palabra clave `return` o `break`.</span><span class="sxs-lookup"><span data-stu-id="083a9-150">In C#, "yield" is not a reserved word and has special meaning only when it is used before a `return` or `break` keyword.</span></span>  
  
##  <a name="BKMK_Technical"></a> <span data-ttu-id="083a9-151">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="083a9-151">Technical Implementation</span></span>  
 <span data-ttu-id="083a9-152">Aunque un iterador se escribe como un método, el compilador lo traduce a una clase anidada que es, en realidad, una máquina de estados.</span><span class="sxs-lookup"><span data-stu-id="083a9-152">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="083a9-153">Esta clase realiza el seguimiento de la posición del iterador mientras el bucle `foreach` continúe en el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="083a9-153">This class keeps track of the position of the iterator as long the `foreach` loop in the client code continues.</span></span>  
  
 <span data-ttu-id="083a9-154">Para ver lo que hace el compilador, puede usar la herramienta Ildasm.exe para ver el código de lenguaje intermedio de Microsoft que se genera para un método iterador.</span><span class="sxs-lookup"><span data-stu-id="083a9-154">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that is generated for an iterator method.</span></span>  
  
 <span data-ttu-id="083a9-155">Cuando crea un iterador para una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md), no necesita implementar la interfaz <xref:System.Collections.IEnumerator> completa.</span><span class="sxs-lookup"><span data-stu-id="083a9-155">When you create an iterator for a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md), you don't have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="083a9-156">Cuando el compilador detecta el iterador, genera automáticamente los métodos `Current`, `MoveNext` y `Dispose` de la interfaz <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="083a9-156">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>  
  
 <span data-ttu-id="083a9-157">En cada iteración sucesiva del bucle `foreach` (o la llamada directa a `IEnumerator.MoveNext`), el cuerpo de código del iterador siguiente se reanuda después de la instrucción `yield return` anterior.</span><span class="sxs-lookup"><span data-stu-id="083a9-157">On each successive iteration of the `foreach` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `yield return` statement.</span></span> <span data-ttu-id="083a9-158">Después continúa con la siguiente instrucción `yield return` hasta que se alcanza el final del cuerpo del iterador, o hasta que se encuentra una instrucción `yield break`.</span><span class="sxs-lookup"><span data-stu-id="083a9-158">It then continues to the next `yield return` statement until the end of the iterator body is reached, or until a `yield break` statement is encountered.</span></span>  
  
 <span data-ttu-id="083a9-159">Los iteradores no admiten el método <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="083a9-159">Iterators don't support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="083a9-160">Para volver a recorrer en iteración desde el principio, se debe obtener un nuevo iterador.</span><span class="sxs-lookup"><span data-stu-id="083a9-160">To re-iterate from the start, you must obtain a new iterator.</span></span>  
  
 <span data-ttu-id="083a9-161">Para obtener más información, vea la [Especificación del lenguaje C#](../../../csharp/language-reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="083a9-161">For additional information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
##  <a name="BKMK_UseOfIterators"></a> <span data-ttu-id="083a9-162">Uso de iteradores</span><span class="sxs-lookup"><span data-stu-id="083a9-162">Use of Iterators</span></span>  
 <span data-ttu-id="083a9-163">Los iteradores permiten mantener la simplicidad de un bucle `foreach` cuando se necesita usar código complejo para rellenar una secuencia de lista.</span><span class="sxs-lookup"><span data-stu-id="083a9-163">Iterators enable you to maintain the simplicity of a `foreach` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="083a9-164">Esto puede ser útil si quiere hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="083a9-164">This can be useful when you want to do the following:</span></span>  
  
-   <span data-ttu-id="083a9-165">Modificar la secuencia de lista después de la primera iteración del bucle `foreach`.</span><span class="sxs-lookup"><span data-stu-id="083a9-165">Modify the list sequence after the first `foreach` loop iteration.</span></span>  
  
-   <span data-ttu-id="083a9-166">Evitar que se cargue totalmente una lista grande antes de la primera iteración de un bucle `foreach`.</span><span class="sxs-lookup"><span data-stu-id="083a9-166">Avoid fully loading a large list before the first iteration of a `foreach` loop.</span></span> <span data-ttu-id="083a9-167">Un ejemplo es una búsqueda paginada para cargar un lote de filas de tabla.</span><span class="sxs-lookup"><span data-stu-id="083a9-167">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="083a9-168">Otro ejemplo es el método <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, que implementa iteradores en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="083a9-168">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>  
  
-   <span data-ttu-id="083a9-169">Encapsular la creación de la lista en el iterador.</span><span class="sxs-lookup"><span data-stu-id="083a9-169">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="083a9-170">En el método iterador, puede crear la lista y después devolver cada resultado en un bucle.</span><span class="sxs-lookup"><span data-stu-id="083a9-170">In the iterator method, you can build the list and then yield each result in a loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="083a9-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="083a9-171">See Also</span></span>  
 <xref:System.Collections.Generic>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="083a9-172">foreach, in</span><span class="sxs-lookup"><span data-stu-id="083a9-172">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="083a9-173">yield</span><span class="sxs-lookup"><span data-stu-id="083a9-173">yield</span></span>](../../../csharp/language-reference/keywords/yield.md)  
 [<span data-ttu-id="083a9-174">Utilizar foreach con matrices</span><span class="sxs-lookup"><span data-stu-id="083a9-174">Using foreach with Arrays</span></span>](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
 [<span data-ttu-id="083a9-175">Genéricos</span><span class="sxs-lookup"><span data-stu-id="083a9-175">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
