---
title: MDA de pInvokeLog
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- signatures, platform invoke
- MDAs (managed debugging assistants), platform invoke
- platform invoke, run-time errors
- platform invoke log
- PInvokeLog MDA
- managed debugging assistants (MDAs), platform invoke
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
caps.latest.revision: 8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1856fd25ca54b456176cf88a28968cf83696fa54
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="pinvokelog-mda"></a>MDA de pInvokeLog
El Asistente para la depuración administrada (MDA) `pInvokeLog` se activa para cada firma de invocación de plataforma única que se usa durante la ejecución.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## <a name="output"></a>Resultado  
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
 [Diagnóstico de errores con asistentes para la depuración administrada](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Consumir funciones DLL no administradas](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)

