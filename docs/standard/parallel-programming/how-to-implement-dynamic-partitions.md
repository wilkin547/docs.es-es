---
title: Procedimiento para implementar particiones dinámicas
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to create a dynamic partitioner
ms.assetid: c875ad12-a161-43e6-ad1c-3d6927c536a7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5719c6afc1c5efc6138f0a4931d1725a6f20909a
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/31/2019
ms.locfileid: "66424043"
---
# <a name="how-to-implement-dynamic-partitions"></a>Procedimiento para implementar particiones dinámicas

En el ejemplo siguiente se muestra cómo implementar una clase <xref:System.Collections.Concurrent.OrderablePartitioner%601?displayProperty=nameWithType> personalizada que implementa la partición dinámica y que puede usarse desde determinadas sobrecargas <xref:System.Threading.Tasks.Parallel.ForEach%2A> y desde PLINQ.  
  
## <a name="example"></a>Ejemplo

Cada vez que se llama a una partición <xref:System.Collections.IEnumerator.MoveNext%2A> en el enumerador, este proporciona la partición con un elemento de lista. En el caso de PLINQ y <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la partición es una instancia <xref:System.Threading.Tasks.Task>. Dado que las solicitudes se producen simultáneamente en varios subprocesos, se sincroniza el acceso al índice actual.  

[!code-csharp[TPL_Partitioners#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioner02.cs#OrderableListPartitioner)]
[!code-vb[TPL_Partitioners#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_partitioners/vb/dynamicpartitioner.vb#04)]  

Este es un ejemplo de creación de particiones por fragmentos, donde cada fragmento consta de un elemento. Proporcionando más elementos a la vez, podría reducir la contención sobre el bloqueo y teóricamente lograr un rendimiento más rápido. Sin embargo, en algún momento, los fragmentos más grandes podrían requerir lógica de equilibrio de carga adicional con el fin de mantener todos los subprocesos ocupados hasta que se completa todo el trabajo.  
  
## <a name="see-also"></a>Vea también

* [Particionadores personalizados para PLINQ y TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
* [Cómo: Implementar un particionador para particionamiento estático](../../../docs/standard/parallel-programming/how-to-implement-a-partitioner-for-static-partitioning.md)
