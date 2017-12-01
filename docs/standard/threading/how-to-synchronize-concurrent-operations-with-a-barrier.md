---
title: "Cómo: Sincronizar operaciones simultáneas con una clase Barrier"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a>Cómo: Sincronizar operaciones simultáneas con una clase Barrier
En el ejemplo siguiente se muestra cómo sincronizar tareas simultáneas con una <xref:System.Threading.Barrier>.  
  
## <a name="example"></a>Ejemplo  
 El propósito del programa siguiente es para contar cuántas iteraciones (o fases) son necesarios para dos subprocesos busquen cada uno su mitad de la solución en la misma fase utilizando un algoritmo de aleatoriedad para reorganizar las palabras. Después de que cada subproceso se ordenan aleatoriamente sus palabras, la operación de barrera de posterior a la fase compara los dos resultados para ver si la frase completa se ha representado en el orden correcto de las palabras.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 A <xref:System.Threading.Barrier> es un objeto que impide que las tareas individuales en una operación paralela continúen hasta que todas las tareas alcancen la barrera. Resulta útil cuando se produce una operación en paralelo en fases y cada fase requiere sincronización entre las tareas. En este ejemplo, hay dos fases para la operación. En la primera fase, cada tarea rellena su sección del búfer con datos. Cuando cada tarea termina de rellenar su sección, la tarea señala la barrera que está listo para continuar y, a continuación, espera. Cuando todas las tareas han señalizado la barrera, se desbloquean y comienza la segunda fase. La barrera es necesaria porque la segunda fase requiere que cada tarea tenga acceso a todos los datos que se ha generado para este punto. Sin la barrera, las primeras tareas en completarse que pueden intentar leer de búferes que no se completaron aún por otras tareas. Puede sincronizar cualquier número de fases de esta manera.  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de datos para la programación paralela](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
