---
title: Habilitar dinámicamente la traza analítica
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d070c66eebbf1a067254c38c6e5bfc7f40742863
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dynamically-enabling-analytic-tracing"></a>Habilitar dinámicamente la traza analítica
Con las herramientas que se distribuyen con el sistema operativo Windows, puede habilitar o deshabilitar la traza de forma dinámica mediante el Seguimiento de eventos para Windows (ETW). Para todos los servicios [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] , el seguimiento analítica puede habilitarse y deshabilitarse de forma dinámica sin modificar el archivo Web.config de la aplicación ni reiniciar el servicio. Esto permite que la aplicación que emite los eventos de traza siga sin más.  
  
 Las opciones de traza de[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] pueden configurarse de una manera similar. Por ejemplo, puede cambiar el nivel de gravedad de **Error** a **Información** sin interrumpir a la aplicación. Esto se puede hacer mediante las siguientes herramientas:  
  
-   **Logman** . Una herramienta de línea de comandos para configurar, controlar y consultar los datos de la traza. Para obtener más información, consulte [Logman crear seguimiento](http://go.microsoft.com/fwlink/?LinkId=165426) y [Logman Update Trace](http://go.microsoft.com/fwlink/?LinkId=165427).  
  
-   **EventViewer** . Herramienta de administración gráfica de Windows para ver los resultados de la traza. Para obtener más información, consulte [servicios WCF y seguimiento de eventos para Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md) y [Visor de eventos](http://go.microsoft.com/fwlink/?LinkId=165428).  
  
-   **Perfmon** . Herramienta de administración gráfica de Windows que usa los contadores para supervisar los contadores de traza y los efectos de la traza durante el rendimiento. Para obtener más información, consulte [crear una datos Recopilador establece manualmente](http://go.microsoft.com/fwlink/?LinkId=165429).  
  
### <a name="keywords"></a>Palabras clave  
 Al utilizar la clase <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> , los mensajes de traza de .NET Framework se suelen filtrar según el nivel de gravedad (por ejemplo, Error, Advertencia e Información). ETW admite el concepto de nivel de gravedad, pero introduce un mecanismo de filtro nuevo y flexible mediante palabras clave. Las palabras clave son valores textuales arbitrarios que permiten a los eventos de traza proporcionar contexto adicional sobre lo que ese evento significa.  
  
 Para la traza analítica de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] , cada evento de traza tiene dos tipos de palabras clave. Primero, cada evento tiene una o más palabras clave de escenario. Estas palabras clave indican los escenarios que este evento debería admitir. Hay tres palabras clave de escenario, cada una diseñada para un propósito concreto, tal y como se muestra en la siguiente tabla. El filtrado con palabras clave puede cambiarse dinámicamente sin interrumpir el servicio de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] . Eso significa que puede cambiar de forma dinámica el escenario de traza actual y la cantidad de información de traza recopilada. Por ejemplo, puede cambiar `HealthMonitoring` a `Troubleshooting` y aumentar la granularidad de los eventos de traza.  
  
|Palabra clave|Descripción|  
|-------------|-----------------|  
|`HealthMonitoring`|Traza muy ligera y mínima que permite supervisar la actividad del servicio.|  
|`EndToEndMonitoring`|Eventos usados para admitir la traza de flujo de mensajes.|  
|`Troubleshooting`|Eventos más granulares alrededor de los puntos de extensibilidad de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].|  
  
 El segundo grupo de palabras clave define qué componente de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] emitió el evento.  
  
|Palabra clave|Descripción|  
|-------------|-----------------|  
|`UserEvents`|Eventos emitidos por el código de usuario y no [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].|  
|`ServiceModel`|Eventos emitidos por el tiempo de ejecución de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] .|  
|`ServiceHost`|Eventos emitidos por el host de servicio.|  
|`WCFMessageLogging`|Eventos de registro de mensajes de[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] .|  
  
## <a name="see-also"></a>Vea también  
 [Servicios WCF y Seguimiento de eventos para Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
