---
title: 'Cómo: Sincronizar operaciones simultáneas con una clase Barrier'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
ms.openlocfilehash: dc0955ba6194dd936da19c634ada797d6cbd3720
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716478"
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a>Cómo: Sincronizar operaciones simultáneas con una clase Barrier

En el ejemplo siguiente se muestra cómo sincronizar tareas simultáneas con <xref:System.Threading.Barrier>.  
  
## <a name="example"></a>Ejemplo  

 El propósito del programa siguiente es contar cuántas iteraciones o fases son necesarias para que dos subprocesos busquen cada uno su mitad de la solución en la misma fase utilizando un algoritmo aleatorio para reorganizar las palabras. Después de que cada subproceso haya ordenado sus palabras, la operación de barrera posterior a la fase compara los dos resultados para ver si la oración completa se ha representado en el orden de palabras correcto.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <xref:System.Threading.Barrier> es un objeto que impide que las tareas individuales de una operación paralela continúen hasta que todas las tareas alcancen la barrera. Resulta útil cuando se produce una operación paralela en fases y cada fase requiere sincronización entre las tareas. En este ejemplo, hay dos fases para la operación. En la primera fase, cada tarea rellena su sección del búfer con datos. Cuando cada tarea termina de rellenar su sección, la tarea señala la barrera que está lista para continuar y, a continuación, espera. Cuando todas las tareas han señalado la barrera, se desbloquean y comienza la segunda fase. La barrera es necesaria porque la segunda fase requiere que cada tarea tenga acceso a todos los datos generados para este punto. Sin la barrera, las primeras tareas en completarse pueden intentar leer de búferes que otras tareas aún no completaron. Puede sincronizar cualquier número de fases de esta manera.  
  
## <a name="see-also"></a>Vea también

- [Estructuras de datos para la programación paralela](../parallel-programming/data-structures-for-parallel-programming.md)
