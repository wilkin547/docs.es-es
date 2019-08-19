---
title: 'Tabla de tipos integrados: Referencia de C#'
ms.custom: seodec18
description: Palabras clave para tipos integrados de C#
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 61701cc38c38b5e7235fbadb6d2a86e0e66b09ac
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69566363"
---
# <a name="built-in-types-table-c-reference"></a>Tabla de tipos integrados (Referencia de C#)

En la siguiente tabla se muestran las palabras clave para los tipos de C# integrados, que son alias de los tipos predefinidos en el espacio de nombres <xref:System>.  
  
|Tipo de C#|Tipo de .NET|  
|--------------|-------------------------|  
|[bool](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[byte](../builtin-types/integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[sbyte](../builtin-types/integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[char](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[decimal](../builtin-types/floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[double](../builtin-types/floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[float](../builtin-types/floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[int](../builtin-types/integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[uint](../builtin-types/integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[long](../builtin-types/integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[ulong](../builtin-types/integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[object](object.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[short](../builtin-types/integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[ushort](../builtin-types/integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[string](string.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a>Comentarios

A todos los tipos de la tabla, excepto `object` y `string`, se les hace referencia como tipos simples.  
  
Los tipos de .NET y sus alias de palabra clave de tipo de C# son intercambiables. Por ejemplo, puede declarar una variable de entero con cualquiera de las siguientes declaraciones:  

```csharp
int x = 123;
System.Int32 y = 123;
```

Use el operador [typeof](../operators/type-testing-and-cast.md#typeof-operator) para obtener la instancia <xref:System.Type?displayProperty=nameWithType> que representa el tipo especificado:

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Tipos de valor](value-types.md)
- [Tipos de referencia](reference-types.md)
- [Tabla de valores predeterminados](default-values-table.md)
- [dynamic](dynamic.md)
