---
title: MDA de pInvokeLog
description: Comprenda el Asistente para la depuración administrada (MDA) pInvokeLog, que se activa para cada firma de invocación de plataforma única que se usa durante la ejecución en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
ms.openlocfilehash: b8cb4805663a2b28a133f98503730199af695c4f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271465"
---
# <a name="pinvokelog-mda"></a>MDA de pInvokeLog

El Asistente para la depuración administrada (MDA) `pInvokeLog` se activa para cada firma de invocación de plataforma única que se usa durante la ejecución.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  

 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Resultados  

 Un mensaje que indica la firma de invocación de plataforma que se usa durante la ejecución.  
  
## <a name="configuration"></a>Configuración  

 Cada elemento coincidente filtra los archivos .dll a los que se realizan llamadas de invocación de plataforma.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <pInvokeLog>  
      <filter>  
        <match dllName="user32.dll"/>  
        <match dllName="kernel32.dll"/>  
      </filter>  
    </pInvokeLog>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Consumir funciones DLL no administradas](../interop/consuming-unmanaged-dll-functions.md)
