---
title: "Cambiar mayúsculas y minúsculas"
description: "Cambiar mayúsculas y minúsculas"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 646c5afd-8aec-4393-9c00-f68ad2580c68
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 023f40969095627242d3652add853eb999c30c4b
ms.lasthandoff: 03/02/2017

---

# <a name="changing-case"></a>Cambiar mayúsculas y minúsculas

Si escribe una aplicación que acepta la entrada de un usuario, nunca podrá estar seguro de si usará mayúsculas o minúsculas para escribir los datos. Normalmente querrá que las cadenas usen mayúsculas y minúsculas de forma coherente, especialmente si se van a mostrar en la interfaz de usuario. En la tabla siguiente, se describen dos métodos para cambiar las mayúsculas y minúsculas.

Nombre del método | Uso
----------- | ---
[String.ToUpper](xref:System.String.ToUpper) | Convierte todos los caracteres de una cadena a mayúsculas.
[String.ToLower](xref:System.String.ToLower) | Convierte todos los caracteres de una cadena a minúsculas.

> [!WARNING]  
> Tenga en cuenta que los métodos `String.ToUpper` y `String.ToLower` no deben usarse para convertir cadenas para compararlas ni para comprobar su igualdad. 

## <a name="comparing-strings-of-mixed-case"></a>Comparar cadenas con mayúsculas y minúsculas mezcladas

Para comparar cadenas con mayúsculas y minúsculas mezcladas para determinar si son iguales, llame a una de las sobrecargas del método [String](xref:System) `Equals` con un parámetro *comparisonType* y proporcione un valor de [StringComparison.CurrentCultureIgnoreCase](xref:System.StringComparison.CurrentCultureIgnoreCase) o [StringComparison.OrdinalIgnoreCase](xref:System.StringComparison.OrdinalIgnoreCase) para el argumento *comparisonType*. 

Para obtener más información, consulte [Procedimientos recomendados para el uso de cadenas](best-practices.md). 

## <a name="toupper"></a>ToUpper

El método [String.ToUpper](xref:System.String.ToUpper) convierte todos los caracteres de una cadena en mayúsculas. En el siguiente ejemplo, se convierte la cadena "Hello World!" de mayúsculas y minúsculas mezcladas a mayúsculas.

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToUpper());
// This example displays the following output:
//       HELLO WORLD!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToUpper())
' This example displays the following output:
'       HELLO WORLD!
```

## <a name="tolower"></a>ToLower

El método [String.ToLower](xref:System.String.ToLower) es similar al método anterior, pero, en su lugar, convierte todos los caracteres de una cadena en minúsculas. En el siguiente ejemplo, se convierte la cadena "Hello World!" en minúsculas.

```csharp
string properString = "Hello World!";
Console.WriteLine(properString.ToLower());
// This example displays the following output:
//       hello world!
```

```vb
Dim MyString As String = "Hello World!"
Console.WriteLine(MyString.ToLower())
' This example displays the following output:
'       hello world!
```

## <a name="see-also"></a>Vea también

[Operaciones básicas de cadenas](basic-string-operations.md)

