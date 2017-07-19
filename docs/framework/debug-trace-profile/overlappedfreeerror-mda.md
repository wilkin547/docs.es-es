---
title: "overlappedFreeError MDA | Microsoft Docs"
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
  - "OverlappedFreeError MDA"
  - "overlapped free method call error"
  - "managed debugging assistants (MDAs), overlapped structures"
  - "overlapped structures"
  - "MDAs (managed debugging assistants), overlapped structures"
  - "freeing overlapped structures"
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# overlappedFreeError MDA
El asistente para la depuración administrada `overlappedFreeError` \(MDA\) se activa cuando se llama al método <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=fullName> antes de que finalice la operación superpuesta.  
  
## Síntomas  
 Infracciones de acceso o daños en la pila de recolección de elementos no utilizados.  
  
## Motivo  
 Se ha liberado una estructura superpuesta antes de que finalizara la operación.  La función que está utilizando el puntero superpuesto podría escribir después en la estructura, una vez que se hubiese liberado.  Esto puede producir daños en la pila porque otro objeto podría ocupar ahora esa región.  
  
 Este asistente para la depuración administrada no podría representar un error si la operación superpuesta no se se hubiese iniciado correctamente.  
  
## Resolución  
 Asegúrese de que la operación de E\/S que utiliza la estructura superpuesta haya finalizado antes de llamar al método <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>.  
  
## Efecto en el Runtime  
 Este MDA no tiene efecto en el CLR.  
  
## Resultados  
 A continuación se muestra un ejemplo de los resultados de este MDA.  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'.  If the AppDomain is shut down, this can cause heap corruption when the async I/O completes.  The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack().  If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## Configuration  
  
```  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)