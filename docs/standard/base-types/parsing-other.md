---
title: Analizar otras cadenas en .NET
description: Analizar otras cadenas en .NET
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 67670b10-3df4-45ea-8908-5ba3f056887c
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 3f26670dc9f4c6b6608599793352445d5665cf64

---

# <a name="parsing-other-strings-in-net"></a>Analizar otras cadenas en .NET

Además de cadenas numéricas y [DateTime](xref:System.DateTime), puede analizar cadenas que representan los tipos [Char](xref:System.Char), [Boolean](xref:System.Boolean) y [Enum](xref:System.Enum) en tipos de datos.

## <a name="char"></a>Char

El método de análisis estático asociado con el tipo de datos [Char](xref:System.Char) es útil para convertir una cadena que contiene un único carácter en su valor Unicode. En el ejemplo de código siguiente se analiza una cadena en un carácter Unicode.

```csharp
string MyString1 = "A";
char MyChar = Char.Parse(MyString1);
// MyChar now contains a Unicode "A" character.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="boolean"></a>Booleano

El tipo de datos [Boolean](xref:System.Boolean) contiene un método [Parse](xref:System.Boolean.Parse(System.String)) que se puede usar para convertir una cadena que representa un valor `Boolean` en un tipo `Boolean` real. Este método no distingue mayúsculas de minúsculas y puede analizar correctamente una cadena que contenga "True" o "False". El método `Parse` asociado al tipo `Boolean` también puede analizar cadenas que estén rodeadas por espacios en blanco. Si se pasa otra cadena, se produce una excepción [FormatException](xref:System.FormatException).

En el ejemplo de código siguiente se usa el método `Parse` para convertir una cadena en un valor `Boolean`.

```csharp
string MyString2 = "True";
bool MyBool = bool.Parse(MyString2);
// MyBool now contains a True Boolean value.
```

```vb
Dim MyString1 As String = "A"
Dim MyChar As Char = Char.Parse(MyString1)
' MyChar now contains a Unicode "A" character.
```

## <a name="enumeration"></a>Enumeración

Puede usar el método [Parse](xref:System.Enum.Parse(System.Type,System.String)) estático para inicializar un tipo de enumeración en el valor de una cadena. Este método acepta el tipo de enumeración que se está analizando, la cadena que se va a analizar y una marca `Boolean` opcional que indica si el análisis distingue mayúsculas de minúsculas. La cadena que se va a analizar puede contener varios valores separados por comas, que pueden ir precedidos o seguidos de uno o varios espacios vacíos (también denominados espacios en blanco). Cuando la cadena contiene varios valores, el valor del objeto devuelto es el valor de todos los valores especificados combinados con una operación OR bit a bit.

En el ejemplo siguiente se usa el método `Parse` para convertir una representación de cadena en un valor de enumeración. La enumeración [DayOfWeek](xref:System.DayOfWeek) se inicializa en Thursday desde una cadena.

```csharp
string MyString3 = "Thursday";
DayOfWeek MyDays = (DayOfWeek)Enum.Parse(typeof(DayOfWeek), MyString3);
Console.WriteLine(MyDays);
// The result is Thursday.
```

```vb
Dim MyString3 As String = "Thursday"
Dim MyDays As DayOfWeek = CType([Enum].Parse(GetType(DayOfWeek), MyString3), DayOfWeek)
Console.WriteLine("{0:G}", MyDays)
' The result is Thursday.
```

## <a name="see-also"></a>Vea también

[Analizar cadenas en .NET](parsing-strings.md)

[Aplicar formato a tipos en .NET](formatting-types.md)

[Conversión de tipos en .NET](type-conversion.md)




<!--HONumber=Nov16_HO1-->


