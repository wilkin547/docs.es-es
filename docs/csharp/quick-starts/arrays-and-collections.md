---
title: "Inicio rápido: colecciones (Guía de C#)"
description: "Conozca C# a través de la colección de listas que se presenta en esta guía de inicio rápido."
keywords: "C#, introducción, tutorial, colecciones, lista"
author: billwagner
ms.author: wiwagn
ms.date: 10/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 228a9dd88d0a511492ccb8b70e0231278969acbe
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2017
---
# <a name="c-quick-start-collections"></a>Inicio rápido de C#: colecciones #

Este inicio rápido proporciona una introducción al lenguaje C# y los conceptos básicos de la <xref:System.Collections.Generic.List%601> clase.

Este inicio rápido en el que se espera que debe disponer de una máquina que se puede usar para el desarrollo. El tema de .NET [empezar a trabajar en 10 minutos](https://www.microsoft.com/net/core) tiene instrucciones sobre cómo configurar el entorno de desarrollo local en Linux, Mac o PC.

## <a name="a-basic-list-example"></a>Un ejemplo de lista básica.

Cree un directorio denominado **inicio rápido-lista**. Conviértalo en el directorio actual y ejecute `dotnet new console`.

> [!NOTE]
> Si acaba de completar [Introducción a .NET en 10 minutos](https://www.microsoft.com/net), puede seguir usando la aplicación myApp que acaba de crear.
 
Abra **Program.cs** en su editor favorito y reemplace el código existente por el siguiente:

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

Reemplace `<name>` por su propio nombre. Guarde **Program.cs**. Escriba `dotnet run` en la ventana de la consola para probarlo.

Hasta ahora, solo ha creado una lista de cadenas, ha agregado tres nombres a dicha lista y ha impreso los nombres en MAYÚSCULA. Los conceptos aplicados ya se han aprendido en los inicios rápidos anteriores para recorrer la lista.

El código para mostrar los nombres usa **cadenas interpoladas**.  Si un valor de `string` va precedido del carácter `$`, significa que puede insertar código de C# en la declaración de cadena. La cadena real reemplaza a ese código de C# con el valor que genera. En este ejemplo, reemplaza `{name.ToUpper()}` con cada nombre, convertido a mayúsculas, porque se llama al método <xref:System.String.ToUpper%2A>.

Vamos a continuar indagando.
    
## <a name="modify-list-contents"></a>Modificación del contenido de las listas

La colección creada usa el tipo <xref:System.Collections.Generic.List%601>. Este tipo almacena las secuencias de elementos. Especifique el tipo de los elementos entre corchetes angulares.
    
Un aspecto importante de este tipo <xref:System.Collections.Generic.List%601> es que se puede aumentar o reducir, lo que permite agregar o quitar elementos. Agregue este código antes del corchete de cierre `}` en el método `Main`:

```csharp
Console.WriteLine();
names.Add("Maria");
names.Add("Bill");
names.Remove("Ana");
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

Se han agregado dos nombres más al final de la lista. También se ha quitado uno. Guarde el archivo y escriba `dotnet run` para probarlo.
    
<xref:System.Collections.Generic.List%601> también permite hacer referencia a elementos individuales a través del **índice**. Coloque el índice entre los tokens `[` y `]` después del nombre de la lista. C# utiliza 0 para el primer índice. Agregue este código directamente después del código que acaba de agregar y pruébelo:

```csharp
Console.WriteLine($"My name is {names[0]}");
Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");
```

No se puede acceder a un índice si se coloca después del final de la lista. Recuerde que los índices empiezan en 0, por lo que el índice más grande válido es uno menos que el número de elementos de la lista. Puede comprobar durante cuánto tiempo la lista usa la propiedad <xref:System.Collections.Generic.List%601.Count%2A>. Agregue el código siguiente al final del método Main:

```csharp
Console.WriteLine($"The list has {names.Count} people in it");
 ```

Guarde el archivo y vuelva a escribir `dotnet run` para ver los resultados.    

## <a name="search-and-sort-lists"></a>Búsqueda y orden en las listas
En los ejemplos se usan listas relativamente pequeñas, pero las aplicaciones a menudo pueden crear listas que contengan muchos más elementos, en ocasiones, con una numeración que engloba millares. Para encontrar elementos en estas colecciones más grandes, debe buscar diferentes elementos en la lista. El método <xref:System.Collections.Generic.List%601.IndexOf%2A> busca un elemento y devuelve su índice. Agregue este código en la parte inferior del método `Main`:

```csharp
var index = names.IndexOf("Felipe");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
}

index = names.IndexOf("Not Found");
if (index == -1)
{
    Console.WriteLine($"When an item is not found, IndexOf returns {index}");
} else
{
    Console.WriteLine($"The name {names[index]} is at index {index}");
    
}
```

Los elementos de la lista también se pueden ordenar. El método <xref:System.Collections.Generic.List%601.Sort%2A> ordena todos los elementos de la lista en su orden normal (por orden alfabético si se trata de cadenas). Agregue este código en la parte inferior del método `Main`:

```csharp
names.Sort();
foreach (var name in names)
{
    Console.WriteLine($"Hello {name.ToUpper()}!");
}
```

Guarde el archivo y escriba `dotnet run` para probar esta última versión.

Antes comenzar con la siguiente sección, se va a mover el código actual a un método independiente. Con este paso, resulta más fácil empezar con un nuevo ejemplo. Cambie el nombre del método `Main` por `WorkingWithStrings` y escriba un método `Main` nuevo que llame a `WorkingWithStrings`. Cuando termine, el código debe tener un aspecto similar al siguiente:

```csharp
using System;
using System.Collections.Generic;

namespace list_quickstart
{
    class Program
    {
        static void Main(string[] args)
        {
            WorkingWithStrings();
        }

        public static void WorkingWithStrings()
        {
            var names = new List<string> { "<name>", "Ana", "Felipe" };
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine();
            names.Add("Maria");
            names.Add("Bill");
            names.Remove("Ana");
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }

            Console.WriteLine($"My name is {names[0]}");
            Console.WriteLine($"I've added {names[2]} and {names[3]} to the list");

            Console.WriteLine($"The list has {names.Count} people in it");

            var index = names.IndexOf("Felipe");
            Console.WriteLine($"The name {names[index]} is at index {index}");

            var notFound = names.IndexOf("Not Found");
            Console.WriteLine($"When an item is not found, IndexOf returns {notFound}");

            names.Sort();
            foreach (var name in names)
            {
                Console.WriteLine($"Hello {name.ToUpper()}!");
            }
        }
    }
}
```

## <a name="lists-of-other-types"></a>Listas de otros tipos

Hasta el momento, se ha usado el tipo `string` en las listas. Se va a crear una lista <xref:System.Collections.Generic.List%601> con un tipo distinto. Se va a crear una serie de números. 

Agregue lo siguiente en la parte inferior del método `Main` nuevo:

```csharp
var fibonacciNumbers = new List<int> {1, 1};
```

Se crea una lista de enteros y se definen los dos primeros enteros con el valor 1. Son los dos primeros valores de una *sucesión de Fibonacci*, una secuencia de números. Cada número sucesivo de Fibonacci se obtiene con la suma de los dos números anteriores. Agregue este código:

```csharp
var previous = fibonacciNumbers[fibonacciNumbers.Count - 1];
var previous2 = fibonacciNumbers[fibonacciNumbers.Count - 2];

fibonacciNumbers.Add(previous + previous2);

foreach(var item in fibonacciNumbers)
    Console.WriteLine(item);
```

Guarde el archivo y escriba `dotnet run` para ver los resultados. 

> [!TIP]
> Para centrarse solo en esta sección, puede comentar el código que llama a `WorkingWithStrings();`. Solo debe colocar dos caracteres `/` delante de la llamada, como en: `// WorkingWithStrings();`. 

## <a name="challenge"></a>Desafío
Trate de recopilar los conocimientos que ha aprendido en esta lección y en las anteriores. Amplíe lo que ha creado hasta el momento con los números de Fibonacci. Pruebe y escriba el código para generar los veinte primeros números de la secuencia.

## <a name="complete-challenge"></a>Desafío completo

Puede ver un ejemplo de solución si [consulta el ejemplo de código terminado en GitHub](https://github.com/dotnet/docs/tree/master/samples/csharp/list-quickstart/Program.cs#L13-L23).

Con cada iteración del bucle, se obtienen los dos últimos enteros de la lista, se suman y se agrega el valor resultante a la lista. El bucle se repite hasta que se hayan agregado veinte elementos a la lista.

Enhorabuena, ha completado el inicio rápido de la lista. Puede continuar con la [Introducción a las clases](introduction-to-classes.md) inicio rápido en su propio entorno de desarrollo.

Puede obtener más información sobre cómo trabajar con el tipo `List` en el tema de la [Guía de .NET](../../standard/index.md) que trata sobre las [colecciones](../../standard/collections/index.md). Ahí también podrá conocer muchos otros tipos de colecciones.
