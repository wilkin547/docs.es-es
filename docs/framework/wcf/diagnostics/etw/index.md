---
title: Traza analítica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 210418b8a8765a1fc59658e9df57c92ce087c95f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="analytic-tracing-with-etw"></a>Traza analítica con ETW
Traza analítica de Windows Communication Foundation (WCF) ofrece una manera de capturar información de diagnóstico durante la ejecución de un servicio WCF. Se emiten eventos de traza analítica de WCF en puntos clave de la pila WCF que permiten solucionar problemas de servicios WCF en un entorno de producción. Traza analítica para los servicios WCF tiene un impacto mínimo en el rendimiento de un servidor del producto que hospeda [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] de servicios de WCF como estos eventos se emiten de forma muy eficaz a una sesión de seguimiento de eventos para Windows (ETW).  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general de traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Describe cómo funciona la traza analítica de WCF en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Habilitación dinámica de la traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Describe cómo habilitar o deshabilitar la traza de forma dinámica mediante ETW.  
  
 [Configuración de la traza del flujo de mensajes](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Describe cómo configurar la traza de flujo de mensajes.  
  
 [Referencia de evento de traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Muestra una tabla de identificadores de eventos con sus niveles de evento, mensajes de evento y palabras clave.  
  
## <a name="see-also"></a>Vea también  
 [Servicios WCF y Seguimiento de eventos para Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [Seguimiento de eventos en Seguimiento de eventos para Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
