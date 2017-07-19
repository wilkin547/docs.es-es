---
title: "notMarshalable MDA | Microsoft Docs"
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
  - "managed debugging assistants (MDAs), interface pointer not marshalable"
  - "interface pointer not marshalable MDA"
  - "MDAs (managed debugging assistants), interface pointer not marshalable"
  - "marshaling, run-time errors"
  - "managed debugging assistants (MDAs), marshaling"
  - "marshalable interface pointers"
  - "MDAs (managed debugging assistants), marshaling"
  - "notMarshalable MDA"
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# notMarshalable MDA
El asistente para la depuración administrada \(MDA\) `notMarshalable` se activa cuando Common Language Runtime \(CLR\) encuentra un puntero a interfaz COM sin un servidor proxy\/código auxiliar válido registrado o una implementación de interfaz `IMarshal` incorrecta al intentar calcular las referencias de la interfaz entre contextos.  
  
## Síntomas  
 No se da servicio a las llamadas o las llamadas se producen en un contexto incorrecto para los punteros a interfaz COM.  
  
## Motivo  
 No hay ningún servidor proxy\/código auxiliar registrado válido o `IMarshal` incorrecta intentando calcular las referencias de la interfaz entre los contextos.  
  
## Resolución  
 Asegúrese de que tiene registrado un código auxiliar de servidor proxy y de que la implementación de `IMarshal` es válida.  
  
## Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el tiempo de ejecución.  
  
## Resultado  
 Un mensaje que describe el problema.  
  
## Configuración  
  
```  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)