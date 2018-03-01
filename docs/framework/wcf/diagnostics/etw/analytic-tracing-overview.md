---
title: "Información general de traza analítica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3492821d56f7089c2aa53bba566690ded02f8a5b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="analytic-tracing-overview"></a>Información general de traza analítica
La traza analítica en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] es una característica de traza de alto rendimiento y bajo nivel de detalle establecida en Seguimiento de eventos para Windows (ETW). ETW se ejecuta en el kernel para reducir en gran medida la sobrecarga de las operaciones de traza. Almacena en búfer eventos de usuario y en modo kernel, y permite una habilitación dinámica del registro sin requerir un reinicio del servicio. Los datos de la traza están disponibles en los registros de eventos una vez emitidos y recibidos.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] ETW, consulte [Improve Debugging and Performance Tuning with ETW (Mejora de la depuración y el ajuste del rendimiento con ETW)](http://go.microsoft.com/fwlink/?LinkId=164781).  
  
 Además de usar registros de eventos del sistema Windows, de seguridad y de la aplicación para analizar la aplicación, [!INCLUDE[wv](../../../../../includes/wv-md.md)] y [!INCLUDE[lserver](../../../../../includes/lserver-md.md)] introducen registros adicionales en el nodo superior de registros de servicios y aplicaciones. El propósito de estos nuevos registros es almacenar eventos para una aplicación determinada o un componente concreto en lugar de los eventos globales que tienen un impacto en todo el sistema (como el tipo de eventos que el registro de eventos de seguridad podría grabar). [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] unifica y correlaciona el registro de eventos de seguimiento de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] , los registros de mensaje de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] y los registros de seguimiento de [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] en los Registros de aplicaciones y servicios.  
  
## <a name="concepts-and-capabilities"></a>Conceptos y capacidades  
 Los siguientes conceptos y capacidades se aplican a la traza analítica de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] .  
  
### <a name="enabling-wcf-diagnostics-settings"></a>Habilitar la configuración de diagnóstico de WCF  
 Se habilitan los diagnósticos WCF dentro de la \<system.serviceModel >\<diagnóstico > sección de configuración.  
  
```xml  
<system.serviceModel>  
  <diagnostics>  
```  
  
 La configuración de diagnóstico de WCF para una aplicación virtual de IIS hospedada en web se habilita en el archivo Web.config. Otra opción es crear Web.config en un subdirectorio dentro de la aplicación.  Esta opción aplica la configuración a todos los servicios dentro de un subdirectorio.  Para asegurarse de que la configuración de diagnóstico se inicializa de forma coherente para todos los servicios dentro de la aplicación, la configuración debería estar dentro de Web.config en el directorio de aplicaciones, y no en uno de los subdirectorios individuales dentro de la aplicación.  
  
### <a name="channels"></a>Canales  
 ETW permite a los componentes de software dirigir eventos de traza a una audiencia determinada mediante el empleo de canales. Por ejemplo, puede enviar eventos para los administradores del sistema a un canal, y eventos importantes para los desarrolladores de aplicaciones a otro canal. Los canales se denominan y se registran con Windows para que los consumidores puedan ver los eventos de un canal mediante el visor de eventos.  
  
 La característica de seguimiento analítico para [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] escribe en el canal Microsoft-Windows-Servidor de aplicaciones. Este canal está diseñado específicamente para los usuarios que desean supervisar el estado de los servicios de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] en producción. Define un pequeño conjunto de eventos que se puede usar en muchos casos de supervisión de estado y solución de problemas.  
  
 Para habilitar el manifiesto Seguimiento de eventos para Windows de modo que los mensajes se descodifiquen de forma apropiada en el registro de eventos, use la herramienta ServiceModelReg en la línea de comandos, como se indica a continuación:  
  
 `ServiceModelReg.exe -i -c:etw`  
  
### <a name="dynamic-configuration"></a>Configuración dinámica  
 La infraestructura de ETW permite habilitar la traza y configurarla de forma dinámica mediante herramientas Windows estándar. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][Habilitar dinámicamente la traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md).  
  
### <a name="message-flow-tracing"></a>Traza de flujo de mensajes  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] cómo habilitar el seguimiento del flujo de mensajes, consulte [Configuring Message Flow Tracing](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md).  
  
### <a name="keywords"></a>Palabras clave  
 Las palabras clave se usan para filtrar los mensajes de traza y definir qué componente de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] emitió el evento. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][Habilitar dinámicamente la traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md).
