---
title: Migración de los servicios web ASP.NET a WCF
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: fa707a4246d5bc9940417072c098b2973140f878
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598806"
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migración de los servicios web ASP.NET a WCF
ASP.NET proporciona bibliotecas de clases y las herramientas de .NET Framework para compilar servicios web, así como funciones para hospedar servicios dentro de Internet Information Services (IIS). Windows Communication Foundation (WCF) proporciona bibliotecas de clases de .NET Framework, herramientas y funciones de hospedaje para permitir que las entidades de software se comuniquen mediante cualquier protocolo, incluidos los usados por los servicios Web.  La migración de los servicios Web de ASP.NET a WCF permite a las aplicaciones aprovechar las nuevas características y mejoras que son exclusivas de WCF.  
  
 WCF tiene varias ventajas importantes en relación con los servicios Web de ASP.NET. Aunque las herramientas de servicios Web de ASP.NET solo sirven para crear servicios Web, WCF proporciona herramientas que se pueden usar cuando se deben realizar entidades de software para comunicarse entre sí. Esto reducirá el número de tecnologías que deben conocer los desarrolladores para adaptarse a distintos escenarios de comunicación de software, que a su vez reducirán el coste de los recursos de desarrollo de software y el tiempo para finalizar los proyectos de desarrollo de software.  
  
 Incluso en el caso de los proyectos de desarrollo de servicios Web, WCF admite más protocolos de servicios web que la compatibilidad con los servicios Web de ASP.NET. Estos protocolos adicionales proporcionan más soluciones sofisticadas, como sesiones y transacciones confiables, entre otras.  
  
 WCF admite más protocolos para transportar mensajes que los servicios Web de ASP.NET. Los servicios web de ASP.NET solo admiten el envío de mensajes mediante el Protocolo de transferencia de hipertexto (HTTP). WCF admite el envío de mensajes mediante HTTP, así como el protocolo de control de transmisión (TCP), canalizaciones con nombre y Microsoft Message Queuing (MSMQ). Y lo que es más importante, WCF se puede extender para admitir protocolos de transporte adicionales. Por lo tanto, el software desarrollado mediante WCF se puede adaptar para trabajar junto con una variedad más amplia de software, lo que aumenta el rendimiento potencial de la inversión.  
  
 WCF proporciona medios mucho más completos para implementar y administrar aplicaciones que los servicios Web de ASP.NET. Además de un sistema de configuración, que también tiene ASP.NET, WCF ofrece un editor de configuración, seguimiento de la actividad de remitentes a receptores y de vuelta a través de cualquier número de intermediarios, un visor de seguimiento, registro de mensajes, un gran número de contadores de rendimiento y compatibilidad para Instrumental de administración de Windows.  
  
 Dadas estas posibles ventajas de WCF en relación con los servicios Web de ASP.NET, si usa o está considerando la posibilidad de usar los servicios Web de ASP.NET, tiene varias opciones:  
  
- Siga usando los servicios Web de ASP.NET y, en virtud de las ventajas, ofrecidos de WCF.  
  
- Siga usando los servicios Web de ASP.NET con la intención de adoptar WCF en algún momento en el futuro. En los temas de esta sección se explica cómo maximizar los posibles clientes para poder usar las nuevas aplicaciones de servicio Web de ASP.NET junto con futuras aplicaciones WCF. En los temas de esta sección también se explica cómo crear nuevos servicios Web ASP.NET para que sea más fácil migrarlos a WCF. Sin embargo, si la protección de los servicios es importante, o si se requieren garantías de confiabilidad o transacción, o si se deben construir instalaciones de administración personalizadas, es una opción mejor adoptar WCF. WCF está diseñado para tales escenarios con precisión.  
  
- Adopte WCF para el nuevo desarrollo y siga manteniendo las aplicaciones de servicio Web de ASP.NET existentes. Es muy probable que esta opción sea la óptima. Ofrece las ventajas de WCF, a la vez que se reserva el costo de modificar las aplicaciones existentes para usarla. En este escenario, las aplicaciones WCF nuevas pueden coexistir con aplicaciones existentes de ASP.NET. Las nuevas aplicaciones WCF podrán usar los servicios Web de ASP.NET existentes y WCF se puede usar para programar nuevas capacidades operativas en aplicaciones ASP.NET existentes en virtud del modo de compatibilidad ASP.NET de WCF.  
  
- Adopte WCF y migre las aplicaciones de servicio Web de ASP.NET existentes a WCF. Puede elegir esta opción para mejorar las aplicaciones existentes con las características proporcionadas por WCF o para reproducir la funcionalidad de los servicios Web de ASP.NET existentes en aplicaciones WCF nuevas y más eficaces.  
  
> [!NOTE]
> Se debe tener cuidado si IIS 5. x hospeda un servicio WCF y se desinstala ASP.NET. Cuando IIS 5. x hospeda un servicio WCF, se puede solicitar el código para el servicio si se desinstala ASP.NET. Cuando se desinstala ASP.NET en un sistema operativo en el que se ejecuta IIS 5. x y se desinstala WCF, un archivo con la extensión. SVC se considera un archivo de texto y el contenido, incluido el código fuente, se devuelve al solicitante.  
  
 En esta sección se describen estas opciones en detalle, se comparan los servicios Web ASP.NET con WCF y se proporcionan instrucciones sobre cómo migrar el código de servicios Web de ASP.NET a WCF.  
  
## <a name="see-also"></a>Vea también

- [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura migración](anticipating-adopting-wcf-migration.md)
- [Anticipación de la adopción de Windows Communication Foundation: cómo facilitar la futura integración](anticipating-adopting-the-wcf-easing-future-integration.md)
- [Adoptación de Windows Communication Foundation](adopting-wcf.md)
- [Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas](comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
- [Comparación de los servicios web ASP.NET con el WCF basado en desarrollo](comparing-aspnet-web-services-to-wcf-based-on-development.md)
