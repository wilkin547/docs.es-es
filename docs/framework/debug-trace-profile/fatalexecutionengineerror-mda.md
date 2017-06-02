---
title: "fatalExecutionEngineError MDA | Microsoft Docs"
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
  - "corrupted CLR"
  - "fatal execution error"
  - "terminated processes"
  - "unexpected terminations"
  - "fatal errors"
  - "MDAs (managed debugging assistants), fatal errors"
  - "process termination"
  - "FatalExecutionEngineError MDA"
  - "managed debugging assistants (MDAs), fatal errors"
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# fatalExecutionEngineError MDA
El asistente para la depuración administrada \(MDA\) `fatalExecutionEngine``Error` se activa cuando se detecta un error irrecuperable en Common Language Runtime \(CLR\).  Esto finaliza el proceso.  
  
## Síntomas  
 Finalización de proceso inesperada.  No se pueden determinar otros síntomas porque los errores de CLR pueden ser debidos a distintos motivos.  
  
## Motivo  
 Common Language Runtime ha sufrido un daño grave.  En la mayoría de los casos, esto se debe a los daños en los datos, lo que puede obedecer a distintos problemas como, por ejemplo, llamar a funciones de invocación de plataforma incorrectas o pasar datos no válidos a Common Language Runtime.  
  
## Resolución  
 Si se habilitan asistentes para la depuración administrada adicionales, se podría ayudar a identificar el problema.  Los siguientes asistentes para la depuración administrada pueden resultar especialmente útiles a la hora de diagnosticar el problema:  
  
-   [invalidOverlappedToPinvoke](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
-   [overlappedFreeError](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
-   [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
-   [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
-   [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
-   [callbackOnCollectedDelegate](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
-   [reportAvOnComRelease](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
-   [invalidVariant](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
-   [invalidIUnknown](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
-   [raceOnRCWCleanup](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
-   [invalidFunctionPointerInDelegate](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
-   [invalidGCHandleCookie](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## Efecto en el Runtime  
 Este asistente para la depuración administrada no tiene ningún efecto en el comportamiento de Common Language Runtime.  
  
## Resultados  
 La dirección de la función de Common Language Runtime que produjo el error irrecuperable, el identificador del subproceso donde se ha producido el error y el código de error.  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>   
 <xref:System.Runtime.ConstrainedExecution.Cer>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)