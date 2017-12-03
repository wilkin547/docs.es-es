---
title: "Migración de los servicios web ASP.NET a WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ca1eb73842f3f7dac5557c1eafff637396d317a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migración de los servicios web ASP.NET a WCF
ASP.NET proporciona bibliotecas de clases y las herramientas de .NET Framework para compilar servicios web, así como funciones para hospedar servicios dentro de Internet Information Services (IIS). [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporciona bibliotecas de clases de .NET Framework, herramientas y funciones de hospedaje para que las entidades de software puedan comunicarse usando cualquier protocolo, incluidos los usados por servicios web.  Migrar los servicios web de ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] permite que las aplicaciones saquen el máximo partido a las nuevas características y mejoras que son exclusivas de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cuenta con varias ventajas importantes relacionadas con los servicios web de ASP.NET. Mientras que las herramientas de estos servicios solo sirven para crear servicios web, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona herramientas que pueden utilizarse cuando se deben crear entidades de software para comunicarse entre ellas. Esto reducirá el número de tecnologías que deben conocer los desarrolladores para adaptarse a distintos escenarios de comunicación de software, que a su vez reducirán el coste de los recursos de desarrollo de software y el tiempo para finalizar los proyectos de desarrollo de software.  
  
 Incluso para los proyectos de desarrollo de los servicios web, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite más protocolos de servicios web que los admitidos por los servicios web de ASP.NET. Estos protocolos adicionales proporcionan más soluciones sofisticadas, como sesiones y transacciones confiables, entre otras.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite más protocolos para transportar mensajes que los servicios web de ASP.NET. Los servicios web de ASP.NET solo admiten el envío de mensajes mediante el Protocolo de transferencia de hipertexto (HTTP). [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite el envío de mensajes mediante HTTP, así como el Protocolo de control de transmisión (TCP), canalizaciones con nombre y Microsoft Message Queuing (MSMQ). Y lo que es más importante, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede extenderse para admitir protocolos de transporte adicionales. Por consiguiente, el software desarrollado con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede adaptarse para trabajar con una amplia variedad de otro software, con lo que se aumenta la devolución potencial de la inversión.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona medios con más funciones para implementar y administrar las aplicaciones que los servicios web de ASP.NET proporcionan. Además de un sistema de configuración, que ASP.NET también tiene, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona un editor de configuración, seguimiento de actividades desde remitentes a receptores y de vuelta a través de intermediarios, un visor de seguimiento, registro de mensajes, un inmenso número de contadores de rendimiento y compatibilidad con el Instrumental de administración de Windows (WMI).  
  
 Dados estos beneficios potenciales de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] relacionados con los servicios web de ASP.NET, si está utilizando, o está pensando en utilizar los servicios web de ASP.NET, tiene varias opciones:  
  
-   Continúe utilizando los servicios web de ASP.NET y prescinda de las ventajas ofrecidas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Siga utilizando los servicios web de ASP.NET con la intención de adoptar en algún momento [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en el futuro. Los temas en esta sección explican cómo maximizar las perspectivas para poder utilizar las nuevas aplicaciones de servicio web ASP.NET junto con las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] futuras. Los temas en esta sección también explican cómo crear los nuevos servicios web de ASP.NET para facilitar su migración a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Sin embargo, si proteger los servicios es importante, si son necesarias garantías de confiabilidad o transacción, o si tendrán que construirse medios de administración personalizados, lo más adecuado es adoptar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] está diseñado precisamente para tales escenarios.  
  
-   Adopte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para el nuevo desarrollo, mientras continúa manteniendo las aplicaciones de servicios web de ASP.NET existentes. Es muy probable que esta opción sea la óptima. Cuenta con las ventajas de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mientras se ahorra el coste de modificar las aplicaciones existentes para usarlo. En este escenario, las nuevas aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden coexistir con aplicaciones ASP.NET anteriores. Las nuevas aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] podrán utilizar servicios web de ASP.NET existentes. Además, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] puede utilizarse para programar nuevas capacidades operativos en aplicaciones de ASP.NET existentes según el modo de compatibilidad de ASP.NET de  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Adopte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y migre las aplicaciones de servicios web de ASP.NET existentes a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Puede elegir esta opción para mejorar las aplicaciones existentes con características proporcionadas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] o para reproducir la funcionalidad de los servicios web de ASP.NET existentes dentro de nuevas aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] más potentes.  
  
> [!NOTE]
>  Se debe tener cuidado si IIS 5.x hospeda un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y se desinstala ASP.NET. Cuando IIS 5.x hospeda un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], se puede solicitar el código para el servicio si se desinstala ASP.NET. Cuando ASP.NET se desinstala en un sistema operativo que está ejecutando IIS 5.x y se desinstala [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], se considerará un archivo de texto un archivo con la extensión .svc y el contenido, incluido cualquier código fuente, se devuelve al solicitante.  
  
 Esta sección describe en detalle estas opciones, compara los servicios web de ASP.NET con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y proporciona las instrucciones sobre cómo migrar el código de los servicios web de ASP.NET a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)  
 [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)  
 [Adopción de Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)  
 [Comparación de los servicios Web de ASP.NET a WCF basado en el propósito y las normas utilizadas](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)  
 [Comparación de los servicios Web de ASP.NET a WCF basado en desarrollo](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
