---
title: ¿Qué es Windows Communication Foundation?
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], technology overview
- technology overview [WCF]
- WCF [WCF], technology overview
ms.assetid: 40e1009d-ef15-450b-9848-62eabe5e5738
caps.latest.revision: 51
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e194a0784eb27043bbd0c127cde6883b4fafb2e
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="what-is-windows-communication-foundation"></a>¿Qué es Windows Communication Foundation?
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] es un marco de trabajo para la creación de aplicaciones orientadas a servicios. Con [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], es posible enviar datos como mensajes asincrónicos de un extremo de servicio a otro. Un extremo de servicio puede formar parte de un servicio disponible continuamente hospedado por IIS, o puede ser un servicio hospedado en una aplicación. Un extremo puede ser un cliente de un servicio que solicita datos de un extremo de servicio. Los mensajes pueden ser tan simples como un carácter o una palabra que se envía como XML, o tan complejos como una secuencia de datos binarios. A continuación se indican unos cuantos escenarios de ejemplo:  
  
-   Un servicio seguro para procesar transacciones comerciales.  
  
-   Un servicio que proporciona datos actualizados a otras personas, como un informe sobre tráfico u otro servicio de supervisión.  
  
-   Un servicio de chat que permite a dos personas comunicarse o intercambiar datos en tiempo real.  
  
-   Una aplicación de panel que sondea los datos de uno o varios servicios y los muestra en una presentación lógica.  
  
-   Exponer un flujo de trabajo implementado utilizando Windows Workflow Foundation como un servicio WCF.  
  
-   Una aplicación de Silverlight para sondear un servicio en busca de las fuentes de datos más recientes.  
  
 Si bien era posible crear tales aplicaciones antes de que existiera [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], con [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] el desarrollo de extremos resulta más sencillo que nunca. En resumen, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se ha diseñado para ofrecer un enfoque manejable para la creación de servicios web y clientes de servicios web.  
  
## <a name="features-of-wcf"></a>Características de WCF  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye el siguiente conjunto de características: [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [WCF Feature Details](../../../docs/framework/wcf/feature-details/index.md).  
  
-   **Orientación a servicios**  
  
     Como consecuencia del uso de los estándares de WS, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] le permite crear aplicaciones *orientadas a servicios* . SOA, la arquitectura orientada a servicios es el uso de servicios web para enviar y recibir datos. Los servicios tienen la ventaja general de estar débilmente acoplados entre una aplicación y otra en lugar de incluidos en el código. Una relación de acoplamiento débil implica que cualquier cliente creado en cualquier plataforma puede conectar con cualquier servicio siempre y cuando se cumplan los contratos esenciales.  
  
-   **Interoperabilidad**  
  
     [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] implementa los estándares del sector modernos para la interoperabilidad de servicios web. [!INCLUDE[crabout](../../../includes/crabout-md.md)] los estándares admitidos, consulte [Interoperability and Integration](../../../docs/framework/wcf/feature-details/interoperability-and-integration.md).  
  
-   **Varios patrones de mensajes**  
  
     Los mensajes se intercambian mediante uno de los distintos patrones. El más común es el de solicitud/respuesta, en que un extremo solicita datos de otro extremo. y el otro extremo responde. Existen otros patrones, como un mensaje unidireccional, en que un único extremo envía un mensaje sin esperar ninguna respuesta. Un patrón más complejo es el patrón de intercambio dúplex donde dos extremos establecen una conexión y envían datos hacia delante y hacia atrás, similar a un programa de mensajería instantánea. [!INCLUDE[crabout](../../../includes/crabout-md.md)] cómo implementar diferentes patrones de intercambio de mensajes mediante [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] , consulte [Contracts](../../../docs/framework/wcf/feature-details/contracts.md).  
  
-   **Metadatos de servicios**  
  
     [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] admite la publicación de metadatos de servicios utilizando los formatos especificados en los estándares de la industria, como WSDL, Esquemas XML y WS-Policy. Estos metadatos pueden utilizarse para generar y configurar automáticamente clientes para el acceso a los servicios de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] . Los metadatos se pueden publicar sobre HTTP y HTTPS, o utilizando el estándar Intercambio de metadatos de servicios web. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Metadata](../../../docs/framework/wcf/feature-details/metadata.md).  
  
-   **Contratos de datos**  
  
     Dado que [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se basa en [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], también incluye métodos con código sencillo para proporcionar los contratos que desea aplicar. Uno de los tipos de contrato universales es el contrato de datos. Básicamente, mientras se escribe el código del servicio usando Visual C# o Visual Basic, la forma más sencilla de controlar los datos consiste en crear clases que representan una entidad de datos con propiedades que pertenecen a la misma. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye un completo sistema para trabajar con datos de esta manera fácil. Cuando se han creado las clases que representan los datos, el servicio genera automáticamente los metadatos que permiten a los clientes ajustarse a los tipos de datos que se han diseñado. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Using Data Contracts](../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
  
-   **Seguridad**  
  
     Es posible cifrar los mensajes para proteger la privacidad, así como obligar a los usuarios a que se autentiquen antes de permitirles recibir mensajes. La seguridad puede implementarse utilizando estándares conocidos como SSL o WS-SecureConversation. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Seguridad](../../../docs/framework/wcf/feature-details/security.md).  
  
-   **Varios transportes y codificaciones**  
  
     Los mensajes pueden enviarse con cualquiera de los protocolos y codificaciones integrados. Cuanto más frecuente de protocolo y codificación consiste en enviar texto codificado mensajes SOAP mediante el protocolo de transferencia de hipertexto (HTTP) para su uso en World Wide Web. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] también le permite enviar mensajes sobre TCP, canalizaciones con nombre o MSMQ. Estos mensajes pueden codificarse como texto o utilizando un formato binario optimizado.  Los datos binarios pueden enviarse de manera eficaz utilizando el estándar MTOM. Si ninguno de los transportes o codificaciones proporcionados satisface sus necesidades, puede crear uno personalizado. [!INCLUDE[crabout](../../../includes/crabout-md.md)] transportes y codificaciones admitidos por [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] vea [transportes](../../../docs/framework/wcf/feature-details/transports.md).  
  
-   **Mensajes confiables y en cola**  
  
     [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] admite intercambio de mensajes confiable usando sesiones confiables implementadas sobre mensajería WS-Reliable y mediante MSMQ. [!INCLUDE[crabout](../../../includes/crabout-md.md)] la compatibilidad con mensajería confiable y en cola en [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] , consulte [Queues and Reliable Sessions](../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).  
  
-   **Mensajes duraderos**  
  
     Un mensaje duradero es aquel que nunca se pierde debido a una interrupción de la comunicación. Los mensajes que forman parte de un patrón de mensajes duraderos siempre se guardan en una base de datos. Si se produce una interrupción, la base de datos le permite reanudar el intercambio de mensajes cuando se restablezca la conexión. También puede crear un mensaje duradero utilizando [!INCLUDE[wf](../../../includes/wf-md.md)]. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Workflow Services](../../../docs/framework/wcf/feature-details/workflow-services.md).  
  
-   **Transacciones**  
  
     WCF también admite las transacciones que usan uno de los tres modelos de transacción: las transacciones WS-Atomic, las API del espacio de nombres <xref:System.Transactions> y Coordinador de transacciones distribuidas de Microsoft. [!INCLUDE[crabout](../../../includes/crabout-md.md)] la compatibilidad con transacciones en [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] , consulte [Transacciones](../../../docs/framework/wcf/feature-details/transactions-in-wcf.md).  
  
-   **Compatibilidad con AJAX y REST**  
  
     REST es un ejemplo de una tecnología de la Web 2.0 en evolución. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se puede configurar para procesar datos XML “sin formato” que no se ajustan en un sobre SOAP. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] también se puede extender para admitir formatos XML concretos, como ATOM (un estándar popular de RSS), e incluso formatos no XML, como notación de objetos JavaScript (JSON).  
  
-   **Extensibilidad**  
  
     La arquitectura de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] tiene varios puntos de extensibilidad. Si se necesita una función adicional, existen una serie de puntos de entrada que le permiten personalizar el comportamiento de un servicio. [!INCLUDE[crabout](../../../includes/crabout-md.md)] puntos de extensibilidad disponibles, consulte [extensión de WCF](../../../docs/framework/wcf/extending/index.md).  
  
## <a name="wcf-integration-with-other-microsoft-technologies"></a>Integración de WCF con otras tecnologías de Microsoft  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] es una plataforma flexible. Debido a esta flexibilidad extrema, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] también se usa en varios otros productos Microsoft. Si comprende los fundamentos de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], tendrá una ventaja inmediata si también utiliza cualquiera de estos productos.  
  
 La primera tecnología en adaptarse a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] fue Windows Workflow Foundation (WF). Los flujos de trabajo simplifican el desarrollo de aplicaciones encapsulando los pasos del flujo de trabajo como "actividades". En la primera versión de [!INCLUDE[wf2](../../../includes/wf2-md.md)], un desarrollador tenía que crear un host para el flujo de trabajo. La versión siguiente de [!INCLUDE[wf2](../../../includes/wf2-md.md)] se integró con [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Esto permitió hospedar cualquier flujo de trabajo fácilmente en un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ; puede hacer esto si elige automáticamente el tipo de proyecto WF/WCF en [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].  
  
 Microsoft BizTalk Server R2 también utiliza [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] como tecnología de comunicaciones. BizTalk está diseñado para recibir y transformar datos de un formato normalizado en otro. Los mensajes deben entregarse en su cuadro de mensajes central, donde es posible transformar el mensaje utilizando una asignación estricta o mediante una de las características de BizTalk, como su motor de flujo de trabajo. BizTalk ahora puede utilizar el adaptador de línea de negocio (LOB, Line Of Business) de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para entregar mensajes en el cuadro de mensajes.  
  
 Microsoft Silverlight es una plataforma para la creación de sofisticadas aplicaciones web interoperables que permiten a los desarrolladores crear sitios Web con uso intensivo de contenidos multimedia (como la transmisión de vídeo por secuencias). A partir de la versión 2, Silverlight incorpora [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] como tecnología de comunicaciones para conectar las aplicaciones Silverlight con los extremos de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] .  
  
 El servidor de aplicaciones [!INCLUDE[dublin](../../../includes/dublin-md.md)] se ha diseñado específicamente para implementar y administrar aplicaciones que utilizan [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] para las comunicaciones. [!INCLUDE[dublin2](../../../includes/dublin2-md.md)] incluye sofisticadas opciones de configuración y herramientas diseñadas específicamente para las aplicaciones habilitadas para [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel>  
 [Conceptos básicos de Windows Communication Foundation](../../../docs/framework/wcf/fundamental-concepts.md)  
 [Arquitectura de Windows Communication Foundation](../../../docs/framework/wcf/architecture.md)  
 [Instrucciones y procedimientos recomendados](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
 [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Guía de la documentación](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [Programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Ejemplos de Windows Communication Foundation](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)
