---
title: "Mitigaci&#243;n: Llamadas al m&#233;todo EventSource.WriteEvent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 327a9fdb-ba8e-40f7-89e5-4c89b46e594f
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Mitigaci&#243;n: Llamadas al m&#233;todo EventSource.WriteEvent
[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] fuerza un contrato entre un método de evento ETW de una clase derivada de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> y el método <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> de su clase base. El método de evento ETW debe pasar al método <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A> el identificador de evento seguido de los mismos argumentos que se pasaron al método del evento.  
  
## Impacto  
 Un método de evento ETW definido de la manera siguiente infringe el contrato:  
  
```  
  
[Event(2, Level = EventLevel.Informational)] public void Info2(string message) { base.WriteEvent(2, message, "-"); }  
  
```  
  
 Cuando se infringe este contrato, se genera una excepción <xref:System.IndexOutOfRangeException> en tiempo de ejecución si un objeto <xref:System.Diagnostics.Tracing.EventListener> lee datos <xref:System.Diagnostics.Tracing.EventSource> en proceso.  
  
 La definición de este método de evento ETW debe seguir este patrón:  
  
```  
  
[Event(2, Level = EventLevel.Informational)] public void Info2(string message) { base.WriteEvent(2, message); }  
  
```  
  
## Mitigación  
 Debe modificar el código existente para que se ajuste al patrón requerido.  
  
 Puede minimizar la cantidad de código que hay que cambiar definiendo dos métodos para llamar al método <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A>, de la forma siguiente:  
  
```  
  
[NonEvent] public void Info2(string message) { Info2Internal(message, "-"); } public void Info2Internal(string message, string prefix) { WriteEvent(2, message, prefix); }  
  
```  
  
## Vea también  
 [Cambios en tiempo de ejecución](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)