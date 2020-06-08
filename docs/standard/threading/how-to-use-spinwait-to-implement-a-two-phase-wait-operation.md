---
title: 'Cómo: Usar SpinWait para implementar una operación de espera de dos fases'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
ms.openlocfilehash: 4b2bc79a7b652c34334d5a78d9c9af328993ff44
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84279211"
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>Cómo: Usar SpinWait para implementar una operación de espera de dos fases
En el ejemplo siguiente se muestra cómo utilizar un objeto <xref:System.Threading.SpinWait?displayProperty=nameWithType> para implementar una operación de espera de dos fases. En la primera fase, el objeto de sincronización, `Latch`, gira durante unos ciclos mientras comprueba si el bloqueo está disponible. En la segunda fase, si el bloqueo está disponible, el método `Wait` realiza la devolución sin usar <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> para la espera; en caso contrario, `Wait` realiza la espera.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra una implementación muy básica de un elemento primitivo de sincronización de bloqueo temporal. Puede usar esta estructura de datos cuando se prevé que los tiempos de espera sean muy cortos. Este ejemplo solamente sirve de demostración. Si necesita una funcionalidad de tipo de bloqueo temporal en el programa, considere la posibilidad de usar <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 El bloqueo temporal usa el objeto <xref:System.Threading.SpinWait> para girar in situ hasta que la siguiente llamada a `SpinOnce` da lugar a que <xref:System.Threading.SpinWait> produzca el intervalo de tiempo del subproceso. En ese momento, el bloqueo temporal produce su propio cambio de contexto mediante una llamada a <xref:System.Threading.WaitHandle.WaitOne%2A> en <xref:System.Threading.ManualResetEvent> y pasa el resto del valor de tiempo de espera.  
  
 La salida del registro muestra la frecuencia con que el bloqueo temporal pudo aumentar el rendimiento mediante la adquisición del bloqueo sin usar <xref:System.Threading.ManualResetEvent>.  
  
## <a name="see-also"></a>Vea también

- [SpinWait](spinwait.md)
- [Objetos y características de subprocesos](threading-objects-and-features.md)
