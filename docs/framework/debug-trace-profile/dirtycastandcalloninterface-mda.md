---
title: "dirtyCastAndCallOnInterface MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), early bound calls AutoDispatch"
  - "dispatch-only mode"
  - "dirtyCastAndCallOnInterface"
  - "early-bound managed classes"
  - "early bound calls on AutoDispatch"
  - "MDAs (managed debugging assistants), early bound calls AutoDispatch"
  - "EarlyBoundCallOnAutorDispatchClassInteface MDA"
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# dirtyCastAndCallOnInterface MDA
El Asistente para la depuración administrada \(MDA\) `dirtyCastAndCallOnInterface` se activa cuando se intenta realizar una llamada enlazada en tiempo de compilación a través de una vtable en una interfaz de clase que se ha marcado solo como enlazada en tiempo de ejecución.  
  
## Síntomas  
 Una aplicación produce una infracción de acceso o tiene un comportamiento inesperado cuando se realiza una llamada enlazada en tiempo de compilación a CLR a través de COM.  
  
## Motivo  
 El código intenta realizar una llamada enlazada en tiempo de compilación a través de una vtable mediante una interfaz de clase que es solo enlazada en tiempo de ejecución.  Tenga en cuenta que las interfaces de clase predeterminadas se identifican solo como enlazadas en tiempo de ejecución.  También pueden identificarse como enlazadas en tiempo de ejecución cuando el atributo <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> tiene un valor <xref:System.Runtime.InteropServices.ClassInterfaceType> \(`[ClassInterface(ClassInterfaceType.AutoDispatch)]`\).  
  
## Resolución  
 La solución recomendada es definir una interfaz explícita para que COM la use y hacer que los clientes COM llamen a través de esta interfaz en lugar de la interfaz de clase que se genera automáticamente.  Como alternativa, la llamada desde COM se puede transformar en una llamada enlazada en tiempo de ejecución mediante `IDispatch`.  
  
 Por último, es posible identificar la clase como <xref:System.Runtime.InteropServices.ClassInterfaceType> \(`[ClassInterface(ClassInterfaceType.AutoDual)]`\) para permitir que se realicen llamadas enlazadas en tiempo de compilación desde COM; sin embargo, se desaconseja usar <xref:System.Runtime.InteropServices.ClassInterfaceType> debido a las limitaciones del control de versiones descritas en <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.  
  
## Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  Solo notifica datos sobre las llamadas enlazadas en tiempo de compilación en interfaces enlazadas en tiempo de ejecución.  
  
## Resultado  
 El nombre del método o el nombre del campo al que se va a acceder mediante enlace en tiempo de compilación.  
  
## Configuración  
  
```  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)