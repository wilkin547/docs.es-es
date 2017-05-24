---
title: "Cómo utilizar ForEach para quitar elementos de BlockingCollection | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88d36d440b6a1d79f978e2cf39bbe2cde241af6b
ms.lasthandoff: 04/18/2017

---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a>Cómo: Utilizar ForEach para quitar elementos de BlockingCollection
Además de adoptar elementos de <xref:System.Collections.Concurrent.BlockingCollection%601> con la utilización del método <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, también puede usar [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) en Visual Basic) para quitar elementos hasta que la adición se haya completado y la colección esté vacía. Esto se denomina una *enumeración de mutación* o *enumeración de consumo* porque, a diferencia de un bucle `foreach` (`For Each`) típico, este enumerador modifica la colección de origen mediante la eliminación de elementos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo quitar todos los elementos de <xref:System.Collections.Concurrent.BlockingCollection%601> mediante un bucle `foreach` (`For Each`).  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 En este ejemplo se usa un bucle `foreach` con el método <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> en el subproceso de consumidor, lo que da lugar a que se quite cada elemento de la colección como se ha enumerado. <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> limita el número máximo de elementos que se encuentran en la colección en cualquier momento. Al enumerar la colección de esta forma, bloquea el subproceso consumidor si no hay elementos disponibles o si la colección está vacía. En este ejemplo, el bloqueo no constituye un problema porque el subproceso de productor agrega elementos más rápido de lo que se pueden consumir.  
  
 No hay ninguna garantía de que los elementos se enumeren en el mismo orden en que los agregan los subprocesos de productor.  
  
 Para enumerar la colección sin modificarla, use `foreach` (`For Each`) sin el método <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>. Pero es importante comprender que este tipo de enumeración representa una instantánea de la colección en un momento concreto. Si otros subprocesos agregan o quitan elementos mientras se ejecuta el bucle, este no podría representar el estado real de la colección.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Programación en paralelo](../../../../docs/standard/parallel-programming/index.md)
