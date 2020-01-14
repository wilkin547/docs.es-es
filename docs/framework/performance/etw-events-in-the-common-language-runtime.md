---
title: Eventos ETW en Common Language Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: 49d1141540fb00ab7ef462da5af84f02e6d9fc4d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937855"
---
# <a name="etw-events-in-the-common-language-runtime"></a>Eventos ETW en Common Language Runtime
Common Language Runtime (CLR) proporciona información de diagnóstico del Seguimiento de eventos para Windows (ETW) útil para una gran variedad de eventos de depuración y de generación de perfiles. Los eventos ETW de CLR se aprovechan del sistema de seguimiento ETW de Windows para aumentar la compatibilidad con la depuración y generación de perfiles proporcionada por Common Language Runtime.  
  
 Puede encontrar más información sobre ETW en el artículo [mejorar la optimización del rendimiento y la depuración con ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) . La información sobre Xperf se puede encontrar en la entrada [Kit de herramientas de rendimiento de Windows - Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) del blog de NTDebugging.  
  
 Se necesita el .NET Framework 4 o posterior para todos los eventos descritos en los temas de eventos. El sistema operativo Windows Vista es el cliente compatible mínimo, y Windows Server 2008 es el servidor compatible mínimo.  
  
## <a name="in-this-section"></a>Esta sección  
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
