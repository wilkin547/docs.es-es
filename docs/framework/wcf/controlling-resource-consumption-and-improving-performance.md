---
title: Control del consumo de recursos y mejora del rendimiento
ms.date: 03/30/2017
ms.assetid: 9a829669-5f76-4c88-80ec-92d0c62c0660
ms.openlocfilehash: f06dd0b7e66ae783b2f268551f15c5e6e8369b7f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255070"
---
# <a name="controlling-resource-consumption-and-improving-performance"></a>Control del consumo de recursos y mejora del rendimiento

En este tema se describen las distintas propiedades de las distintas áreas de la arquitectura Windows Communication Foundation (WCF) que funcionan para controlar el consumo de recursos y afectar a las métricas de rendimiento.

## <a name="properties-that-constrain-resource-consumption-in-wcf"></a>Propiedades que restringen el consumo de recursos en WCF

 Windows Communication Foundation (WCF) aplica restricciones en determinados tipos de procesos, ya sea con fines de seguridad o de rendimiento. Estas restricciones adquieren dos formas básicas: cuotas y aceleradores. Las *cuotas* son límites cuando se alcanza o se supera el desencadenamiento de una excepción inmediata en algún punto del sistema. Las *limitaciones* son límites que no provocan inmediatamente que se produzca una excepción. En su lugar, cuando se alcanza el límite del acelerador, el procesamiento continúa pero dentro de los límites establecidos por ese valor. Este procesamiento limitado puede activar una excepción en otra parte, pero esto depende de la aplicación.

 Además de la distinción entre cuotas y aceleradores, algunas propiedades de restricción se encuentran en el nivel de serialización, algunas en el nivel de transporte y algunas en el nivel de aplicación. Por ejemplo, la cuota <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=nameWithType>, que implementan todos los elementos de enlace de transporte proporcionados por el sistema, está establecida de forma predeterminada en 65.536 bytes para impedir que los clientes malintencionados emprendan ataques de denegación de servicio contra un servicio provocando el consumo excesivo de memoria. (Normalmente, puede aumentar el rendimiento bajando este valor.)

 Un ejemplo de una cuota de la serialización es la propiedad <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=nameWithType>, que especifica el número máximo de objetos que el serializador serializa o deserializa en una única llamada al método <xref:System.Runtime.Serialization.DataContractSerializer.ReadObject%2A>. Un ejemplo de un acelerador en el nivel de aplicación es la propiedad <xref:System.ServiceModel.Dispatcher.ServiceThrottle.MaxConcurrentSessions%2A?displayProperty=nameWithType>, que de forma predeterminada restringe el número de conexiones de canal con sesión simultáneas a 10. (A diferencia de las cuotas, si se alcanza este valor de acelerador, la aplicación continúa con el procesamiento pero no acepta nuevos canales con sesión, lo que significa que los nuevos clientes no se pueden conectar hasta que uno de los otros canales con sesión haya finalizado.)

 Estos controles están diseñados para proporcionar una mitigación rápida contra ciertos tipos de ataques o para mejorar métrica de rendimiento tal como el consumo de memoria, el tiempo de inicio, etc. Sin embargo, dependiendo de la aplicación, estos controles pueden impedir el rendimiento de la aplicación del servicio o evitar que la aplicación funcione. Por ejemplo, una aplicación diseñada para transmitir secuencias de vídeo puede superar con facilidad la propiedad <xref:System.ServiceModel.Channels.TransportBindingElement.MaxReceivedMessageSize%2A?displayProperty=nameWithType> predeterminada. En este tema se proporciona información general sobre los distintos controles que se aplican a las aplicaciones en todos los niveles de WCF, se describen varias maneras de obtener más información sobre si un valor de configuración está obstaculizando la aplicación y se describen las formas de corregir diversos problemas. La mayoría de los aceleradores y algunas cuotas están disponibles en el nivel de aplicación, incluso cuando la propiedad base es una serialización o una restricción de transporte. Por ejemplo, puede establecer la propiedad <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A?displayProperty=nameWithType> utilizando la propiedad <xref:System.ServiceModel.ServiceBehaviorAttribute.MaxItemsInObjectGraph%2A?displayProperty=nameWithType> en la clase de servicio.

> [!NOTE]
> Si tiene un problema determinado, primero debe leer la guía de [Inicio rápido de solución de problemas de WCF](wcf-troubleshooting-quickstart.md) para ver si el problema (y una solución) aparece en la lista.

 Las propiedades que restringen los procesos de serialización se enumeran en [consideraciones de seguridad para los datos](./feature-details/security-considerations-for-data.md). Las propiedades que restringen el consumo de recursos relacionados con los transportes se enumeran en [cuotas de transporte](./feature-details/transport-quotas.md). Las propiedades que restringen el consumo de recursos en el nivel de aplicación son los miembros de la clase <xref:System.ServiceModel.Dispatcher.ServiceThrottle>.

## <a name="detecting-application-and-performance-issues-related-to-quota-settings"></a>Detectar la aplicación y los problemas de rendimiento relacionados con los valores de cuota

 Los valores predeterminados de los valores anteriores se han elegido para habilitar la funcionalidad de la aplicación básica en una amplia gama de tipos de aplicación proporcionando al mismo tiempo protección básica contra los problemas de seguridad comunes. Sin embargo, los diseños de las diferentes aplicaciones pueden superar uno o más valores de acelerador aunque por otro lado la aplicación sea segura y funcione como se ha diseñado. En estos casos, debe identificar qué valores de acelerador se superan y en qué nivel, y decidir la acción adecuada para aumentar el rendimiento de la aplicación.

 Normalmente, al escribir la aplicación y depurarla, establece la propiedad <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> en `true` en el archivo de configuración o mediante programación. Esto indica a WCF que devuelva los seguimientos de la pila de excepciones de servicio a la aplicación cliente para su visualización. Esta característica crea informes de la mayoría de las excepciones en el nivel de aplicación de manera que se muestran qué valores de cuota podrían estar implicados, si ése es el problema.

 En tiempo de ejecución se producen algunas excepciones bajo el nivel de aplicación visible y no se devuelven por medio de este mecanismo ni pueden controlarse mediante una implementación <xref:System.ServiceModel.Dispatcher.IErrorHandler?displayProperty=nameWithType> personalizada. Si está en un entorno de desarrollo como Microsoft Visual Studio, la mayoría de estas excepciones se muestran automáticamente. Sin embargo, algunas excepciones se pueden enmascarar según la configuración del entorno de desarrollo, como [solo mi código](/visualstudio/debugger/just-my-code) Visual Studio.

 Independientemente de las capacidades del entorno de desarrollo, puede usar las capacidades del seguimiento de WCF y del registro de mensajes para depurar todas las excepciones y optimizar el rendimiento de las aplicaciones. Para obtener más información, consulte [uso del seguimiento para solucionar problemas de la aplicación](./diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md).

## <a name="performance-issues-and-xmlserializer"></a>Problemas de rendimiento y XmlSerializer

 Los servicios y las aplicaciones cliente que usan tipos de datos que son serializables mediante <xref:System.Xml.Serialization.XmlSerializer> generan y compilan el código de serialización de los tipos de datos en tiempo de ejecución, lo que se puede traducir en un rendimiento de inicio lento.

> [!NOTE]
> El código de serialización generado previamente solo puede usarse en aplicaciones cliente, no en servicios.

 La [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) puede mejorar el rendimiento de inicio de estas aplicaciones mediante la generación del código de serialización necesario a partir de los ensamblados compilados para la aplicación. Para obtener más información, vea [Cómo: mejorar el tiempo de inicio de las aplicaciones cliente WCF mediante XmlSerializer](./feature-details/startup-time-of-wcf-client-applications-using-the-xmlserializer.md).

## <a name="performance-issues-when-hosting-wcf-services-under-aspnet"></a>Problemas de rendimiento al hospedar los servicios WCF bajo ASP.NET

Cuando un servicio WCF se hospeda bajo IIS y ASP.NET, la configuración de IIS y ASP.NET puede afectar al rendimiento y al consumo de memoria del servicio WCF.  Para obtener más información sobre el rendimiento de ASP.NET, vea [mejorar el rendimiento de ASP.net](/previous-versions/msp-n-p/ff647787(v=pandp.10)). Una configuración que quizá pueda tener consecuencias imprevistas es la propiedad <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A>, que es una propiedad de la clase <xref:System.Web.Configuration.ProcessModelSection>. Si la aplicación tiene un número fijo o pequeño de clientes, al establecer <xref:System.Web.Configuration.ProcessModelSection.MinWorkerThreads%2A> en 2 se podría observar un aumento del rendimiento en un equipo con varios procesadores que tenga un uso de CPU próximo al 100%. Esta mejora del rendimiento tiene su precio: aumentará también el consumo de memoria, lo que podría disminuir la escalabilidad.

## <a name="see-also"></a>Vea también

- [Administración y diagnóstico](./diagnostics/index.md)
- [Datos de gran tamaño y secuencias](./feature-details/large-data-and-streaming.md)
