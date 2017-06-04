---
title: "How to: Use SpinWait to Implement a Two-Phase Wait Operation | Microsoft Docs"
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
  - "SpinWait, how to synchronize two-phase wait"
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Use SpinWait to Implement a Two-Phase Wait Operation
En el siguiente ejemplo se muestra cómo utilizar un objeto <xref:System.Threading.SpinWait?displayProperty=fullName> para implementar una operación de espera de dos fases.  En la primera fase, el objeto de sincronización, `Latch`, gira durante unos ciclos mientras comprueba si el bloqueo está disponible.  En la segunda fase, si el bloqueo está disponible, el método `Wait` vuelve sin utilizar <xref:System.Threading.ManualResetEvent?displayProperty=fullName> para realizar su espera; de lo contrario, `Wait` realiza la espera.  
  
## Ejemplo  
 En este ejemplo, se muestra una implementación muy básica de una primitiva de sincronización de Latch.  Puede utilizar esta estructura de datos mientras se prevé que los tiempos de espera sean muy cortos.  El único fin de este ejemplo es usarlo para realizar una demostración.  Si necesita una funcionalidad de tipo bloqueo temporal en el programa, considere la posibilidad de utilizar <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 El bloqueo temporal utiliza el objeto <xref:System.Threading.SpinWait> para girar en su posición solo hasta que la llamada siguiente a `SpinOnce` haga que <xref:System.Threading.SpinWait> genere el intervalo de tiempo del subproceso.  A partir de ese momento, el bloqueo temporal produce su propio cambio de contexto llamando a <xref:System.Threading.WaitHandle.WaitOne%2A> en <xref:System.Threading.ManualResetEvent> y pasando el resto del valor del tiempo de espera.  
  
 El resultado del registro muestra con qué frecuencia Latch pudo aumentar el rendimiento adquiriendo el bloqueo sin utilizar <xref:System.Threading.ManualResetEvent>.  
  
## Vea también  
 [SpinWait](../../../docs/standard/threading/spinwait.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)