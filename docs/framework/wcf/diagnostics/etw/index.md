---
title: "Traza analítica con ETW"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a16f66ed8443749764e66d2616ae566ad788d571
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="analytic-tracing-with-etw"></a>Traza analítica con ETW
El seguimiento analítico de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] proporciona una manera de capturar información de diagnóstico durante la ejecución de un servicio de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]. Los seguimientos analíticos [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] son los eventos emitidos en los puntos clave de la pila de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] que permiten solucionar problemas de los servicios de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en un entorno de producción. Traza analítica para [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] servicios tiene un impacto mínimo en el rendimiento de un servidor del producto que hospeda [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] de servicios como estos eventos se emiten de forma muy eficaz a una sesión de seguimiento de eventos para Windows (ETW).  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general de traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Describe cómo el seguimiento analítica [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] funciona en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Habilitación dinámica de la traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Describe cómo habilitar o deshabilitar la traza de forma dinámica mediante ETW.  
  
 [Configuración de la traza del flujo de mensajes](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Describe cómo configurar la traza de flujo de mensajes.  
  
 [Referencia de evento de traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Muestra una tabla de identificadores de eventos con sus niveles de evento, mensajes de evento y palabras clave.  
  
## <a name="see-also"></a>Vea también  
 [Servicios WCF y Seguimiento de eventos para Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)  
 [Seguimiento de eventos en Seguimiento de eventos para Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
