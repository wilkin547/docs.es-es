---
title: "Analytic Tracing with ETW | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "diagnostics [WCF], analytic tracing"
  - "administration [WCF], analytic tracing"
  - "analytic tracing [WCF]"
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Analytic Tracing with ETW
El seguimiento analítico de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] proporciona una manera de capturar información de diagnóstico durante la ejecución de un servicio de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].Los eventos de seguimiento analítico de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] se emiten en los puntos clave de la pila de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] que permiten solucionar problemas de los servicios de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en un entorno de producción.La traza analítica para los servicios de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] tiene un impacto mínimo en el rendimiento de un servidor del producto que hospeda servicios de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)], ya que estos eventos se emiten de forma muy eficaz a una sesión del Seguimiento de eventos para Windows \(ETW\).  
  
## En esta sección  
 [Información general de traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Describe cómo funciona la traza analítica de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Habilitar dinámicamente la traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Describe cómo habilitar o deshabilitar la traza de forma dinámica mediante ETW.  
  
 [Configurar la traza de flujo de mensajes](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Describe cómo configurar la traza de flujo de mensajes.  
  
 [Referencia de evento de traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Muestra una tabla de identificadores de eventos con sus niveles de evento, mensajes de evento y palabras clave.  
  
## Vea también  
 [Servicios de WCF y seguimiento de eventos para Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)   
 [Seguimiento de eventos en Seguimiento de eventos para Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)