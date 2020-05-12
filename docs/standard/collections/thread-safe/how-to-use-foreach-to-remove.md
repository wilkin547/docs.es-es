---
title: Uso de foreach para quitar elementos de BlockingCollection
ms.date: 05/04/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collection
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
ms.openlocfilehash: 1255fcda89396ea8ff9abf6cf111e6dd9ea5a87d
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2020
ms.locfileid: "82861015"
---
# <a name="use-foreach-to-remove-items-in-a-blockingcollection"></a>Uso de foreach para quitar elementos de BlockingCollection

Además de obtener los elementos de <xref:System.Collections.Concurrent.BlockingCollection%601> mediante los métodos <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, también puede usar [foreach](../../../csharp/language-reference/keywords/foreach-in.md) ([For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) en Visual Basic) con <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> para quitar elementos hasta que se complete la adición y se vacíe la colección. Esto se denomina una *enumeración de mutación* o *enumeración de consumo* porque, a diferencia de un bucle `foreach` (`For Each`) típico, este enumerador modifica la colección de origen mediante la eliminación de elementos.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo se quitan todos los elementos de <xref:System.Collections.Concurrent.BlockingCollection%601> mediante un bucle `foreach` (`For Each`).

[!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
[!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]

Este ejemplo usa un bucle de `foreach` con el método <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> en el subproceso de consumo, lo que provoca que se quite cada elemento de la colección según se enumera. <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> limita el número máximo de elementos que se encuentran en la colección en cualquier momento. Al enumerar la colección de esta forma, bloquea el subproceso consumidor si no hay elementos disponibles o si la colección está vacía. En este ejemplo, el bloqueo no constituye un problema porque el subproceso de productor agrega elementos más rápido de lo que se pueden consumir.

<xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType> devuelve `IEnumerable<T>`, por lo que no se puede garantizar el orden. Sin embargo, internamente se usa <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> como tipo de colección subyacente, lo que quitará de la cola los objetos en orden de primero en entrar, primero en salir (FIFO, PEPS). Si se realizan llamadas simultáneas a <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=nameWithType>, competirán. Los elementos consumidos (quitados de la cola) de una enumeración no se pueden observar en la otra.

Para enumerar la colección sin modificación alguna, simplemente use `foreach` (`For Each`) sin el método <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>. Pero es importante comprender que este tipo de enumeración representa una instantánea de la colección en un momento concreto. Si otros subprocesos agregan o quitan elementos mientras se ejecuta el bucle, este no podría representar el estado real de la colección.

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Programación en paralelo](../../../../docs/standard/parallel-programming/index.md)
