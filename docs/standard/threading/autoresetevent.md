---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70af739bdb90a70a1319354b4964c261e432912b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729962"
---
# <a name="autoresetevent"></a>AutoResetEvent
La clase <xref:System.Threading.AutoResetEvent> representa un evento de identificador de espera local que se restablece automáticamente cuando se le señala, después de liberar un subproceso en espera único. Esta clase representa un caso especial de su clase base, <xref:System.Threading.EventWaitHandle>. Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para información sobre el uso y las características de los eventos de restablecimiento automático.  
  
 Un objeto <xref:System.Threading.AutoResetEvent> se restablece automáticamente a no señalado por el sistema una vez que se ha liberado un subproceso en espera único. Si no hay subprocesos en espera, el objeto del evento sigue teniendo el estado señalizado.
  
 Para obtener un ejemplo en el que se usa <xref:System.Threading.AutoResetEvent>, vea <xref:System.Threading.Monitor>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
- [Objetos y características de subprocesos](threading-objects-and-features.md)
- [Subprocesamiento](index.md)
