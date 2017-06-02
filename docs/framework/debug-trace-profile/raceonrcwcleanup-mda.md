---
title: "raceOnRCWCleanup MDA | Microsoft Docs"
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
  - "RCW"
  - "managed debugging assistants (MDAs), RCWs"
  - "race on RCW cleanup"
  - "MDAs (managed debugging assistants), RCWs"
  - "RaceOnRCWCleanup MDA"
  - "runtime callable wrappers"
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# raceOnRCWCleanup MDA
El asistente para la depuración administrada \(MDA\) de `raceOnRCWCleanup` se activa cuando Common Language Runtime \(CLR\) detecta que un [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) \(RCW\) está en uso al realizar una llamada para liberarlo utilizando un comando como el método <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName>.  
  
## Síntomas  
 Infracciones de acceso o daños en la memoria durante o después de la liberalización de RCW utilizando <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> o un método similar.  
  
## Motivo  
 RCW está en otro subproceso o en la pila de subprocesos de liberación.  No se puede liberar un RCW que esté en uso.  
  
## Solución  
 No libere ningún RCW que pudiera estar en uso en este o en otros subprocesos.  
  
## Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## Resultado  
 Un mensaje que describe el error.  
  
## Configuración  
  
```  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)