---
title: Comparar cadenas
description: Comparar cadenas
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 920ee5e8-3d61-4941-b5af-fc50eaee427c
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 2ad585bd5475cf39aeae5dadc9ce3864c501a205

---

# <a name="comparing-strings"></a>Comparar cadenas

.NET proporciona varios métodos para comparar los valores de cadenas. En la tabla siguiente se enumeran y describen los métodos de comparación de valores.

Nombre del método | Uso
----------- | ---
[String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) | Compara los valores de dos cadenas. Devuelve un valor entero.
[String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) | Compara dos cadenas independientemente de la referencia cultural local. Devuelve un valor entero.
[String.CompareTo](xref:System.String.CompareTo(System.String)) | Compara el objeto de cadena actual con otra cadena. Devuelve un valor entero.
[String.StartsWith](xref:System.String.StartsWith(System.String)) | Determina si una cadena comienza con la cadena que se pasa. Devuelve un valor booleano.
[String.EndsWith](xref:System.String.CompareTo(System.String)) | Determina si una cadena termina con la cadena que se pasa. Devuelve un valor booleano.
[String.Equals](xref:System.String.CompareTo(System.String)) | Determina si dos cadenas son iguales. Devuelve un valor booleano.
[String.IndexOf](xref:System.String.IndexOf(System.Char)) | Devuelve la posición de índice de un carácter o cadena, empezando en el comienzo de la cadena que se examina. Devuelve un valor entero.
[String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) | Devuelve la posición de índice de un carácter o cadena, empezando en el final de la cadena que se examina. Devuelve un valor entero.

## <a name="compare"></a>Comparar

El método [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) estático proporciona una manera de comparar dos cadenas exhaustivamente. En este método se tiene en cuenta la referencia cultural. Esta función se puede usar para comparar dos cadenas o subcadenas de dos cadenas. Además, se proporcionan sobrecargas para tener en cuenta o no las diferencias de referencia cultural y de mayúsculas y minúsculas. En la tabla siguiente, se muestran los tres valores enteros que este método puede devolver. 

Valor devuelto | Condición
------------ | ---------
Un entero negativo | La primera cadena precede a la segunda cadena en el criterio de ordenación, o la primera cadena es `null`.
0 | La primera y la segunda cadena son iguales o ambas cadenas son `null`.
Un entero positivo, o 1 | La primera cadena sigue a la segunda cadena en el criterio de ordenación, o la segunda cadena es null.
 
> [!IMPORTANT]
> La finalidad principal del método [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) es que se use para la ordenación o clasificación de cadenas. El método [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) no debe usarse para comprobar la igualdad (es decir, para buscar explícitamente un valor devuelto que sea 0 sin tener en cuenta si una cadena es menor o mayor que otra). En su lugar, para determinar si dos cadenas son iguales, use el método [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).

En el ejemplo siguiente, se usa el método [String.Compare](xref:System.String.Compare(System.String,System.Int32,System.String,System.Int32,System.Int32)) para determinar los valores relativos de dos cadenas.

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.Compare(string1, "Hello World?"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.Compare(string1, "Hello World?"))
```

Con este ejemplo se muestra `-1` en la consola.

## <a name="compareordinal"></a>CompareOrdinal

El método [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) compara dos objetos de cadena sin tener en cuenta la referencia cultural local. Los valores devueltos de este método son idénticos a los que devolvía el método `Compare` en la tabla anterior.

> [!IMPORTANT]
> La finalidad principal del método [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) es que se use para la ordenación o clasificación de cadenas. El método [String.CompareOrdinal](xref:System.String.CompareOrdinal(System.String,System.Int32,System.String,System.Int32,System.Int32)) no debe usarse para comprobar la igualdad (es decir, para buscar explícitamente un valor devuelto que sea 0 sin tener en cuenta si una cadena es menor o mayor que otra). En su lugar, para determinar si dos cadenas son iguales, use el método [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).

En el ejemplo siguiente, se usa el método `CompareOrdinal` para comparar los valores de dos cadenas.

```csharp
string string1 = "Hello World!";
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(String.CompareOrdinal(string1, "hello world!"))
```

Con este ejemplo se muestra `-32` en la consola.

## <a name="compareto"></a>CompareTo

El método [String.CompareTo](xref:System.String.CompareTo(System.String)) compara la cadena que encapsula el objeto de cadena actual con otra cadena u objeto. Los valores devueltos de este método son idénticos a los que devolvía el método `String.Compare` en la tabla anterior.

> [!IMPORTANT]
> La finalidad principal del método [String.CompareTo](xref:System.String.CompareTo(System.String)) es que se use para la ordenación o clasificación de cadenas. El método [String.CompareTo](xref:System.String.CompareTo(System.String)) no debe usarse para comprobar la igualdad (es decir, para buscar explícitamente un valor devuelto que sea 0 sin tener en cuenta si una cadena es menor o mayor que otra). En su lugar, para determinar si dos cadenas son iguales, use el método [String.Equals(String, String, StringComparison)](xref:System.String.Equals(System.String,System.String,System.StringComparison)).

En el ejemplo siguiente, se usa el método `String.CompareTo` para comparar los objetos `string1` y `string2`.

```csharp
string string1 = "Hello World";
string string2 = "Hello World!";
int MyInt = string1.CompareTo(string2);
Console.WriteLine( MyInt );
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World!"
Dim MyInt As Integer = string1.CompareTo(string2)
Console.WriteLine(MyInt)
```

Con este ejemplo se muestra `-1` en la consola.

## <a name="equals"></a>Es igual a

El método [String.Equals](xref:System.String.CompareTo(System.String)) puede determinar con facilidad si dos cadenas son iguales. Este método distingue entre mayúsculas y minúsculas y devuelve un valor booleano `true` o `false`. Se puede usar desde una clase existente, como se muestra en el siguiente ejemplo. En el ejemplo siguiente, se usa el método `Equals` para determinar si un objeto de cadena contiene la frase "Hello World".

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.Equals("Hello World"));
```

```vb
Dim string1 As String = "Hello World"
Console.WriteLine(string1.Equals("Hello World"))
```

Con este ejemplo se muestra `true` en la consola.

Este método se puede usar también como método estático. En el ejemplo siguiente se comparan dos objetos de cadena utilizando un método estático.

```csharp
string string1 = "Hello World";
string string2 = "Hello World";
Console.WriteLine(String.Equals(string1, string2));
```

```vb
Dim string1 As String = "Hello World"
Dim string2 As String = "Hello World"
Console.WriteLine(String.Equals(string1, string2))
```

Con este ejemplo se muestra `true` en la consola.

## <a name="startswith-and-endswith"></a>StartsWith y EndsWith

El método [String.StartsWith](xref:System.String.StartsWith(System.String)) se puede usar para determinar si un objeto de cadena comienza con los mismos caracteres que forman otra cadena. Este método distingue entre mayúsculas y minúsculas y devuelve `true` si el objeto de cadena actual comienza con la cadena que se pasa y `false` si no lo hace. En el ejemplo siguiente se usa este método para determinar si un objeto de cadena comienza con "Hello".

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.StartsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.StartsWith("Hello"))
```

Con este ejemplo se muestra `true` en la consola.

El método [String.EndsWith](xref:System.String.CompareTo(System.String)) compara la cadena que se pasa con los caracteres del final del objeto de cadena actual. También devuelve un valor booleano. En el ejemplo siguiente, se comprueba el final de una cadena con el método `EndsWith`.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.EndsWith("Hello"));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.EndsWith("Hello"))
```

Con este ejemplo se muestra `false` en la consola.

## <a name="indexof-and-lastindexof"></a>IndexOf y LastIndexOf

El método [String.IndexOf](xref:System.String.IndexOf(System.Char)) se puede usar para determinar la posición de la primera aparición de un carácter concreto dentro de una cadena. Este método, que distingue entre mayúsculas y minúsculas, empieza a contar desde el comienzo de una cadena y devuelve la posición del carácter que se pasa utilizando un índice de base cero. Si no encuentra el carácter, se devuelve un valor de –1.

En el ejemplo siguiente, se usa el método `IndexOf` para buscar la primera aparición del carácter "`l`" en una cadena.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.IndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.IndexOf("l"))
```

Con este ejemplo se muestra `2` en la consola.

El método [String.LastIndexOf](xref:System.String.LastIndexOf(System.Char)) es parecido al método `String.IndexOf`, con la diferencia de que devuelve la posición de la última instancia de un carácter concreto en una cadena. Distingue mayúsculas y minúsculas y utiliza un índice de base cero. 

En el ejemplo siguiente, se usa el método `LastIndexOf` para buscar la última aparición del carácter "`l`" en una cadena.

```csharp
string string1 = "Hello World";
Console.WriteLine(string1.LastIndexOf('l'));
```

```vb
Dim string1 As String = "Hello World!"
Console.WriteLine(string1.LastIndexOf("l"))
```

Con este ejemplo se muestra `9` en la consola.

Los dos métodos resultan útiles si se usan junto con el método [String.Remove](xref:System.String.Remove(System.Int32)). Se pueden usar los métodos `IndexOf` o `LastIndexOf` para recuperar la posición de un carácter y después proporcionar esa posición al método `Remove method` para quitar un carácter o una palabra que comience por ese carácter.

## <a name="see-also"></a>Vea también

[Operaciones básicas de cadenas](basic-string-operations.md)















<!--HONumber=Nov16_HO3-->


