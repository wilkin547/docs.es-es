---
title: "Configuración de servicios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de970bf27fdf3365daa0ac515852a68d01a246eb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-services"></a>Configuración de servicios
Cuando haya diseñado e implementado su contrato de servicios, usted está listo para configurar su servicio. En este momento define y personaliza cómo se expone su servicio a los clientes, además de especificar la dirección donde se puede encontrar, el transporte y codificación de mensajes que utiliza para enviar y recibir mensajes y el tipo de seguridad que requiere.  
  
 La configuración tal y como se utiliza aquí incluye todas las maneras, imperativamente en código o utilizando un archivo de configuración, en el que puede definir y personalizar los diferentes aspectos de un servicio, como especificar sus direcciones de extremo, los transportes utilizados y sus esquemas de seguridad. En la práctica, escribir la configuración es una parte principal de la programación de aplicaciones de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .  
  
## <a name="in-this-section"></a>En esta sección  
 [Configuración simplificada](../../../docs/framework/wcf/simplified-configuration.md)  
 A partir de [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye un nuevo modelo de configuración predeterminado que simplifica los requisitos de configuración de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] . Si no se proporciona ninguna configuración de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para un servicio concreto, el tiempo de ejecución lo configurará automáticamente con extremos, enlaces y comportamientos predeterminados.  
  
 [Configuración de servicios mediante archivos de configuración](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 Se puede configurar un servicio de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] mediante la tecnología de configuración [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]. Por lo general, los elementos XML se agregan al archivo Web.config para un sitio de Internet Information Services (IIS) que hospeda un servicio [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Los elementos le permiten cambiar los datos, como las direcciones de punto de conexión (las direcciones reales utilizadas para comunicarse con el servicio) en una base equipo por equipo.  
  
 [Enlaces](../../../docs/framework/wcf/bindings.md)  
 Además, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye varias configuraciones comunes proporcionadas por el sistema en forma de enlaces que le permiten seleccionar rápidamente las características más básicas sobre cómo se comunican un cliente y el servicio, como los transportes, seguridad y codificación de mensajes utilizadas.  
  
 [Puntos de conexión](../../../docs/framework/wcf/endpoints.md)  
 Toda la comunicación con un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio se produce a través de la *extremos* del servicio. Los puntos de conexión contienen el contrato, la información de configuración que se especifica en los enlaces, y las direcciones que indican dónde encontrar el servicio o dónde obtener información sobre el servicio.  
  
 [Seguridad de servicios](../../../docs/framework/wcf/securing-services.md)  
 Utilizando [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y mecanismos de seguridad existentes, puede implementar confidencialidad, integridad, autenticación y autorización en cualquier servicio. También puede revisar los éxitos de seguridad y errores.  
  
 [Creación de servicios interoperables de WS-I Basic Profile 1.1](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 Los requisitos para implementar un servicio interoperable con servicios y clientes en cualquier otra plataforma o sistema operativo se describen en la especificación WS-I Basic Profile 1.1.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ciclo de vida de programación básica](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [Diseño e implementación de servicios](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [Servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md)  
  
 [Creación de clientes](../../../docs/framework/wcf/building-clients.md)  
  
 [Introducción a la extensibilidad](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [Administración y diagnóstico](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a>Vea también  
 [Programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Información conceptual](../../../docs/framework/wcf/conceptual-overview.md)  
 [Detalles de las características de WCF](../../../docs/framework/wcf/feature-details/index.md)
