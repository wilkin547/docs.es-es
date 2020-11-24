---
title: 'Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking dictionary
ms.assetid: 38f2f3d8-15e5-4bf4-9c83-2b5b6f22bad1
ms.openlocfilehash: 5501e108d1866fc1ae6fc66f9fe665b63373414b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818640"
---
# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a>Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection
Este ejemplo muestra cómo agregar y quitar elementos de <xref:System.Collections.Concurrent.BlockingCollection%601> con bloqueo y sin bloqueo. Para obtener más información sobre <xref:System.Collections.Concurrent.BlockingCollection%601>, consulte [Información general sobre BlockingCollection](blockingcollection-overview.md).  
  
 Para obtener un ejemplo de cómo enumerar un elemento <xref:System.Collections.Concurrent.BlockingCollection%601> hasta que esté vacío y que así no se agreguen más elementos, consulte [Cómo: Utilizar ForEach para quitar elementos de BlockingCollection](how-to-use-foreach-to-remove.md).
  
## <a name="example"></a>Ejemplo  
 En este primer ejemplo se muestra cómo agregar y quitar elementos para que las operaciones se bloqueen si la colección está temporalmente vacía (al quitarla) o en su capacidad máxima (al agregarla), o si ha transcurrido el período de tiempo de espera especificado. Tenga en cuenta que el bloqueo en capacidad máxima solo se habilita cuando el elemento BlockingCollection se crea con una capacidad máxima especificada en el constructor.  
  
 [!code-csharp[CDS_BlockingCollection#01](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example01.cs#01)]
 [!code-vb[CDS_BlockingCollection#01](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/simpleblocking.vb#01)]  
  
## <a name="example"></a>Ejemplo  
 En este segundo ejemplo se muestra cómo agregar y quitar elementos para que las operaciones no se bloqueen. Si no hay ningún elemento o si se ha alcanzado la capacidad máxima de una colección limitada, o si el periodo de tiempo de espera ya ha transcurrido, la operación <xref:System.Collections.Concurrent.BlockingCollection%601.TryAdd%2A> o <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A> devuelve el resultado “false”. Esto permite al subproceso hacer algún otro trabajo útil durante un rato, para después volver a intentar recuperar un nuevo elemento o intentar agregar el elemento que no se pudo agregar previamente. Asimismo, el programa también muestra cómo implementar la cancelación cuando se tiene acceso al elemento <xref:System.Collections.Concurrent.BlockingCollection%601>.  
  
 [!code-csharp[CDS_BlockingCollection#02](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example02.cs#02)]
 [!code-vb[CDS_BlockingCollection#02](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/nonblockingbc.vb#02)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Información general sobre BlockingCollection](blockingcollection-overview.md)
