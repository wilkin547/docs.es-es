---
title: "gcManagedToUnmanaged MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), garbage collection"
  - "GcManagedToUnmanaged MDA"
  - "GC managed to unmanaged"
  - "transitioning threads managed to unmanaged code"
  - "threading [.NET Framework], garbage collection"
  - "managed to unmanaged garbage collection"
  - "managed debugging assistants (MDAs), garbage collection"
  - "threading [.NET Framework], managed debugging assistants"
  - "garbage collection, run-time errors"
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# gcManagedToUnmanaged MDA
El asistente para la depuración administrada \(MDA\) `gcManagedToUnmanaged` produce una recolección de elementos no utilizados siempre que un subproceso realiza la transición de código administrado a no administrado.  
  
## Síntomas  
 Un componente de usuario no administrado produce una infracción de acceso al intentar usar un objeto administrado que se había expuesto a COM.  El objeto COM aparece como liberado.  La infracción de acceso es no determinista.  
  
## Motivo  
 Si un componente no administrado no cuenta correctamente las referencias de un objeto COM administrado, CLR podría recopilar un objeto administrado expuesto a COM cuando el componente no administrado todavía contiene una referencia al objeto.  Como CLR llama a <xref:System.Runtime.InteropServices.Marshal.Release%2A> durante las recolecciones de elementos no utilizados, si el componente de usuario utiliza el objeto antes de que se produzca la recolección de elementos no utilizados, aún no se habrá recolectado.  Este es el origen del no determinismo.  
  
## Resolución  
 Habilitar este asistente reduce el tiempo entre el momento en que el objeto es apto para la recolección y el momento en que se llama a <xref:System.Runtime.InteropServices.Marshal.Release%2A>, lo que ayuda a realizar un seguimiento de qué componente no administrado intenta acceder primero al objeto recolectado.  
  
## Efecto en el Runtime  
 Produce una recolección de elementos no utilizados siempre que un subproceso realice la transición de código administrado a no administrado.  
  
## Salida  
 Este MDA no produce ninguna salida.  
  
## Configuración  
  
```  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)   
 [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)