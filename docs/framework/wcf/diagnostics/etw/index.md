---
description: 'Más información sobre: traza analítica con ETW'
title: Traza analítica con ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: fd40d40de2508fd251c793e4455c1e656a1cbbf6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798802"
---
# <a name="analytic-tracing-with-etw"></a>Traza analítica con ETW

La traza analítica de Windows Communication Foundation (WCF) ofrece una manera de capturar información de diagnóstico durante la ejecución de un servicio WCF. Los eventos de seguimiento analítico de WCF se emiten en puntos clave de la pila de WCF para permitir la solución de problemas de los servicios WCF en un entorno de producción. La traza analítica de los servicios WCF tiene un impacto mínimo en el rendimiento de un servidor de producto que hospeda los [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] servicios WCF, ya que estos eventos se emiten de forma muy eficaz a una sesión de seguimiento de eventos para Windows (ETW).  
  
## <a name="in-this-section"></a>En esta sección  

 [Información general de traza analítica](analytic-tracing-overview.md)  
 Describe cómo funciona el seguimiento analítico de WCF en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] .  
  
 [Habilitar dinámicamente la traza analítica](dynamically-enabling-analytic-tracing.md)  
 Describe cómo habilitar o deshabilitar la traza de forma dinámica mediante ETW.  
  
 [Configurar la traza de flujo de mensajes](configuring-message-flow-tracing.md)  
 Describe cómo configurar la traza de flujo de mensajes.  
  
 [Referencia de evento de traza analítica](analytic-trace-event-reference.md)  
 Muestra una tabla de identificadores de eventos con sus niveles de evento, mensajes de evento y palabras clave.  
  
## <a name="see-also"></a>Vea también

- [Servicios de WCF y seguimiento de eventos para Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
- [Seguimiento de eventos en Seguimiento de eventos para Windows](../../../windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
