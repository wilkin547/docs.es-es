---
title: "C&#243;mo: Utilizar ForEach para quitar elementos de BlockingCollection | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "colecciones seguras para subprocesos, cómo enumerar colecciones de bloqueo"
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Utilizar ForEach para quitar elementos de BlockingCollection
Además de tomar elementos de una clase <xref:System.Collections.Concurrent.BlockingCollection%601> mediante los métodos <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A>, también puede usar [foreach](../Topic/foreach,%20in%20\(C%23%20Reference\).md) \([For Each](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md) en Visual Basic\) para quitar elementos hasta que se complete la operación de agregar y la colección esté vacía.  Esto se denomina *enumeración mutable* o *enumeración consumidora* porque, a diferencia de un bucle `foreach` \(`For Each`\) típico, este enumerador modifica la colección de origen quitando elementos.  
  
## Ejemplo  
 En el siguiente ejemplo, se muestra cómo quitar todos los elementos de una <xref:System.Collections.Concurrent.BlockingCollection%601> mediante un bucle `foreach` \(`For Each`\).  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 En este ejemplo, se utiliza un bucle `foreach` con el método <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> en el subproceso consumidor, por lo que se quita cada elemento de la colección en cuanto se enumera.  <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> limita el número máximo de elementos de la colección.  Al enumerar la colección de esta manera, se bloquea el subproceso consumidor si no hay elementos disponibles o si la colección está vacía.  En este ejemplo el bloqueo no supone ningún problema, ya que el subproceso de productor agrega elementos más rápido de lo que se pueden usar.  
  
 No hay ninguna garantía de que los elementos se enumeren en el mismo orden en que los subprocesos productores los agregan.  
  
 Para enumerar la colección sin modificarla, use `foreach` \(`For Each`\) sin el método <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>.  Sin embargo, es importante entender que este tipo de enumeración representa una instantánea de la colección en un momento concreto.  Si otros subprocesos agregan o quitan elementos mientras se ejecuta el bucle, es posible que el bucle no represente el estado real de la colección.  
  
## Vea también  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Parallel Programming](../../../../docs/standard/parallel-programming/index.md)