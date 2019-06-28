---
title: ¿Qué es Windows Communication Foundation?
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation [WCF], technology overview
- technology overview [WCF]
- WCF [WCF], technology overview
ms.assetid: 40e1009d-ef15-450b-9848-62eabe5e5738
ms.openlocfilehash: a7db79185d4445c68adda214d10be6d31f6ed9e0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425113"
---
# <a name="what-is-windows-communication-foundation"></a>¿Qué es Windows Communication Foundation?
Windows Communication Foundation (WCF) es un marco para crear aplicaciones orientadas a servicios. Con WCF, puede enviar datos como mensajes asincrónicos de un extremo de servicio a otro. Un extremo de servicio puede formar parte de un servicio disponible continuamente hospedado por IIS, o puede ser un servicio hospedado en una aplicación. Un extremo puede ser un cliente de un servicio que solicita datos de un extremo de servicio. Los mensajes pueden ser tan simples como un carácter o una palabra que se envía como XML, o tan complejos como una secuencia de datos binarios. A continuación se indican unos cuantos escenarios de ejemplo:

- Un servicio seguro para procesar transacciones comerciales.

- Un servicio que proporciona datos actualizados a otras personas, como un informe sobre tráfico u otro servicio de supervisión.

- Un servicio de chat que permite a dos personas comunicarse o intercambiar datos en tiempo real.

- Una aplicación de panel que sondea los datos de uno o varios servicios y los muestra en una presentación lógica.

- Exponer un flujo de trabajo implementado utilizando Windows Workflow Foundation como un servicio WCF.

- Una aplicación de Silverlight para sondear un servicio en busca de las fuentes de datos más recientes.

Si crear tales aplicaciones era posible antes de la existencia de WCF, WCF facilita el desarrollo de los puntos de conexión que nunca. En resumen, WCF está diseñado para ofrecer un enfoque manejable a la creación de servicios Web y clientes de servicios Web.

## <a name="features-of-wcf"></a>Características de WCF

WCF incluye el siguiente conjunto de características. Para obtener más información, consulte [detalles de características de WCF](../../../docs/framework/wcf/feature-details/index.md).

- **Orientación a servicios**

     Una consecuencia del uso de los estándares de WS es que WCF le permite crear *orientadas a servicios* aplicaciones. SOA, la arquitectura orientada a servicios es el uso de servicios web para enviar y recibir datos. Los servicios tienen la ventaja general de estar débilmente acoplados entre una aplicación y otra en lugar de incluidos en el código. Una relación de acoplamiento débil implica que cualquier cliente creado en cualquier plataforma puede conectar con cualquier servicio siempre y cuando se cumplan los contratos esenciales.

- **Interoperabilidad**

     WCF implementa los estándares del sector modernos para la interoperabilidad del servicio Web. Para obtener más información acerca de los estándares admitidos, consulte [interoperabilidad e integración](../../../docs/framework/wcf/feature-details/interoperability-and-integration.md).

- **Varios patrones de mensajes**

     Los mensajes se intercambian mediante uno de los distintos patrones. El más común es el de solicitud/respuesta, en que un extremo solicita datos de otro extremo. y el otro extremo responde. Existen otros patrones, como un mensaje unidireccional, en que un único extremo envía un mensaje sin esperar ninguna respuesta. Un patrón más complejo es el patrón de intercambio dúplex donde dos extremos establecen una conexión y envían datos hacia delante y hacia atrás, similar a un programa de mensajería instantánea. Para obtener más información sobre cómo implementar el intercambio de mensajes diferentes patrones de uso de WCF vea [contratos](../../../docs/framework/wcf/feature-details/contracts.md).

- **Metadatos de servicios**

     WCF admite la publicación de servicio de metadatos utilizando formatos especificados en los estándares del sector como WSDL, esquemas XML y WS-Policy. Estos metadatos se pueden usar para generar automáticamente y configurar a clientes para tener acceso a los servicios WCF. Los metadatos se pueden publicar sobre HTTP y HTTPS, o utilizando el estándar Intercambio de metadatos de servicios web. Para obtener más información, consulte [metadatos](../../../docs/framework/wcf/feature-details/metadata.md).

- **Contratos de datos**

     Dado que WCF se compila con .NET Framework, también incluye métodos con código sencillo proporcionar los contratos que desea aplicar. Uno de los tipos de contrato universales es el contrato de datos. Básicamente, mientras se escribe el código del servicio usando Visual C# o Visual Basic, la forma más sencilla de controlar los datos consiste en crear clases que representan una entidad de datos con propiedades que pertenecen a la misma. WCF incluye un completo sistema para trabajar con datos de esta manera fácil. Cuando se han creado las clases que representan los datos, el servicio genera automáticamente los metadatos que permiten a los clientes ajustarse a los tipos de datos que se han diseñado. Para obtener más información, consulte [Using Data Contracts](../../../docs/framework/wcf/feature-details/using-data-contracts.md)

- **Seguridad**

     Es posible cifrar los mensajes para proteger la privacidad, así como obligar a los usuarios a que se autentiquen antes de permitirles recibir mensajes. La seguridad puede implementarse utilizando estándares conocidos como SSL o WS-SecureConversation. Para más información, consulte [Seguridad](../../../docs/framework/wcf/feature-details/security.md).

- **Varios transportes y codificaciones**

     Los mensajes pueden enviarse con cualquiera de los protocolos y codificaciones integrados. Más frecuente de protocolo y codificación consiste en enviar texto con codificación de mensajes SOAP mediante el protocolo de transferencia de hipertexto (HTTP) para su uso en World Wide Web. Como alternativa, WCF le permite enviar mensajes a través de TCP, canalizaciones con nombre o MSMQ. Estos mensajes pueden codificarse como texto o utilizando un formato binario optimizado.  Los datos binarios pueden enviarse de manera eficaz utilizando el estándar MTOM. Si ninguno de los transportes o codificaciones proporcionados satisface sus necesidades, puede crear uno personalizado. Para obtener más información acerca de los transportes y codificaciones admitidos por WCF vea [transportes](../../../docs/framework/wcf/feature-details/transports.md).

- **Mensajes confiables y en cola**

     WCF admite intercambio de mensajes confiable utilizando sesiones confiables implementadas sobre WS-Reliable Messaging y utilizando MSMQ. Para obtener más información sobre la compatibilidad con mensajería confiable y en cola en WCF, vea [colas y sesiones confiables](../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md).

- **Mensajes duraderos**

     Un mensaje duradero es aquel que nunca se pierde debido a una interrupción de la comunicación. Los mensajes que forman parte de un patrón de mensajes duraderos siempre se guardan en una base de datos. Si se produce una interrupción, la base de datos le permite reanudar el intercambio de mensajes cuando se restablezca la conexión. También puede crear un mensaje duradero utilizando Windows Workflow Foundation (WF). Para obtener más información, consulte [servicios de flujo de trabajo](../../../docs/framework/wcf/feature-details/workflow-services.md).

- **Transacciones**

     WCF también admite transacciones mediante uno de los tres modelos de transacción: WS-AtomicTransactions, las API en el <xref:System.Transactions> espacio de nombres y el Coordinador de transacciones distribuidas de Microsoft. Para obtener más información acerca de la transacción de soporte técnico en WCF vea [transacciones](../../../docs/framework/wcf/feature-details/transactions-in-wcf.md).

- **Compatibilidad con AJAX y REST**

     REST es un ejemplo de una tecnología de la Web 2.0 en evolución. WCF se puede configurar para procesar datos XML "sin formato" que no se ajustan en un sobre SOAP. WCF también puede ampliarse para admitir formatos XML concretos, como ATOM (un estándar popular de RSS) e incluso formatos no XML, como JavaScript Object Notation (JSON).

- **Extensibilidad**

     La arquitectura de WCF tiene un número de puntos de extensibilidad. Si se necesita una función adicional, existen una serie de puntos de entrada que le permiten personalizar el comportamiento de un servicio. Para obtener más información acerca de extensibilidad disponibles vea puntos [Extending WCF](../../../docs/framework/wcf/extending/index.md).

## <a name="wcf-integration-with-other-microsoft-technologies"></a>Integración de WCF con otras tecnologías de Microsoft

WCF es una plataforma flexible. Debido a esta flexibilidad extrema, WCF también se usa en otros productos de Microsoft. Al comprender los conceptos básicos de WCF, tiene una ventaja inmediata si también utiliza cualquiera de estos productos.

La primera tecnología en adaptarse con WCF fue Windows Workflow Foundation (WF). Los flujos de trabajo simplifican el desarrollo de aplicaciones encapsulando los pasos del flujo de trabajo como "actividades". En la primera versión de Windows Workflow Foundation, un desarrollador tenía que crear un host del flujo de trabajo. La próxima versión de Windows Workflow Foundation se integra con WCF. Que permite que cualquier flujo de trabajo fácilmente hospedarse en un servicio WCF. Puede hacerlo si elige automáticamente el tipo de proyecto WF/WCF en Visual Studio 2012 o posterior.

Microsoft BizTalk Server R2 también utiliza WCF como tecnología de comunicaciones. BizTalk está diseñado para recibir y transformar datos de un formato normalizado en otro. Los mensajes deben entregarse en su cuadro de mensajes central, donde es posible transformar el mensaje utilizando una asignación estricta o mediante una de las características de BizTalk, como su motor de flujo de trabajo. BizTalk ahora puede usar el adaptador de WCF línea de negocio (LOB) para entregar mensajes en el cuadro de mensaje.

Microsoft Silverlight es una plataforma para la creación de sofisticadas aplicaciones web interoperables que permiten a los desarrolladores crear sitios Web con uso intensivo de contenidos multimedia (como la transmisión de vídeo por secuencias). A partir de la versión 2, Silverlight incorpora WCF como tecnología de comunicaciones para conectar las aplicaciones de Silverlight a puntos de conexión WCF.

Las características de hospedaje de servidor de aplicaciones de Windows Server AppFabric diseñadas específicamente para implementar y administrar las aplicaciones que usan WCF para la comunicación. Las características de hospedaje incluyen opciones de configuración y herramientas enriquecidas diseñadas específicamente para aplicaciones habilitadas para WCF.

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel>
- [Conceptos básicos de Windows Communication Foundation](../../../docs/framework/wcf/fundamental-concepts.md)
- [Arquitectura de Windows Communication Foundation](../../../docs/framework/wcf/architecture.md)
- [Instrucciones y procedimientos recomendados](../../../docs/framework/wcf/guidelines-and-best-practices.md)
- [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md)
- [Guía de la documentación](../../../docs/framework/wcf/guide-to-the-documentation.md)
- [Programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md)
- [Ejemplos de Windows Communication Foundation](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751514%28v=vs.90%29)
