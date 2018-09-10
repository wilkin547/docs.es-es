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
ms.openlocfilehash: 7602a61a4403b7ab85015876823aa41e250b23de
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863314"
---
# <a name="autoresetevent"></a>AutoResetEvent
La clase <xref:System.Threading.AutoResetEvent> representa un evento de identificador de espera local que se restablece automáticamente cuando se le señala, después de liberar un subproceso en espera único. Esta clase representa un caso especial de su clase base, <xref:System.Threading.EventWaitHandle>. Consulte la documentación conceptual [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) para información sobre el uso y las características de los eventos de restablecimiento automático.  
  
 Un objeto <xref:System.Threading.AutoResetEvent> se restablece automáticamente a no señalado por el sistema una vez que se ha liberado un subproceso en espera único. Si no hay subprocesos en espera, el objeto del evento sigue teniendo el estado señalizado. <xref:System.Threading.AutoResetEvent> corresponde a una llamada a `CreateEvent` de Win32, definiendo `false` para el argumento `bManualReset`.  
  
 Para obtener un ejemplo en el que se usa <xref:System.Threading.AutoResetEvent>, vea <xref:System.Threading.Monitor>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.ManualResetEvent>  
- <xref:System.Threading.Monitor>  
- [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [Subprocesamiento](../../../docs/standard/threading/index.md)  
- [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)  
- [Wait Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489) (Clases WaitHandle)
