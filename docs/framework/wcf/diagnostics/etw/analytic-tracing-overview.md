---
title: Información general de traza analítica
ms.date: 03/30/2017
helpviewer_keywords:
- analytic tracing [WCF], overview
ms.assetid: ae55e9cc-0809-442f-921f-d644290ebf15
ms.openlocfilehash: 9918f07d9c26c1779a1eedfbc423c31e61659334
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44070126"
---
# <a name="analytic-tracing-overview"></a>Información general de traza analítica
La traza analítica en [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] es una característica de traza de alto rendimiento y bajo nivel de detalle establecida en Seguimiento de eventos para Windows (ETW). ETW se ejecuta en el kernel para reducir en gran medida la sobrecarga de las operaciones de traza. Almacena en búfer eventos de usuario y en modo kernel, y permite una habilitación dinámica del registro sin requerir un reinicio del servicio. Los datos de la traza están disponibles en los registros de eventos una vez emitidos y recibidos.  
  
 Para obtener más información sobre ETW, vea [Improve Debugging and Performance Tuning with ETW](https://go.microsoft.com/fwlink/?LinkId=164781).  
  
 Además de usar registros de eventos del sistema Windows, de seguridad y de la aplicación para analizar la aplicación, [!INCLUDE[wv](../../../../../includes/wv-md.md)] y [!INCLUDE[lserver](../../../../../includes/lserver-md.md)] introducen registros adicionales en el nodo superior de registros de servicios y aplicaciones. El propósito de estos nuevos registros es almacenar eventos para una aplicación determinada o un componente concreto en lugar de los eventos globales que tienen un impacto en todo el sistema (como el tipo de eventos que el registro de eventos de seguridad podría grabar). [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] unifica y correlaciona el registro de eventos de seguimiento de WCF, los registros de mensaje WCF y [!INCLUDE[wf1](../../../../../includes/wf1-md.md)] los registros de seguimiento para los registros de servicios y aplicaciones.  
  
## <a name="concepts-and-capabilities"></a>Conceptos y capacidades  
 Los siguientes conceptos y capacidades se aplican a la traza analítica de WCF.  
  
### <a name="enabling-wcf-diagnostics-settings"></a>Habilitar la configuración de diagnóstico de WCF  
 Se habilitan los diagnósticos WCF dentro de la \<system.serviceModel >\<diagnósticos > sección de configuración.  
  
```xml  
<system.serviceModel>  
  <diagnostics>  
```  
  
 La configuración de diagnóstico de WCF para una aplicación virtual de IIS hospedada en web se habilita en el archivo Web.config. Otra opción es crear Web.config en un subdirectorio dentro de la aplicación.  Esta opción aplica la configuración a todos los servicios dentro de un subdirectorio.  Para asegurarse de que la configuración de diagnóstico se inicializa de forma coherente para todos los servicios dentro de la aplicación, la configuración debería estar dentro de Web.config en el directorio de aplicaciones, y no en uno de los subdirectorios individuales dentro de la aplicación.  
  
### <a name="channels"></a>Canales  
 ETW permite a los componentes de software dirigir eventos de traza a una audiencia determinada mediante el empleo de canales. Por ejemplo, puede enviar eventos para los administradores del sistema a un canal, y eventos importantes para los desarrolladores de aplicaciones a otro canal. Los canales se denominan y se registran con Windows para que los consumidores puedan ver los eventos de un canal mediante el visor de eventos.  
  
 La característica de traza analítica de WCF en [!INCLUDE[netfx_current_short](../../../../../includes/netfx-current-short-md.md)] escribe en el canal de Microsoft-Windows-Application-Server-Applications. Este canal está diseñado específicamente para los usuarios que desean supervisar el estado de los servicios WCF en producción. Define un pequeño conjunto de eventos que se puede usar en muchos casos de supervisión de estado y solución de problemas.  
  
 Para habilitar el manifiesto Seguimiento de eventos para Windows de modo que los mensajes se descodifiquen de forma apropiada en el registro de eventos, use la herramienta ServiceModelReg en la línea de comandos, como se indica a continuación:  
  
 `ServiceModelReg.exe -i -c:etw`  
  
### <a name="dynamic-configuration"></a>Configuración dinámica  
 La infraestructura de ETW permite habilitar la traza y configurarla de forma dinámica mediante herramientas Windows estándar. Para obtener más información, consulte [dinámicamente habilitar la traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md).  
  
### <a name="message-flow-tracing"></a>Traza de flujo de mensajes  
 Para obtener más información acerca de cómo habilitar el seguimiento del flujo de mensajes, vea [Configuring Message Flow Tracing](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md).  
  
### <a name="keywords"></a>Palabras clave  
 Las palabras clave se usan para filtrar los mensajes de traza y definir qué componente de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] emitió el evento. Para obtener más información, consulte [dinámicamente habilitar la traza analítica](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md).
