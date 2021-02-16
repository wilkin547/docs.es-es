---
title: Tipos básicos
description: 'Descubra los tipos básicos fundamentales que se usan en el lenguaje F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 2bfc9ba9370cb8ba1fcc1d42369c2551cbb57623
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456918"
---
# <a name="basic-types"></a>Tipos básicos

En este tema se enumeran los tipos básicos que se definen en el lenguaje F #. Estos tipos son los más fundamentales en F #, que forman la base de casi todos los programas de F #. Son un superconjunto de tipos primitivos de .NET.

|Tipo|Tipo de .NET|Descripción|Ejemplo|
|----|---------|-----------|-------|
|`bool`|<xref:System.Boolean>|Los valores posibles son `true` y `false`.|`true`/`false`|
|`byte`|<xref:System.Byte>|Valores de 0 a 255.|`1uy`|
|`sbyte`|<xref:System.SByte>|Valores de-128 a 127.|`1y`|
|`int16`|<xref:System.Int16>|Valores de-32768 a 32767.|`1s`|
|`uint16`|<xref:System.UInt16>|Valores de 0 a 65535.|`1us`|
|`int`|<xref:System.Int32>|Valores de-2.147.483.648 a 2.147.483.647.|`1`|
|`uint`|<xref:System.UInt32>|Valores de 0 a 4.294.967.295.|`1u`|
|`int64`|<xref:System.Int64>|Valores de-9223372036854775808 a 9.223.372.036.854.775.807.|`1L`|
|`uint64`|<xref:System.UInt64>|Valores de 0 a 18446744073709551615.|`1UL`|
|`nativeint`|<xref:System.IntPtr>|Puntero nativo como entero con signo.|`nativeint 1`|
|`unativeint`|<xref:System.UIntPtr>|Puntero nativo como entero sin signo.|`unativeint 1`|
|`decimal`|<xref:System.Decimal>|Un tipo de datos de punto flotante que tiene al menos 28 dígitos significativos.|`1.0`|
|`float`, `double`|<xref:System.Double>|Tipo de punto flotante de 64 bits.|`1.0`|
|`float32`, `single`|<xref:System.Single>|Tipo de punto flotante de 32 bits.|`1.0f`|
|`char`|<xref:System.Char>|Valores de caracteres Unicode.|`'c'`|
|`string`|<xref:System.String>|Texto Unicode.|`"str"`|
|`unit`|no aplicable|Indica la ausencia de un valor real. El tipo solo tiene un valor formal, que se indica `()` . El valor de unidad, `()` , se usa a menudo como un marcador de posición en el que se necesita un valor, pero no hay ningún valor real disponible o tiene sentido.|`()`|

> [!NOTE]
> Puede realizar cálculos con enteros demasiado grandes para el tipo entero de 64 bits mediante el `bigint` tipo. `bigint` no se considera un tipo básico; es una abreviatura de `System.Numerics.BigInteger` .

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
