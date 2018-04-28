---
title: Tipos primitivos (F#)
description: 'Detectar los tipos primitivos fundamentales que se utilizan en el lenguaje F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 7832151ee211f56547ecad98fc31f1454cb18870
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="primitive-types"></a>Tipos primitivos

Este tema enumeran los tipos primitivos fundamentales que se utilizan en el lenguaje F #. También se proporcionan los tipos de .NET correspondientes y los valores máximos y mínimos para cada tipo.

## <a name="summary-of-primitive-types"></a>Resumen de tipos primitivos
En la tabla siguiente se resume las propiedades de los tipos primitivos de F #.

|Tipo|Tipo de .NET|Descripción|
|----|---------|-----------|
|`bool`|`System.Boolean`|Los valores posibles son `true` y `false`.|
|`byte`|`System.Byte`|Valores de 0 a 255.|
|`sbyte`|`System.SByte`|Valores de -128 a 127.|
|`int16`|`System.Int16`|Valores de -32768 a 32767.|
|`uint16`|`System.UInt16`|Valores de 0 a 65535.|
|`int`|`System.Int32`|Valores de -2.147.483.648 a 2.147.483.647.|
|`uint32`|`System.UInt32`|Valores de 0 a 4.294.967.295.|
|`int64`|`System.Int64`|Valores de -9.223.372.036.854.775.808 a 9.223.372.036.854.775.807.|
|`uint64`|`System.UInt64`|Valores de 0 a 18.446.744.073.709.551.615.|
|`nativeint`|`System.IntPtr`|Un puntero nativo como un entero con signo.|
|`unativeint`|`System.UIntPtr`|Un puntero nativo como un entero sin signo.|
|`char`|`System.Char`|Valores de caracteres Unicode.|
|`string`|`System.String`|Texto Unicode.|
|`decimal`|`System.Decimal`|Tipo de datos que tiene al menos 28 dígitos significativos de punto flotante.|
|`unit`|No aplicable|Indica la ausencia de un valor real. El tipo tiene un único valor formal, que se indica `()`. El valor de la unidad, `()`, a menudo se utiliza como un marcador de posición donde se necesita un valor pero ningún valor real está disponible o tiene sentido.|
|`void`|`System.Void`|No indica que ningún tipo o valor.|
|`float32, single`|`System.Single`|Tipo de punto flotante de 32 bits.|
|`float, double`|`System.Double`|Tipo de punto flotante de 64 bits.|

>[!NOTE]
Puede realizar cálculos con enteros demasiado grandes para el tipo de entero de 64 bits mediante el [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) tipo. `bigint` no se considera un tipo primitivo; es una abreviatura de `System.Numerics.BigInteger`.

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)
