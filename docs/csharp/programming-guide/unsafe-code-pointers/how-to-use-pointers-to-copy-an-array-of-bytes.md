---
title: 'Cómo: Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)'
ms.date: 04/20/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6e87a2ec2c04812ac9b998c4c6d9a18d1b097342
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a>Cómo: Utilizar punteros para copiar una matriz de bytes (Guía de programación de C#)

En el ejemplo siguiente se usan punteros para copiar bytes de una matriz a otra.

En este ejemplo se usa la palabra clave [unsafe](../../language-reference/keywords/unsafe.md), que permite el uso de punteros en el método `Copy`. La instrucción [fixed](../../language-reference/keywords/fixed-statement.md) se usa para declarar punteros a las matrices de origen y destino. La instrucción `fixed` *ancla* la ubicación de las matrices de origen y destino en memoria, para que no puedan ser desplazadas por la recolección de elementos no utilizados. Estos bloques de memoria para las matrices se desanclan cuando finaliza el bloque `fixed`. Dado que el método `Copy` de este ejemplo usa la palabra clave `unsafe`, se debe compilar con la opción del compilador [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).

Este ejemplo accede a los elementos de ambas matrices con índices en lugar de con un segundo puntero no administrado. La declaración de los punteros `pSource` y `pTarget` ancla las matrices. Esta característica está disponible a partir de C# 7.3.

## <a name="example"></a>Ejemplo

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a>Vea también
 [Guía de programación de C#](../index.md)  
 [Código no seguro y punteros](index.md)  
 [-unsafe (Opciones del compilador de C#)](../../language-reference/compiler-options/unsafe-compiler-option.md)  
 [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)  
