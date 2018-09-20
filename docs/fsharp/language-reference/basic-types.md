---
title: 'Tipos básicos (F #)'
description: 'Descubra los tipos básicos fundamentales que se usan en el lenguaje F #.'
ms.date: 07/09/2018
ms.openlocfilehash: 8f948d066323527b09b1d3f9f4167b95b1c875cf
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46480739"
---
# <a name="basic-types"></a>Tipos básicos

En este tema se enumera los tipos básicos que se definen en el lenguaje F #. Estos tipos son más importantes en F #, que forman la base de casi todos los programas F #. Son un superconjunto de los tipos primitivos. NET.

|Tipo|Tipo de .NET|Descripción|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|Los valores posibles son `true` y `false`.|
|`byte`|<xref:System.Byte>|Valores de 0 a 255.|
|`sbyte`|<xref:System.SByte>|Valores de -128 a 127.|
|`int16`|<xref:System.Int16>|Valores de -32768 a 32767.|
|`uint16`|<xref:System.UInt16>|Valores de 0 a 65535.|
|`int`|<xref:System.Int32>|Valores entre -2.147.483.648 a 2.147.483.647.|
|`uint32`|<xref:System.UInt32>|Valores entre 0 y 4.294.967.295.|
|`int64`|<xref:System.Int64>|Valores comprendidos entre -9.223.372.036.854.775.808 a + 9.223.372.036.854.775.807.|
|`uint64`|<xref:System.UInt64>|Valores de 0 a 18,446,744,073,709,551,615.|
|`nativeint`|<xref:System.IntPtr>|Un puntero nativo como un entero con signo.|
|`unativeint`|<xref:System.UIntPtr>|Un puntero nativo como un entero sin signo.|
|`char`|<xref:System.Char>|Valores de caracteres Unicode.|
|`string`|<xref:System.String>|Texto Unicode.|
|`decimal`|<xref:System.Decimal>|Tipo de datos que tiene al menos 28 dígitos significativos de punto flotante.|
|`unit`|No aplicable|Indica la ausencia de un valor real. El tipo tiene un único valor formal, que se indica `()`. El valor de unidad, `()`, a menudo se usa como marcador de posición donde se necesita un valor pero ningún valor real está disponible o que tenga sentido.|
|`void`|<xref:System.Void>|No indica que ningún tipo de valor.|
|`float32`, `single`|<xref:System.Single>|Tipo de punto flotante de 32 bits.|
|`float`, `double`|<xref:System.Double>|Tipo de punto flotante de 64 bits.|

>[!NOTE]
Puede realizar cálculos con números enteros demasiado grandes para el tipo de entero de 64 bits mediante el [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) tipo. `bigint` no se considera un tipo básico; es la abreviatura de `System.Numerics.BigInteger`.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
