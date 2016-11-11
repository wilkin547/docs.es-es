---
title: "Cadenas de formato de enumeración"
description: "Cadenas de formato de enumeración"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/25/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 4d581898-99bc-42c3-816c-d8238f45096f
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 8cb811636ca2c7b207f7661e990567b5785bc994

---

# <a name="enumeration-format-strings"></a>Cadenas de formato de enumeración

Puede usar el método [Enum.ToString](xref:System.Enum.ToString) para crear un nuevo objeto de cadena que represente el valor de cadena, numérico o hexadecimal del miembro de una enumeración. Este método toma una de las cadenas de formato de enumeración para especificar el valor que quiere que se devuelva.

En las secciones siguientes se enumeran las cadenas de formato de enumeración y los valores que devuelven. Estos especificadores de formato no distinguen mayúsculas de minúsculas.

## <a name="the-g-or-g-format-strings"></a>Cadenas de formato G o g

Las cadenas de formato G o g muestran la entrada de enumeración como un valor de cadena, si es posible, y si no, muestran el valor entero de la instancia actual. Si la enumeración se define con el conjunto de atributos `Flags`, los valores de cadena de cada entrada válida se concatenan, separados por comas. Si el atributo `Flags` no está establecido, se muestra un valor no válido como entrada numérica. En el siguiente ejemplo se muestra el uso del especificador de formato G.

```csharp
Console.WriteLine(ConsoleColor.Red.ToString("G"));         // Displays Red
FileAttributes attributes = FileAttributes.Hidden |
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("G"));   // Displays Hidden, Archive
```

```vb
Console.WriteLine(ConsoleColor.Red.ToString("G"))           ' Displays Red
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("G"))     ' Displays Hidden, Archive
```

## <a name="the-f-or-f-format-strings"></a>Cadenas de formato F o f

Las cadenas de formato F o f muestran la entrada de enumeración como un valor de cadena, si es posible. Si el valor se puede mostrar por completo como una suma de las entradas de la enumeración (incluso si el atributo `Flags` no está presente), los valores de cadena de cada entrada válida se concatenan, separados por comas. Si las entradas de enumeración no pueden determinar completamente el valor, a este se le da formato como valor entero. En el siguiente ejemplo se muestra el uso del especificador de formato F.

```csharp
Console.WriteLine(ConsoleColor.Blue.ToString("F"));       // Displays Blue
FileAttributes attributes = FileAttributes.Hidden | 
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("F"));   // Displays Hidden, Archive
```

```vb
Console.WriteLine(ConsoleColor.Blue.ToString("F"))         ' Displays Blue
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("F"))     ' Displays Hidden, Archive
```

## <a name="the-d-or-d-format-strings"></a>Cadenas de formato D o d

Las cadenas de formato D o d muestran la entrada de enumeración como un valor entero en la representación más corta posible. En el siguiente ejemplo se muestra el uso del especificador de formato D.

```csharp
Console.WriteLine(ConsoleColor.Cyan.ToString("D"));         // Displays 11
FileAttributes attributes = FileAttributes.Hidden |
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("D"));                // Displays 34
````

```vb
Console.WriteLine(ConsoleColor.Cyan.ToString("D"))           ' Displays 11
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("D"))                  ' Displays 34 
```

## <a name="the-x-or-x-format-strings"></a>Cadenas de formato X o x

Las cadenas de formato X o x muestran la entrada de enumeración como un valor hexadecimal. En caso necesario, el valor se representa con ceros iniciales para asegurarse de que tenga como mínimo ocho dígitos de longitud. En el siguiente ejemplo se muestra el uso del especificador de formato X.

```csharp
Console.WriteLine(ConsoleColor.Cyan.ToString("X"));   // Displays 0000000B
FileAttributes attributes = FileAttributes.Hidden |
                            FileAttributes.Archive;
Console.WriteLine(attributes.ToString("X"));          // Displays 00000022
```

```vb
Console.WriteLine(ConsoleColor.Cyan.ToString("X"))     ' Displays 0000000B
Dim attributes As FileAttributes = FileAttributes.Hidden Or _
                                   FileAttributes.Archive
Console.WriteLine(attributes.ToString("X"))            ' Displays 00000022 
```

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define una enumeración denominada `Colors` que consta de tres entradas: `Red`, `Blue` y `Green`.

 ```csharp
 public enum Color {Red = 1, Blue = 2, Green = 3}
```

```vb
Public Enum Color
   Red = 1
   Blue = 2
   Green = 3
End Enum
```

Una vez definida la enumeración, se puede declarar una instancia de la siguiente manera.

```csharp
Color myColor = Color.Green;
```

```vb
Dim myColor As Color = Color.Green
```

Luego se puede usar el método `Color.ToString(System.String)` para mostrar el valor de enumeración de maneras diferentes, según el especificador de formato pasado.

```csharp
Console.WriteLine("The value of myColor is {0}.", 
                  myColor.ToString("G"));
Console.WriteLine("The value of myColor is {0}.", 
                  myColor.ToString("F"));
Console.WriteLine("The value of myColor is {0}.", 
                  myColor.ToString("D"));
Console.WriteLine("The value of myColor is 0x{0}.", 
                  myColor.ToString("X"));
// The example displays the following output to the console:
//       The value of myColor is Green.
//       The value of myColor is Green.
//       The value of myColor is 3.
//       The value of myColor is 0x00000003.
```

```vb
Console.WriteLine("The value of myColor is {0}.", _
                  myColor.ToString("G"))
Console.WriteLine("The value of myColor is {0}.", _
                  myColor.ToString("F"))
Console.WriteLine("The value of myColor is {0}.", _
                  myColor.ToString("D"))
Console.WriteLine("The value of myColor is 0x{0}.", _
                  myColor.ToString("X"))
' The example displays the following output to the console:
'       The value of myColor is Green.
'       The value of myColor is Green.
'       The value of myColor is 3.
'       The value of myColor is 0x00000003. 
```

## <a name="see-also"></a>Vea también

[Aplicar formato a tipos](formatting-types.md)




<!--HONumber=Nov16_HO1-->


