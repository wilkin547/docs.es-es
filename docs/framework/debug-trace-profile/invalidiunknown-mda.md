---
title: "invalidIUnknown MDA | Microsoft Docs"
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
  - "MDAs (managed debugging assistants), invalid IUnknown pointer"
  - "InvalidIUnknown MDA"
  - "invalid IUnknown pointers"
  - "IUnknown pointers"
  - "managed debugging assistants (MDAs), invalid IUnknown pointer"
ms.assetid: c7924771-a16b-40fe-b337-ce51dcdf6a12
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# invalidIUnknown MDA
El asistente para la depuración administrada \(MDA\) de `invalidIUnknown` se activa cuando un puntero `IUnknown` no válido se pasa a código administrado de código nativo.  Se produce un error en `IUnknown` a la hora de devolver un resultado correctamente cuando se solicita la interfaz `IUnknown`.  
  
## Síntomas  
 Se produce un error inesperado al calcular referencias de un puntero a una interfaz COM durante el cálculo de referencias del argumento.  
  
## Motivo  
 Implementación de `QueryInterface` incorrecta en la interfaz COM pasada al CLR.  
  
## Resolución  
 Corrija la implementación de `QueryInterface`.  
  
## Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR.  
  
## Salida  
 Descripción del error.  
  
## Configuración  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidIUnknown />  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)