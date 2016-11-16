---
title: Recortar y quitar caracteres de cadenas
description: Recortar y quitar caracteres de cadenas
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 95d818bc-2661-43f6-adb8-13b53abf9682
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 96cf08c0de8ba73d931d561187369ccf8b091651

---

# <a name="trimming-and-removing-characters-from-strings"></a>Recortar y quitar caracteres de cadenas

Si va a analizar una frase en las palabras que la forman, el resultado pueden ser palabras con espacios en blanco delante y detrás. En este caso, puede usar uno de los métodos de recorte de la clase [System.String](https://docs.microsoft.com/dotnet/core/api/System.String) para quitar espacios u otros caracteres de una posición especificada de la cadena. En la tabla siguiente se describen los métodos de recorte disponibles.

Nombre del método | Uso
----------- | ---
[String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) | Quita del comienzo y del final de una cadena los espacios en blanco o los caracteres especificados en una matriz de caracteres.
[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) | Quita los caracteres especificados de una matriz de caracteres del final de una cadena.
[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) | Quita los caracteres especificados de una matriz de caracteres del comienzo de una cadena.
[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) | Quita un número especificado de caracteres de una posición de índice especificada de una cadena.


## <a name="trim"></a>Trim

Los espacios en blanco situados delante y detrás de una cadena se pueden quitar fácilmente con el método [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim), como se muestra en el ejemplo siguiente.

```csharp
string MyString = " Big   ";
Console.WriteLine("Hello{0}World!", MyString);
string TrimString = MyString.Trim();
Console.WriteLine("Hello{0}World!", TrimString);
//       The example displays the following output:
//             Hello Big   World!
//             HelloBigWorld!
```

```vb
Dim MyString As String = " Big   "
Console.WriteLine("Hello{0}World!", MyString)
Dim TrimString As String = MyString.Trim()
Console.WriteLine("Hello{0}World!", TrimString)
' The example displays the following output:
'       Hello Big   World!
'       HelloBigWorld!
```

También se pueden quitar del principio y el final de una cadena los caracteres especificados en una matriz de caracteres. En el ejemplo siguiente se quitan los caracteres de espacio en blanco, los puntos y asteriscos.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String header = "* A Short String. *";
      Console.WriteLine(header);
      Console.WriteLine(header.Trim( new Char[] { ' ', '*', '.' } ));
   }
}
// The example displays the following output:
//       * A Short String. *
//       A Short String
```

```vb
Module Example
   Public Sub Main()
      Dim header As String = "* A Short String. *"
      Console.WriteLine(header)
      Console.WriteLine(header.Trim( { " "c, "*"c, "."c } ))
   End Sub
End Module
' The example displays the following output:
'       * A Short String. *
'       A Short String
```

## <a name="trimend"></a>TrimEnd

El método [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) quita caracteres del final de una cadena, creando un nuevo objeto de cadena. A este método se le pasa una matriz de caracteres para especificar los caracteres que se van a quitar. El orden de los elementos en la matriz de caracteres no afecta a la operación de recorte. El recorte se detiene cuando se encuentra un carácter no especificado en la matriz.

En el ejemplo siguiente se quitan las últimas letras de una cadena con el método TrimEnd. En este ejemplo, se invierte la posición de los caracteres `'r'` y `'W'` para ilustrar que el orden de los caracteres en la matriz no tiene importancia. Observe que este código quita la última palabra de `MyString` y parte de la primera.

```csharp
string MyString = "Hello World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

Con este código se muestra `He` en la consola.

En el ejemplo siguiente se quita la última palabra de una cadena con el método [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])). En este código hay una coma después de `Hello` y, como la coma no está especificada en la matriz de caracteres que se deben recortar, la operación se detiene en la coma.

```csharp
string MyString = "Hello, World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello, World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

Con este código se muestra `Hello,` en la consola.

## <a name="trimstart"></a>TrimStart

El método [String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) es parecido al método [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])), con la diferencia de que crea una nueva cadena quitando caracteres del comienzo de un objeto de cadena existente. Al método [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) se le pasa una matriz de caracteres para especificar los caracteres que se van a quitar. Lo mismo que en el método [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])), el orden de los elementos en la matriz de caracteres no afecta a la operación de recorte. El recorte se detiene cuando se encuentra un carácter no especificado en la matriz.

En el siguiente ejemplo se quita la primera palabra de una cadena. En este ejemplo, se invierte la posición de los caracteres `'l'` y `'H'` para ilustrar que el orden de los caracteres en la matriz no tiene importancia.

```csharp
string MyString = "Hello World!";
char[] MyChar = {'e', 'H','l','o',' ' };
string NewString = MyString.TrimStart(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"e","H","l","o"," " }
Dim NewString As String = MyString.TrimStart(MyChar)
Console.WriteLine(NewString)
```

Con este código se muestra `World!` en la consola.

## <a name="remove"></a>Quitar

El método [String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) quita un número especificado de caracteres a partir de una posición especificada de una cadena existente. Este método utiliza un índice basado en cero.

En el ejemplo siguiente se quitan diez caracteres de una cadena, comenzando en la posición cinco de un índice de base cero de la cadena.

```csharp
string MyString = "Hello Beautiful World!";
Console.WriteLine(MyString.Remove(5,10));
// The example displays the following output:
//         Hello World!  
```

```vb
Dim MyString As String = "Hello Beautiful World!"
Console.WriteLine(MyString.Remove(5,10))
' The example displays the following output:
'         Hello World!
```

También puede quitar un carácter o una subcadena de una cadena llamando al método [String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String)) y especificando una cadena vacía ([String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)) como reemplazo. En el ejemplo siguiente se quitan todas las comas de una cadena.

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String phrase = "a cold, dark night";
      Console.WriteLine("Before: {0}", phrase);
      phrase = phrase.Replace(",", "");
      Console.WriteLine("After: {0}", phrase);
   }
}
// The example displays the following output:
//       Before: a cold, dark night
//       After: a cold dark night
```

```vb
Module Example
   Public Sub Main()
      Dim phrase As String = "a cold, dark night"
      Console.WriteLine("Before: {0}", phrase)
      phrase = phrase.Replace(",", "")
      Console.WriteLine("After: {0}", phrase)
   End Sub
End Module
' The example displays the following output:
'       Before: a cold, dark night
'       After: a cold dark night
```

## <a name="see-also"></a>Vea también

[Operaciones básicas de cadenas](basic-string-operations.md)




<!--HONumber=Nov16_HO1-->


