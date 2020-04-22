---
title: 'Tipos integrados: referencia de C#'
description: Información sobre los tipos de referencia y de valor integrados de C#
ms.date: 02/04/2020
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: bf8823c6674b1ff3f0028a50df8ce8d0f803cfc1
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389490"
---
# <a name="built-in-types-c-reference"></a>Tipos integrados (referencia de C#)

En la siguiente tabla se muestran los tipos de [valor](value-types.md) de C#:

|Palabra clave de tipo de C#|Tipo de .NET|
|--------------|-------------------------|
|[`bool`](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|
|[`byte`](integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|
|[`sbyte`](integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|
|[`char`](char.md)|<xref:System.Char?displayProperty=nameWithType>|
|[`decimal`](floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|
|[`double`](floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|
|[`float`](floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|
|[`int`](integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|
|[`uint`](integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

En la siguiente tabla se muestran los tipos de [referencia](../keywords/reference-types.md) integrados de C#:

|Palabra clave de tipo de C#|Tipo de .NET|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|

En las tablas anteriores, cada palabra clave de tipo de C# de la columna ubicada a la izquierda es un alias del tipo de .NET correspondiente. Son intercambiables. Por ejemplo, en las declaraciones siguientes se declaran variables del mismo tipo:

```csharp
int a = 123;
System.Int32 b = 123;
```

La palabra clave [`void`](void.md) representa la ausencia de un tipo. Se usa como el tipo de valor devuelto de un método que no devuelve un valor.

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Valores predeterminados de los tipos de C#](default-values.md)
- [Palabra clave `dynamic`](reference-types.md#the-dynamic-type)
