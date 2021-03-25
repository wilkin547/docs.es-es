---
title: 'Procedimiento Utilizar punteros para copiar una matriz de bytes: Guía de programación de C#'
description: Aprenda a usar punteros para copiar una matriz de bytes Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: f0122d29729ac8ad634f39f0643902e9bb78a8a5
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478602"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes-c-programming-guide"></a>Procedimiento Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)

En el ejemplo siguiente se usan punteros para copiar bytes de una matriz a otra.

En este ejemplo se usa la palabra clave [unsafe](../../language-reference/keywords/unsafe.md), que permite el uso de punteros en el método `Copy`. La instrucción [fixed](../../language-reference/keywords/fixed-statement.md) se usa para declarar punteros a las matrices de origen y destino. La instrucción `fixed`*ancla* la ubicación de las matrices de origen y destino en memoria, para que no puedan ser desplazadas por la recolección de elementos no utilizados. Estos bloques de memoria para las matrices se desanclan cuando finaliza el bloque `fixed`. Como el método `Copy` de este ejemplo usa la palabra clave `unsafe`, se debe compilar con la opción del compilador [**AllowUnsafeBlocks**](../../language-reference/compiler-options/language.md#allowunsafeblocks).

Este ejemplo accede a los elementos de ambas matrices con índices en lugar de con un segundo puntero no administrado. La declaración de los punteros `pSource` y `pTarget` ancla las matrices. Esta característica está disponible a partir de C# 7.3.

## <a name="example"></a>Ejemplo

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Código no seguro y punteros](index.md)
- [**AllowUnsafeBlocks** (opciones del compilador de C#)](../../language-reference/compiler-options/language.md#allowunsafeblocks)
- [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)
