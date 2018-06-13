---
title: 'Cómo: Usar matrices de colecciones de bloqueo en una canalización'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9313f1064534702fdc2d239eb7f0f69a470329e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567775"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a>Cómo: Usar matrices de colecciones de bloqueo en una canalización
En el ejemplo siguiente se muestra cómo usar matrices de objetos de <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> con métodos estáticos como <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> y <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A> para implementar una transferencia de datos rápida y flexible entre los componentes.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una implementación de canalización básica en la que cada objeto obtiene simultáneamente datos de la colección de entrada, los transforma y los pasa a la colección de salida.  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 [Colecciones seguras para subprocesos](../../../../docs/standard/collections/thread-safe/index.md)
