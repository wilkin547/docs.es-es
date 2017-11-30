---
title: "Cómo: Implementar un particionador para particionamiento estático"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b28ff0bb8436fefc4956918889435e258ae98b12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>Cómo: Implementar un particionador para particionamiento estático
En el ejemplo siguiente se muestra una manera de implementar a un particionador personalizado simple para PLINQ que realiza la partición estática. Dado que el particionador no admite las particiones dinámicas, no resulta Dese <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Este particionador determinado podría proporcionar velocidad sobre el particionador de intervalo predeterminado para los orígenes de datos para el que cada elemento necesita una cantidad creciente de tiempo de procesamiento.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 Las particiones en este ejemplo se basan en el supuesto de un aumento lineal en tiempo de procesamiento para cada elemento. En el mundo real, puede que sea difícil de predecir los tiempos de procesamiento de esta manera. Si usas un particionador estático con un origen de datos concreto, puede optimizar la fórmula de partición para el origen, agregar lógica de equilibrio de carga o usar un fragmento enfoque de partición como se muestra en [Cómo: implementar las particiones dinámicas](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>Vea también  
 [Particionadores personalizados para PLINQ y TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
