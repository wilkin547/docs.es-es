---
title: Migración de los servicios web ASP.NET a WCF
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: 7d43c66952d17a91e38ae1b086478b9416321b8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migración de los servicios web ASP.NET a WCF
ASP.NET proporciona bibliotecas de clases y las herramientas de .NET Framework para compilar servicios web, así como funciones para hospedar servicios dentro de Internet Information Services (IIS). Windows Communication Foundation (WCF) proporciona bibliotecas de clases de .NET Framework, herramientas y funciones de hospedaje para que las entidades de software puedan comunicarse usando cualquier protocolo, los usados por los servicios Web incluidos.  Migrar servicios Web de ASP.NET a WCF permite que sus aplicaciones aprovechar las nuevas características y mejoras que son exclusivas de WCF.  
  
 WCF tiene varias ventajas importantes con respecto a los servicios Web ASP.NET. Mientras que herramientas de servicios Web ASP.NET son solo sirven para crear servicios Web, WCF proporciona herramientas que se pueden usar cuando se deben crear entidades de software para comunicarse entre sí. Esto reducirá el número de tecnologías que deben conocer los desarrolladores para adaptarse a distintos escenarios de comunicación de software, que a su vez reducirán el coste de los recursos de desarrollo de software y el tiempo para finalizar los proyectos de desarrollo de software.  
  
 Incluso para los proyectos de desarrollo de servicios Web, WCF admite más protocolos de servicios Web de compatibilidad con servicios Web de ASP.NET. Estos protocolos adicionales proporcionan más soluciones sofisticadas, como sesiones y transacciones confiables, entre otras.  
  
 WCF admite más protocolos para transportar mensajes a los servicios Web ASP.NET. Los servicios web de ASP.NET solo admiten el envío de mensajes mediante el Protocolo de transferencia de hipertexto (HTTP). WCF admite el envío de mensajes mediante HTTP, así como el protocolo de Control de transmisión (TCP), que canalizaciones con nombre y Microsoft Message Queuing (MSMQ). Más importante, WCF puede ampliarse para admitir protocolos de transporte adicionales. Por lo tanto, el software desarrollado con WCF pueden adaptarse para trabajar con una amplia variedad de otro software, con lo que aumenta el rendimiento potencial de la inversión.  
  
 WCF proporciona medios con más funciones para implementar y administrar aplicaciones de servicios Web de ASP.NET. Además de un sistema de configuración, que también tiene ASP.NET, WCF ofrece un editor de configuración de seguimiento de actividades desde remitentes a receptores y de vuelta a través de intermediarios, un visor de seguimiento, registro de mensajes, una gran cantidad de contadores de rendimiento, y compatibilidad con Instrumental de administración de Windows.  
  
 Dados estos beneficios potenciales de WCF en relación con ASP.NET Web services, si está usando, o está pensando en utilizar los servicios Web ASP.NET que tiene varias opciones:  
  
-   Continuar usar los servicios Web ASP.NET y Prescinda de las ventajas ofrecidas por WCF.  
  
-   Seguir usando los servicios Web ASP.NET con la intención de adoptar WCF en algún momento en el futuro. Los temas de esta sección explican cómo maximizar las perspectivas para poder usar nuevas aplicaciones de servicio Web ASP.NET junto con las aplicaciones WCF futuras. Los temas de esta sección también explican cómo crear nuevo Web de ASP.NET servicios con el fin de que sea más fácil migrarlos a WCF. Sin embargo, si proteger los servicios es importante o se necesitan garantías de confiabilidad o transacción, o si personalizada tendrán que construirse medios de administración, es más adecuado es adoptar WCF. WCF está diseñado precisamente para tales escenarios.  
  
-   Se han adoptado WCF para nuevas implementaciones, mientras continúa manteniendo las aplicaciones de servicio Web ASP.NET existentes. Es muy probable que esta opción sea la óptima. Las ventajas de WCF, produce mientras se ahorra el costo consiste en modificar las aplicaciones existentes para usarlo. En este escenario, nuevas aplicaciones WCF pueden coexistir con aplicaciones de ASP.NET existentes. Nuevas aplicaciones de WCF, podrán usar los servicios Web de ASP.NET existentes y WCF puede utilizarse para programar nuevas capacidades operativos en las aplicaciones de ASP.NET existentes en virtud de modo de compatibilidad ASP.NET de WCF.  
  
-   Adoptar WCF y migrar las aplicaciones de servicio Web ASP.NET existentes a WCF. Puede elegir esta opción para mejorar las aplicaciones existentes con características proporcionadas por WCF, o para reproducir la funcionalidad de servicios Web ASP.NET existentes dentro de nuevas, aplicaciones de WCF más eficaces.  
  
> [!NOTE]
>  Se debe tener cuidado si un servicio WCF se hospeda en IIS 5.x y se desinstala ASP.NET. Cuando un servicio WCF está hospedado en IIS 5.x, el código para el servicio se puede solicitar si se desinstala ASP.NET. Cuando ASP.NET se desinstala en un sistema operativo que está ejecutando IIS 5.x y WCF se desinstala, se considerará un archivo de texto a un archivo con la extensión .svc y el contenido, incluido cualquier código fuente, se devuelve al solicitante.  
  
 En esta sección se describe en detalle estas opciones, compara los servicios Web ASP.NET a WCF y proporciona instrucciones sobre cómo migrar el código de servicios Web ASP.NET a WCF.  
  
## <a name="see-also"></a>Vea también  
 [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)  
 [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)  
 [Adopción de Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)  
 [Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)  
 [Comparación de los servicios web ASP.NET con el WCF basado en desarrollo](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
