---
description: volatile - Referencia de C#
title: volatile - Referencia de C#
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: bb89e99e8e28ff1e263817f498619dbfae700a50
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141704"
---
# <a name="volatile-c-reference"></a>volatile (Referencia de C#)

La palabra clave `volatile` indica que un campo puede ser modificado por varios subprocesos que se ejecutan al mismo tiempo. El compilador, el sistema de runtime e incluso el hardware pueden reorganizar las lecturas y escrituras en las ubicaciones de memoria por motivos de rendimiento. Los campos que se declaran `volatile` no están sujetos a estas optimizaciones. La incorporación del modificador `volatile` asegura que todos los subprocesos observarán las operaciones de escritura volátiles realizadas por cualquier otro subproceso en el orden en que se realizaron. No hay ninguna garantía de una única ordenación total de las operaciones de escritura volátiles como se muestra en todos los subprocesos de ejecución.

La palabra clave `volatile` se puede aplicar a campos de estos tipos:

- Tipos de referencia.
- Tipos de puntero (en un contexto no seguro). Observe que aunque el propio puntero puede ser volatile, no el objeto al que apunta. Es decir, no puede declarar un "puntero a volatile".
- Tipos simples como `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float` y `bool`.
- Un tipo `enum` con uno de los siguientes tipos base: `byte`, `sbyte`, `short`, `ushort`, `int` o `uint`.
- Parámetros de tipo genérico que se sabe que son tipos de referencia.
- <xref:System.IntPtr> y <xref:System.UIntPtr>.

Otros tipos, incluidos `double` y `long`, no pueden marcarse como `volatile` porque no se puede garantizar que las lecturas y escrituras los campos de esos tipos sean atómicas. Para proteger el acceso multiproceso a esos tipos de campos, use los miembros de clase <xref:System.Threading.Interlocked> o proteja el acceso mediante la instrucción [`lock`](lock-statement.md).

La palabra clave `volatile` solo se puede aplicar a campos de `class` o `struct`. Las variables locales no se pueden declarar como `volatile`.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo declarar una variable de campo pública como `volatile`.

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

En el ejemplo siguiente se muestra cómo crear un subproceso auxiliar o de trabajo y usarlo para realizar el procesamiento en paralelo con el del subproceso principal. Para más información sobre el multithreading, vea [Subprocesamiento administrado](../../../standard/threading/index.md).

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

Con el modificador `volatile` que se agrega a la declaración de `_shouldStop` en su lugar, siempre obtendrá los mismos resultados (similar al fragmento que se muestra en el código anterior). Sin embargo, sin ese modificador en el miembro `_shouldStop`, el comportamiento es imprevisible. El método `DoWork` puede optimizar el acceso a los miembros, lo que provoca la lectura de datos obsoletos. Dada la naturaleza de la programación multiproceso, el número de lecturas obsoletas es imprevisible. Distintas ejecuciones del programa generarán resultados ligeramente diferentes.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Especificación del lenguaje C#: palabra clave volatile](../../../../_csharplang/spec/classes.md#volatile-fields)
- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Palabras clave de C#](index.md)
- [Modificadores](index.md)
- [lock (Instrucción)](lock-statement.md)
- <xref:System.Threading.Interlocked>
