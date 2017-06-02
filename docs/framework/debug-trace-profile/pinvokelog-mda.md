---
title: "pInvokeLog MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "signatures, platform invoke"
  - "MDAs (managed debugging assistants), platform invoke"
  - "platform invoke, run-time errors"
  - "platform invoke log"
  - "PInvokeLog MDA"
  - "managed debugging assistants (MDAs), platform invoke"
ms.assetid: b830444a-5003-49fe-b89b-b8bee22f7b1a
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# pInvokeLog MDA
El asistente para la depuración administrada \(MDA\) de `pInvokeLog` se activa para cada firma de invocación de plataforma única utilizada durante la ejecución.  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  
  
## Resultados  
 Mensaje que indica la firma de invocación de la plataforma utilizada durante la ejecución.  
  
## Configuration  
 Cada elemento coincidente filtra los archivos .dll donde se realizan las llamadas de invocación de plataforma.  
  
```  
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
  
## Vea también  
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)