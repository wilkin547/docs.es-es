---
title: Eventos ETW en Common Language Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83246f42275425bca48530915c7bf5c19f3b9f04
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447665"
---
# <a name="etw-events-in-the-common-language-runtime"></a>Eventos ETW en Common Language Runtime
Common Language Runtime (CLR) proporciona información de diagnóstico del Seguimiento de eventos para Windows (ETW) útil para una gran variedad de eventos de depuración y de generación de perfiles. Los eventos ETW de CLR se aprovechan del sistema de seguimiento ETW de Windows para aumentar la compatibilidad con la depuración y generación de perfiles proporcionada por Common Language Runtime.  
  
 More information about ETW is available in the [Improve Debugging and Performance Tuning with ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) article. La información sobre Xperf se puede encontrar en la entrada [Kit de herramientas de rendimiento de Windows - Xperf](https://blogs.msdn.microsoft.com/ntdebugging/2008/04/03/windows-performance-toolkit-xperf/) del blog de NTDebugging.  
  
 The .NET Framework 4 or later is required for all the events described in the event topics. El sistema operativo Windows Vista es el cliente compatible mínimo, y Windows Server 2008 es el servidor compatible mínimo.  
  
## <a name="in-this-section"></a>En esta sección  
 [Controlar el registro de .NET Framework](controlling-logging.md)  
 Describe las herramientas y los comandos para capturar y ver los eventos ETW.  
  
 [Proveedores ETW de CLR](clr-etw-providers.md)  
 Proporciona información sobre los proveedores de runtime y de detención; además, explica el modo de usarlos para la recopilación de datos ETW.  
  
 [Palabras clave y niveles ETW de CLR](clr-etw-keywords-and-levels.md)  
 Describe las palabras clave para los proveedores de runtime y de detención que habilitan el filtrado de eventos por categoría.  
  
 [CLR ETW Events (Eventos ETW de CLR)](clr-etw-events.md)  
 Proporciona información detallada sobre eventos ETW de CLR, sus palabras clave, niveles y datos de evento.  
  
## <a name="see-also"></a>Vea también

- [Eventos ETW en .NET Framework](etw-events.md)
