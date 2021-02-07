---
description: Más información acerca de cómo configurar servicios WCF
title: Configuración de servicios WCF
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: 1c0df8c7d9b4e2b1a032f02e74db2de4a8de020c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720844"
---
# <a name="configuring-wcf-services"></a>Configuración de servicios WCF

Cuando haya diseñado e implementado su contrato de servicios, usted está listo para configurar su servicio. En este momento define y personaliza cómo se expone su servicio a los clientes, además de especificar la dirección donde se puede encontrar, el transporte y codificación de mensajes que utiliza para enviar y recibir mensajes y el tipo de seguridad que requiere.  
  
 La configuración tal y como se utiliza aquí incluye todas las maneras, imperativamente en código o utilizando un archivo de configuración, en el que puede definir y personalizar los diferentes aspectos de un servicio, como especificar sus direcciones de extremo, los transportes utilizados y sus esquemas de seguridad. En la práctica, escribir la configuración es una parte importante de la programación de aplicaciones WCF.  
  
## <a name="in-this-section"></a>En esta sección  

 [Configuración simplificada](simplified-configuration.md)  
 A partir de .NET Framework 4, WCF incluye un nuevo modelo de configuración predeterminado que simplifica los requisitos de configuración de WCF. Si no proporciona ninguna configuración de WCF para un servicio determinado, el tiempo de ejecución configura automáticamente el servicio con los extremos, enlaces y comportamientos predeterminados.  
  
 [Configuración de servicios mediante archivos de configuración](configuring-services-using-configuration-files.md)  
 Un servicio Windows Communication Foundation (WCF) se puede configurar mediante la tecnología de configuración de .NET Framework. Normalmente, los elementos XML se agregan al archivo Web.config para un sitio Internet Information Services (IIS) que hospeda un servicio WCF. Los elementos le permiten cambiar los datos, como las direcciones de punto de conexión (las direcciones reales utilizadas para comunicarse con el servicio) en una base equipo por equipo.  
  
 [Enlaces](bindings.md)  
 Además, WCF incluye varias configuraciones comunes proporcionadas por el sistema en forma de enlaces que permiten seleccionar rápidamente las características más básicas sobre cómo se comunica un cliente y un servicio, como los transportes, la seguridad y las codificaciones de mensajes que se usan.  
  
 [Extremos](endpoints.md)  
 Todas las comunicaciones con un servicio WCF se producen a través de los *puntos de conexión* del servicio. Los puntos de conexión contienen el contrato, la información de configuración que se especifica en los enlaces, y las direcciones que indican dónde encontrar el servicio o dónde obtener información sobre el servicio.  
  
 [Seguridad de servicios](securing-services.md)  
 Con WCF y los mecanismos de seguridad existentes, puede implementar la confidencialidad, la integridad, la autenticación y la autorización en cualquier servicio. También puede revisar los éxitos de seguridad y errores.  
  
 [Creación de servicios interoperables de WS-I Basic Profile 1.1](./creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 Los requisitos para implementar un servicio interoperable con servicios y clientes en cualquier otra plataforma o sistema operativo se describen en la especificación WS-I Basic Profile 1.1.  
  
## <a name="reference"></a>Referencia  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Ciclo de vida de programación básica](basic-programming-lifecycle.md)  
  
 [Diseño e implementación de servicios](designing-and-implementing-services.md)  
  
 [Servicios de hospedaje](hosting-services.md)  
  
 [Creación de clientes](building-clients.md)  
  
 [Introducción a la extensibilidad](introduction-to-extensibility.md)  
  
 [Administración y diagnóstico](./diagnostics/index.md)  
  
## <a name="see-also"></a>Vea también

- [Programación básica de WCF](basic-wcf-programming.md)
- [Información general conceptual](conceptual-overview.md)
- [Detalles de las características de WCF](./feature-details/index.md)
