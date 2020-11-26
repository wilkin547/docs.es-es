---
title: Diseño e implementación de servicios
ms.date: 03/30/2017
helpviewer_keywords:
- defining service contracts [WCF]
ms.assetid: 036fae20-7c55-4002-b71d-ac4466e167a3
ms.openlocfilehash: ea32855a3a512b8e96b8d6d72f101523b5d16107
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248778"
---
# <a name="designing-and-implementing-services"></a>Diseño e implementación de servicios

En esta sección se muestra cómo definir e implementar contratos WCF. Un contrato de servicio especifica lo que un punto de conexión comunica al mundo exterior. En un nivel más concreto, es una instrucción sobre un conjunto de mensajes concretos organizada en patrones de intercambio de mensajes básicos (MEP), como solicitud/respuesta, unidireccional y dúplex. Si un contrato de servicio es un conjunto relacionado de forma lógica de intercambios de mensajes, una operación de servicio es un intercambio único de mensajes. Por ejemplo, una operación `Hello` debe aceptar obviamente un mensaje (de manera que el autor de la llamada pueda anunciar el saludo) y puede o no devolver un mensaje (dependiendo de la cortesía de la operación).  
  
 Para obtener más información sobre los contratos y otros conceptos principales de Windows Communication Foundation (WCF), vea [conceptos básicos de Windows Communication Foundation](fundamental-concepts.md). Este tema se centra en describir los contratos de servicio. Para obtener más información sobre cómo crear clientes que usen contratos de servicio para conectarse a los servicios, consulte [información general del cliente de WCF](wcf-client-overview.md).  
  
## <a name="overview"></a>Información general  

 En este tema se proporciona una orientación conceptual de alto nivel para diseñar e implementar servicios WCF. Los subtemas proporcionan más información detallada sobre las características de diseño e implementación. Antes de diseñar e implementar la aplicación WCF, se recomienda que:  
  
- Entender lo que es un contrato de servicio, cómo funciona, y cómo crear uno.  
  
- Comprender que los contratos especifican requisitos mínimos que la configuración en tiempo de ejecución o el entorno de hospedaje pueden no admitir.  
  
## <a name="service-contracts"></a>Contratos de servicio  

 Un contrato de servicio especifica lo siguiente:  
  
- Las operaciones que el contrato expone.  
  
- La firma de las operaciones en términos de mensajes intercambiados.  
  
- Los tipos de datos de estos mensajes.  
  
- La ubicación de las operaciones.  
  
- Los protocolos concretos y formatos de serialización que se utilizan para admitir la comunicación correcta con el servicio.  
  
 Por ejemplo, un contrato de orden de compra podría tener una operación `CreateOrder` que acepte una entrada de tipos de información de orden y devuelva información de error o completada, además de un identificador de orden. También podría tener una operación `GetOrderStatus` que acepte un identificador de orden y devuelva información de estado de la orden. Un contrato de servicio de este tipo especificaría lo siguiente:  
  
1. Que el contrato de la orden compra consistiese en las operaciones `CreateOrder` y `GetOrderStatus`.  
  
2. Que las operaciones han especificado mensajes de entrada y de salida.  
  
3. Los datos que estos mensajes pueden llevar.  
  
4. Instrucciones de categorías sobre la infraestructura de la comunicación necesaria para procesar correctamente los mensajes. Por ejemplo, estos detalles incluyen qué formularios de seguridad son necesarios para establecer una comunicación correcta.  
  
 Para transmitir este tipo de información a otras aplicaciones en muchas plataformas (incluidas plataformas que no sean de Microsoft), los contratos de servicio XML se expresan públicamente en formatos XML estándar, como el [lenguaje de descripción de servicios web](https://www.w3.org/TR/2001/NOTE-wsdl-20010315) (WSDL) y el [esquema XML](https://www.w3.org/XML/Schema) (XSD), entre otros. Los desarrolladores para muchas plataformas pueden utilizar esta información de contrato público para crear aplicaciones que pueden comunicarse con el servicio, porque entienden el lenguaje de la especificación y porque esos lenguajes están diseñados para permitir la interoperación describiendo los formularios, formatos y protocolos públicos que el servicio admite. Para obtener más información sobre cómo WCF controla este tipo de información, vea [metadatos](./feature-details/metadata.md).  
  
 Los contratos se pueden expresar de muchas maneras, pero, aunque WSDL y XSD son lenguajes excelentes para describir servicios de una manera accesible, se trata de lenguajes difíciles de usar directamente y son simplemente descripciones de un servicio, no implementaciones de contratos de servicio. Por lo tanto, las aplicaciones WCF usan atributos, interfaces y clases administrados para definir la estructura de un servicio e implementarlo.  
  
 El contrato resultante definido en tipos administrados se puede *exportar* como metadatos (WSDL y XSD) cuando lo necesiten clientes u otros implementadores de servicio. El resultado es un modelo de programación sencillo que se puede describir (usando metadatos públicos) en cualquier aplicación cliente. Los detalles de los mensajes SOAP subyacentes, el transporte y la información relacionada con la seguridad, etc., pueden dejarse en WCF, que realiza automáticamente las conversiones necesarias para y desde el sistema de tipo de contrato de servicio al sistema de tipos XML.  
  
 Para obtener más información sobre el diseño de contratos, consulte [diseño de contratos de servicio](designing-service-contracts.md). Para obtener más información sobre la implementación de contratos, vea [implementación de contratos de servicio](implementing-service-contracts.md).  
  
### <a name="messages-up-front-and-center"></a>Mensajes arriba y al centro  

 Utilizar interfaces, clases y métodos administrados para modelar las operaciones de servicio es sencillo cuando está acostumbrado a firmas de método de estilo de llamada a procedimiento remoto (RPC), en las que pasar parámetros a un método y recibir valores de devolución es la forma normal de solicitar funcionalidad desde un objeto u otro tipo de código. Por ejemplo, los programadores que usan lenguajes administrados como Visual Basic y C++ COM pueden aplicar sus conocimientos del enfoque de estilo RPC (ya sea mediante objetos o interfaces) a la creación de contratos de servicio WCF sin experimentar los problemas inherentes a los sistemas de objetos distribuidos de estilo RPC. La orientación del servicio proporciona las ventajas de la programación acoplada y orientada a mensajes mientras mantiene la facilidad y familiaridad de la experiencia de programación de RPC.  
  
 Muchos programadores se sienten más cómodos con las interfaces de programación de aplicaciones orientadas a mensajes, como las colas de mensajes como Microsoft MSMQ, los espacios de nombres <xref:System.Messaging> en .NET Framework o el envío de XML no estructurado en solicitudes HTTP, por nombrar algunos. Para obtener más información sobre la programación en el nivel de mensaje, vea [uso de contratos de mensaje](./feature-details/using-message-contracts.md), programación de Channel-Level de [servicio](./extending/service-channel-level-programming.md)e [interoperabilidad con aplicaciones POX](./feature-details/interoperability-with-pox-applications.md).  
  
### <a name="understanding-the-hierarchy-of-requirements"></a>Introducción a la jerarquía de los requisitos  

 Un contrato de servicio agrupa operaciones; especifica el patrón de intercambio de mensajes, tipos de mensaje y tipos de datos que llevan esos mensajes e indica categorías de comportamiento de tiempo de ejecución que una implementación debe tener para admitir el contrato (por ejemplo, puede requerir que los mensajes se cifren y firmen). El contrato de servicio en sí mismo no especifica precisamente cómo se cumplen estos requisitos, solo que son obligatorios. El tipo de cifrado o la manera en la que se firma un mensaje depende de la implementación y configuración de un servicio conforme.  
  
 Observe la manera en que el contrato requiere algunas cosas de la implementación del contrato de servicio y la configuración del tiempo de ejecución para agregar comportamiento. El conjunto de requisitos que se deben cumplir para exponer un servicio para usar compilaciones en el conjunto anterior de requisitos. Si un contrato realiza requisitos de la implementación, una implementación puede requerir todavía más de la configuración y enlaces que permiten al servicio ejecutarse. Finalmente, la aplicación host también debe admitir cualquier requisito que la configuración de servicio y los enlaces agreguen.  
  
 Este proceso de requisitos aditivos es importante tener en cuenta al diseñar, implementar, configurar y hospedar una aplicación de servicio de Windows Communication Foundation (WCF). Por ejemplo, el contrato puede especificar que necesita admitir una sesión. En ese caso, deberá configurar el enlace para admitir ese requisito contractual o la implementación del servicio no funcionará. O si su servicio requiere Autenticación integrada de Windows y se hospeda en Internet Information Services (IIS), la aplicación web en la que el servicio reside debe tener Autenticación integrada de Windows activada y la compatibilidad anónima desactivada. Para obtener más información sobre las características y el impacto de los distintos tipos de aplicación host de servicio, vea [servicios de hospedaje](hosting-services.md).  
  
## <a name="see-also"></a>Vea también

- [Diseño de contratos de servicios](designing-service-contracts.md)
- [Implementación de contratos de servicio](implementing-service-contracts.md)
