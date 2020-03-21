---
title: Habilitar dinámicamente la traza analítica
ms.date: 03/30/2017
ms.assetid: 58b63cfc-307a-427d-b69d-9917ff9f44ac
ms.openlocfilehash: 22d122f802e82c2aa04d72a996cb872e06fcaeaa
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78674957"
---
# <a name="dynamically-enabling-analytic-tracing"></a>Habilitar dinámicamente la traza analítica
Con las herramientas que se distribuyen con el sistema operativo Windows, puede habilitar o deshabilitar la traza de forma dinámica mediante el Seguimiento de eventos para Windows (ETW). Para [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] todos los servicios de Windows Communication Foundation (WCF), el seguimiento analítico se puede habilitar y deshabilitar dinámicamente sin modificar el archivo Web.config de la aplicación ni reiniciar el servicio. Esto permite que la aplicación que emite los eventos de traza siga sin más.  
  
 Las opciones de seguimiento de WCF se pueden configurar de forma similar. Por ejemplo, puede cambiar el nivel de gravedad de **Error** a **Información** sin interrumpir a la aplicación. Esto se puede hacer mediante las siguientes herramientas:  
  
- **Logman** . Una herramienta de línea de comandos para configurar, controlar y consultar los datos de la traza. Para obtener más información, consulte [Logman Create Trace](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc788036(v=ws.10)) y [Logman Update Trace](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc788128(v=ws.10)).  
  
- **EventViewer** . Herramienta de administración gráfica de Windows para ver los resultados de la traza. Para obtener más información, vea [Servicios WCF y seguimiento](../../samples/wcf-services-and-event-tracing-for-windows.md) de eventos para Windows y Visor [de](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc766042(v=ws.11))eventos .  
  
- **Perfmon** . Herramienta de administración gráfica de Windows que usa los contadores para supervisar los contadores de traza y los efectos de la traza durante el rendimiento. Para obtener más información, consulte Crear un conjunto de [recopiladores](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc766404(v=ws.11))de datos manualmente .  
  
### <a name="keywords"></a>Palabras clave  
 Al utilizar la clase <xref:System.ServiceModel.Activation.Configuration.ServiceModelActivationSectionGroup.Diagnostics%2A> , los mensajes de traza de .NET Framework se suelen filtrar según el nivel de gravedad (por ejemplo, Error, Advertencia e Información). ETW admite el concepto de nivel de gravedad, pero introduce un mecanismo de filtro nuevo y flexible mediante palabras clave. Las palabras clave son valores textuales arbitrarios que permiten a los eventos de traza proporcionar contexto adicional sobre lo que ese evento significa.  
  
 Para el seguimiento analítico de WCF, cada evento de seguimiento tiene dos tipos de palabras clave. Primero, cada evento tiene una o más palabras clave de escenario. Estas palabras clave indican los escenarios que este evento debería admitir. Hay tres palabras clave de escenario, cada una diseñada para un propósito concreto, tal y como se muestra en la siguiente tabla. Filtrar mediante palabras clave se puede cambiar dinámicamente sin molestar el servicio WCF. Eso significa que puede cambiar de forma dinámica el escenario de traza actual y la cantidad de información de traza recopilada. Por ejemplo, puede cambiar `HealthMonitoring` a `Troubleshooting` y aumentar la granularidad de los eventos de traza.  
  
|Palabra clave|Descripción|  
|-------------|-----------------|  
|`HealthMonitoring`|Traza muy ligera y mínima que permite supervisar la actividad del servicio.|  
|`EndToEndMonitoring`|Eventos usados para admitir la traza de flujo de mensajes.|  
|`Troubleshooting`|Eventos más granulares alrededor de los puntos de extensibilidad de WCF.|  
  
 El segundo grupo de palabras clave define qué componente de .NET Framework emitió el evento.  
  
|Palabra clave|Descripción|  
|-------------|-----------------|  
|`UserEvents`|Eventos emitidos por el código de usuario y no por .NET Framework.|  
|`ServiceModel`|Eventos emitidos por el tiempo de ejecución de WCF.|  
|`ServiceHost`|Eventos emitidos por el host de servicio.|  
|`WCFMessageLogging`|Eventos de registro de mensajes WCF.|  
  
## <a name="see-also"></a>Consulte también

- [WCF Services and Event Tracing for Windows](../../samples/wcf-services-and-event-tracing-for-windows.md)
