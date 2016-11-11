---
title: "Creación de nuevas cadenas"
description: "Creación de nuevas cadenas"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 639397c7-e694-43e0-845b-1681c62bd9fd
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 43d6194afd948aeccbf051365e059794c74d2646

---

# <a name="creating-new-strings"></a>Creación de nuevas cadenas

.NET permite crear cadenas mediante asignaciones simples y además sobrecarga a un constructor de clases para admitir la creación de cadenas con una serie de parámetros. .NET también proporciona varios métodos en la clase [System.String](xref:System.String) que crean nuevos objetos de cadena al combinar varias cadenas, matrices de cadenas u objetos. 

## <a name="creating-strings-using-assignment"></a>Creación de cadenas mediante asignaciones

La manera más sencilla de crear un nuevo objeto [String](xref:System.String) es asignar un literal de cadena a un objeto [String](xref:System.String). 

## <a name="creating-strings-using-a-class-constructor"></a>Creación de cadenas mediante un constructor de clase

Puede usar las sobrecargas del constructor de clase [String](xref:System.String) para crear cadenas a partir de matrices de caracteres. También puede crear una nueva cadena al duplicar un determinado carácter un número especificado de veces. 

## <a name="methods-that-return-strings"></a>Métodos que devuelven cadenas

En la tabla siguiente se enumeran varios métodos útiles que devuelven nuevos objetos de cadena.

Nombre del método | Uso
----------- | ---
[String.Format](xref:System.String.Format(System.String,System.Object)) | Compila una cadena con formato a partir de un conjunto de objetos de entrada.
[String.Concat](xref:System.String.Concat(System.String,System.String)) | Compila cadenas a partir de dos o más cadenas.
[String.Join](xref:System.String.Join(System.String,System.String[])) |Compila una nueva cadena al combinar una matriz de cadenas.
[String.Insert](xref:System.String.Insert(System.Int32,System.String)) | Compila una nueva cadena al insertar una cadena en el índice especificado de una cadena existente.
[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32)) | Copia los caracteres especificados de una cadena en la posición especificada de una matriz de caracteres.

### <a name="format"></a>Formato

Puede usar el método `String.Format` para crear cadenas con formato y concatenar cadenas que representan a varios objetos. Este método convierte automáticamente cualquier objeto pasado en una cadena. Por ejemplo, si la aplicación debe mostrar un valor [Int32](xref:System.Int32) y un valor [DateTime](xref:System.DateTime) al usuario, puede construir fácilmente una cadena para representar estos valores con el método `Format`. Para más información sobre las convenciones de formato usadas con este método, consulte la sección sobre [formatos compuestos](composite-format.md).

En el ejemplo siguiente se usa el método `Format` para crear una cadena que emplea una variable de entero.

```csharp
int numberOfFleas = 12;
string miscInfo = String.Format("Your dog has {0} fleas. " +
                                "It is time to get a flea collar. " + 
                                "The current universal date is: {1:u}.", 
                                numberOfFleas, DateTime.Now);
Console.WriteLine(miscInfo);
// The example displays the following output:
//       Your dog has 12 fleas. It is time to get a flea collar. 
//       The current universal date is: 2008-03-28 13:31:40Z.
```

```vb
Dim numberOfFleas As Integer = 12
Dim miscInfo As String = String.Format("Your dog has {0} fleas. " & _
                                       "It is time to get a flea collar. " & _ 
                                       "The current universal date is: {1:u}.", _ 
                                       numberOfFleas, Date.Now)
Console.WriteLine(miscInfo)
' The example displays the following output:
'       Your dog has 12 fleas. It is time to get a flea collar. 
'       The current universal date is: 2008-03-28 13:31:40Z.
```

En este ejemplo, [DateTime.Now](xref:System.DateTime.Now) muestra la fecha y hora actuales en el formato especificado por la referencia cultural asociada al subproceso actual.

### <a name="concat"></a>Concat

El método `String.Concat` se puede usar para crear fácilmente un nuevo objeto de cadena a partir de dos o más objetos existentes. Proporciona una manera independiente del lenguaje de concatenar cadenas. Este método acepta cualquier clase que derive de `System.Object`. En el ejemplo siguiente se crea una cadena a partir de dos objetos de cadena existentes y un carácter de separación.

```csharp
string helloString1 = "Hello";
string helloString2 = "World!";
Console.WriteLine(String.Concat(helloString1, ' ', helloString2));
// The example displays the following output:
//      Hello World!
```

```vb
Dim helloString1 As String = "Hello"
Dim helloString2 As String = "World!"
Console.WriteLine(String.Concat(helloString1, " "c, helloString2))
' The example displays the following output:
'      Hello World!
```

### <a name="join"></a>Join

El método `String.Join` crea una nueva cadena a partir de una matriz de cadenas y una cadena separadora. Este método resulta útil si quiere concatenar varias cadenas para formar una lista quizás separada por una coma.

En el ejemplo siguiente se usa un espacio para enlazar una matriz de cadenas.

```csharp
string[] words = {"Hello", "and", "welcome", "to", "my" , "world!"};
Console.WriteLine(String.Join(" ", words));
// The example displays the following output:
//      Hello and welcome to my world!
```

```vb
Dim words() As String = {"Hello", "and", "welcome", "to", "my" , "world!"}
Console.WriteLine(String.Join(" ", words))
' The example displays the following output:
'      Hello and welcome to my world!
```

### <a name="insert"></a>Insertar

El método `String.Insert` crea una nueva cadena al insertar una cadena en la posición especificada de otra cadena. Este método usa un índice basado en cero. En el ejemplo siguiente se inserta una cadena en la quinta posición del índice de `MyString` y se crea una nueva cadena con este valor.

```csharp
string sentence = "Once a time.";   
 Console.WriteLine(sentence.Insert(4, " upon"));
 // The example displays the following output:
 //      Once upon a time.
```

```vb
Dim sentence As String = "Once a time."   
 Console.WriteLine(sentence.Insert(4, " upon"))
 ' The example displays the 
```

### <a name="copyto"></a>CopyTo

El método `String.CopyTo` copia partes de una cadena en una matriz de caracteres. Puede especificar el índice inicial de la cadena y el número de caracteres que se va a copiar. Este método toma el índice de origen, una matriz de caracteres, el índice de destino y el número de caracteres que se va a copiar. Todos los índices se basan en cero.

En el ejemplo siguiente se usa el método `CopyTo` para copiar los caracteres de la palabra "Hello" de un objeto de cadena en la primera posición del índice de una matriz de caracteres.

```csharp
string greeting = "Hello World!";
char[] charArray = {'W','h','e','r','e'};
Console.WriteLine("The original character array: {0}", new string(charArray));
greeting.CopyTo(0, charArray,0 ,5);
Console.WriteLine("The new character array: {0}", new string(charArray));
// The example displays the following output:
//       The original character array: Where
//       The new character array: Hello
```

```vb
Dim greeting As String = "Hello World!"
Dim charArray() As Char = {"W"c, "h"c, "e"c, "r"c, "e"c}
Console.WriteLine("The original character array: {0}", New String(charArray))
greeting.CopyTo(0, charArray,0 ,5)
Console.WriteLine("The new character array: {0}", New String(charArray))
' The example displays the following output:
'       The original character array: Where
'       The new character array: Hello
```

## <a name="see-also"></a>Vea también

[Operaciones básicas de cadenas](basic-string-operations.md)

[Formatos compuestos](composite-format.md)




<!--HONumber=Nov16_HO1-->


