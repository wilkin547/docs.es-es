---
title: Conceptos básicos de Windows Communication Foundation
description: Obtenga información sobre los aspectos básicos de la arquitectura de Windows Communication Foundation (WCF) con esta explicación de alto nivel.
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], concepts
- concepts [WCF]
- fundamentals [WCF]
- Windows Communication Foundation [WCF], concepts
ms.assetid: 3e7e0afd-7913-499d-bafb-eac7caacbc7a
ms.openlocfilehash: 93e75942487a1a81a8b0e8ecd8d9d666610152dc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244685"
---
# <a name="fundamental-windows-communication-foundation-concepts"></a>Conceptos básicos de Windows Communication Foundation

En este documento se proporciona una vista de alto nivel de la arquitectura de Windows Communication Foundation (WCF). Pretende explicar los conceptos clave y cómo encajan entre ellos. Para ver un tutorial sobre cómo crear la versión más sencilla de un servicio y cliente WCF, consulte [Introducción tutorial](getting-started-tutorial.md). Para obtener información sobre la programación de WCF, vea [programación básica de WCF](basic-wcf-programming.md).

## <a name="wcf-fundamentals"></a>Fundamentos de WCF

WCF es un entorno de tiempo de ejecución y un conjunto de API para crear sistemas que envían mensajes entre servicios y clientes. La misma infraestructura y API se utilizan para crear aplicaciones que se comuniquen con otras aplicaciones en el mismo sistema del equipo o en un sistema que resida en otra compañía y a la que se obtenga acceso a través de Internet.

### <a name="messaging-and-endpoints"></a>Mensajería y puntos de conexión

WCF se basa en la noción de comunicación basada en mensajes y cualquier cosa que se pueda modelar como un mensaje (por ejemplo, una solicitud HTTP o un mensaje de Message Queuing (también conocido como MSMQ)) se puede representar de manera uniforme en el modelo de programación. Esto habilita una API unificada en todos los mecanismos de transporte diferentes.

El modelo distingue entre _clientes_, que son aplicaciones que inician la comunicación y _servicios_, que son aplicaciones que esperan a que los clientes se comuniquen con ellos y respondan a esa comunicación. Una única aplicación puede actuar como cliente y como servicio. Para obtener ejemplos, vea [servicios dúplex](./feature-details/duplex-services.md) y [redes punto a punto](./feature-details/peer-to-peer-networking.md).

Los mensajes se envían entre puntos de conexión. Los _extremos_ son los lugares donde los mensajes se envían o reciben (o ambos), y definen toda la información requerida para el intercambio de mensajes. Un servicio expone uno o más puntos de conexión de la aplicación (y a cero o más puntos de conexión de la infraestructura), y el cliente genera un punto de conexión que es compatible con uno de los puntos de conexión del servicio.

Un _punto de conexión_ describe de una manera basada en el estándar en la que se deben enviar los mensajes, cómo deben enviarse y el aspecto de los mensajes. Un servicio puede exponer esta información como metadatos que los clientes pueden procesar para generar los clientes de WCF y las _pilas_de comunicación adecuados.

### <a name="communication-protocols"></a>Protocolos de comunicaciones

Un elemento obligatorio de la pila de comunicación es el _Protocolo de transporte_. Los mensajes se pueden enviar a través de intranets e Internet utilizando transportes comunes, como HTTP y TCP. Otros transportes incluidos admiten la comunicación con aplicaciones Message Queuing (MSMQ) y nodos en una malla de redes del mismo nivel. Se pueden agregar más mecanismos de transporte mediante los puntos de extensión integrados de WCF.

Otro elemento necesario en la pila de comunicación es la codificación que especifica cómo se da formato a cualquier mensaje determinado. WCF proporciona las codificaciones siguientes:

- Codificación de texto, una codificación interoperable.

- Codificación Mecanismo de optimización de transmisión de mensajes (MTOM), que es una manera interoperable de enviar eficazmente datos binarios no estructurados a y desde un servicio.

- Codificación binaria para una transferencia eficaz.

Se pueden agregar más mecanismos de codificación (por ejemplo, una codificación de compresión) mediante los puntos de extensión integrados de WCF.

### <a name="message-patterns"></a>Patrones de mensajes

WCF admite varios patrones de mensajería, como la comunicación de solicitud-respuesta, unidireccionales y dúplex. Los transportes diferentes admiten patrones de mensajería diferentes y, por consiguiente, afectan a los tipos de interacciones que admiten. Las API y el tiempo de ejecución de WCF también le ayudan a enviar mensajes de manera segura y confiable.

## <a name="wcf-terms"></a>Términos de WCF

Otros conceptos y términos que se usan en la documentación de WCF son los siguientes:

**Mensaje**  
 Unidad autónoma de datos que puede constar de varias partes, incluyendo un cuerpo y encabezados.

**Servicio**  
 Construcción que expone uno o más extremos, y en la que cada extremo expone una o más operaciones de servicio.

**Punto de conexión**  
 Construcción en la que se envían o reciben mensajes (o ambos). Comprende una ubicación (una dirección) que define dónde se pueden enviar los mensajes, una especificación del mecanismo de comunicación (un enlace) que describe cómo se deben enviar los mensajes y una definición de un conjunto de mensajes que se pueden enviar o recibir (o ambos) en esa ubicación (un contrato de servicio) que describe qué mensaje se puede enviar.

Un servicio de WCF se expone al mundo como una colección de extremos.

**Extremo de la aplicación**  
 Un extremo expuesto por la aplicación y que corresponde a un contrato de servicios implementado por la aplicación.

**Punto de conexión de infraestructura**  
 Un punto de conexión que expone la infraestructura para facilitar la funcionalidad necesaria o proporcionada por el servicio que no se relaciona con un contrato de servicios. Por ejemplo, un servicio podría tener un extremo de la infraestructura que proporciona información de metadatos.

**Dirección**  
 Especifica la ubicación donde se reciben los mensajes. Se especifica como un identificador uniforme de recursos (URI). La parte del esquema URI nombra el mecanismo de transporte que se ha de utilizar para alcanzar la dirección, por ejemplo HTTP y TCP. La parte jerárquica del URI contiene una ubicación única cuyo formato depende del mecanismo de transporte.

La dirección del extremo le permite crear direcciones únicas de extremos para cada extremo de un servicio o, bajo ciertas condiciones, compartir una dirección en los extremos. El siguiente ejemplo muestra una dirección que utiliza el protocolo HTTPS con un puerto no predeterminado:

```http
HTTPS://cohowinery:8005/ServiceModelSamples/CalculatorService
```

**Enlace**  
 Define cómo se comunica un punto de conexión con el mundo. Consta de un conjunto de componentes llamados elementos de enlace que se "apilan" uno sobre el otro para crear la infraestructura de comunicaciones. Como mínimo, un enlace define el transporte (como HTTP o TCP) y la codificación utilizada (por ejemplo, de texto o binaria). Un enlace puede contener elementos de enlace que especifican detalles, por ejemplo los mecanismos de seguridad utilizados para proteger los mensajes o el patrón de mensaje utilizado por un extremo. Para obtener más información, vea [configuración de servicios](configuring-services.md).

**Elemento de enlace**  
 Representa una parte determinada del enlace, por ejemplo un transporte, una codificación, una implementación de un protocolo del nivel de infraestructura (como WS-ReliableMessaging), o cualquier otro componente de la pila de comunicaciones.

**Determinados**  
 Componente que controla varios aspectos del tiempo de ejecución de un servicio, un punto de conexión, una operación determinada o un cliente. Los comportamientos están agrupados en función del ámbito: los comportamientos comunes afectan globalmente a todos los puntos de conexión, los comportamientos de servicios sólo afectan a los aspectos relacionados con servicios, los comportamientos de puntos de conexión sólo afectan a las propiedades relacionadas con los puntos de conexión y los comportamientos de operaciones afectan a las operaciones determinadas. Por ejemplo, un comportamiento del servicio está limitando que especifica cómo un servicio reacciona cuando un exceso de mensajes amenaza agobiar sus funciones del control. Un comportamiento de extremos, por otro lado, solo controla los aspectos relacionados con los extremos, como, por ejemplo, cómo y dónde encontrar una credencial de seguridad.

**Enlaces proporcionados por el sistema**  
 WCF incluye varios enlaces proporcionados por el sistema. Éstas son colecciones de elementos de enlace optimizados para escenarios concretos. Por ejemplo, <xref:System.ServiceModel.WSHttpBinding> está diseñado para la interoperabilidad con servicios que implementan varias \* Especificaciones de WS. Estos enlaces predefinidos ahorran tiempo al presentar sólo las opciones que se pueden aplicar correctamente al escenario en cuestión. Si un enlace predefinido no cumple sus requisitos, puede crear su propio enlace personalizado.

**Configuración frente a codificación**  
 El control de una aplicación puede realizarse mediante codificación, configuración o a mediante una combinación de ambas. La configuración tiene la ventaja de que permite a alguien que no sea el programador (por ejemplo, un administrador de redes) establecer parámetros de servicio y de cliente después de que el código se haya escrito y sin necesidad de recompilar. La configuración no sólo permite establecer valores como las direcciones de los extremos, sino que también proporciona un control adicional al permitir la agregación de extremos, enlaces y comportamientos. La codificación permite al desarrollador retener un control estricto sobre todos los componentes del servicio o cliente, y cualquier ajuste realizado a través de la configuración se puede inspeccionar y, si fuese necesario, podría invalidarse mediante el código.

**Operación de servicio**  
 Procedimiento definido en el código de un servicio que implementa la funcionalidad de una operación. Esta operación se expone a los clientes como métodos en un cliente de WCF. El método puede devolver un valor y tomar un número opcional de argumentos, o no tomar ningún argumento y no devolver ninguna respuesta. Por ejemplo, una operación que funciona como un simple "Hola" se puede utilizar para notificar acerca de la presencia de un cliente y para comenzar una serie de operaciones.

**Contrato de servicio**  
 Une varias operaciones relacionadas en una unidad funcional única. El contrato puede definir ajustes del nivel de servicio, como el espacio de nombres del servicio, un contrato de devolución de llamadas correspondiente y otros ajustes de este tipo. En la mayoría de los casos, el contrato se define mediante la creación de una interfaz en el lenguaje de programación que elija y la aplicación del atributo <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz. El código de servicio real se obtiene al implementar la interfaz.

**Contrato de la operación**  
 Un contrato de operación define los parámetros y el tipo de valor devuelto de una operación. Al crear una interfaz que define el contrato de servicio, se significa un contrato de operación mediante la aplicación del atributo <xref:System.ServiceModel.OperationContractAttribute> a cada definición de método que forma parte del contrato. Las operaciones se pueden modelar para que acepten un único mensaje y devuelvan también un único mensaje, o para que acepten un conjunto de tipos y devuelvan un tipo. En el último caso, el sistema determinará el formato de los mensajes que han de intercambiarse para esa operación.

**Contrato de mensaje**  
 Describe el formato de un mensaje. Por ejemplo, declara si los elementos del mensaje deberían ir en encabezados frente al cuerpo, qué nivel de seguridad debería aplicarse a qué elementos del mensaje, etc.

**Contrato de error**  
 Puede estar asociado a una operación de servicio para denotar errores que se pueden devolver al autor de la llamada. Una operación puede tener cero o más errores asociados a ella. Estos errores son errores de SOAP que se modelan como excepciones en el modelo de programación.

**Contrato de datos**  
 Las descripciones en los metadatos de los tipos de datos que usa un servicio. Esto permite a otros interoperar con el servicio. Los tipos de datos se pueden usar en cualquier parte de un mensaje; por ejemplo, como parámetros o tipos de valores devueltos. Si el servicio sólo utiliza tipos simples, no hay necesidad de utilizar explícitamente contratos de datos.

**Hospedar aplicaciones de WPF**  
 Un servicio debe hospedarse en algún proceso. Un _host_ es una aplicación que controla la duración del servicio. Los servicios pueden ser autohospedados o estar administrados por un proceso de hospedaje existente.

**Servicio autohospedado**  
 Es aquel que se ejecuta dentro de una aplicación de proceso que creó el desarrollador. El desarrollador controla su duración, establece las propiedades del servicio, abre el servicio (que lo establece en un modo de escucha) y cierra el servicio.

**Proceso de hospedaje**  
 Aplicación diseñada para hospedar servicios. Entre ellos se incluyen Internet Information Services (IIS), Windows Activation Services (WAS) y Windows Services. En estos escenarios hospedados, el host controla la duración del servicio. Por ejemplo, mediante IIS puede configurar un directorio virtual que contenga el ensamblado del servicio y el archivo de configuración. Cuando se recibe un mensaje, IIS inicia el servicio y controla su duración.

**Instancing**  
 Un servicio tiene un modelo de creación de instancias. Hay tres modelos de creación de instancias: "único" en el que un objeto CLR único repara todos los clientes; "por llamada", en el que un nuevo objeto CLR se crea para administrar cada llamada de cliente; y "por sesión", en el que se crea un conjunto de objetos CLR, uno para cada sesión individual. Para elegir un modelo de creación de instancias se han de tener en cuenta los requisitos de aplicación y el patrón de uso esperado del servicio.

**Aplicación cliente**  
 Programa que intercambia mensajes con uno o varios puntos de conexión. La aplicación cliente comienza creando de una instancia de un cliente de WCF y llamando a los métodos del cliente de WCF. Es importante tener en cuenta que una única aplicación pueda ser cliente y servicio.

**Canal**  
 Implementación concreta de un elemento de enlace. El enlace representa la configuración, y el canal es la implementación asociada a esa configuración. Por consiguiente, hay un canal asociado a cada elemento de enlace. Los canales se apilan uno sobre otro para crear la implementación concreta del enlace: la pila de canales.

**cliente de WCF**  
 Una construcción de aplicación cliente que expone las operaciones de servicio como métodos (en el lenguaje de programación .NET Framework que elija, como Visual Basic o Visual C#). Cualquier aplicación puede hospedar a un cliente de WCF, incluso una aplicación que hospede un servicio. Por tanto, es posible crear un servicio que incluya clientes de WCF de otros servicios.

Un cliente de WCF se puede generar automáticamente mediante la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) y apuntarlo a un servicio en ejecución que publica los metadatos.

**Metadata**  
 En un servicio, describen las características de este que tiene que comprender una entidad externa para comunicarse con él. La [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) puede consumir los metadatos para generar un cliente de WCF y la configuración adjunta que puede usar una aplicación cliente para interactuar con el servicio.

Los metadatos expuestos por el servicio incluyen documentos de esquema XML, que definen el contrato de datos del servicio, y documentos WSDL, que describen los métodos del servicio.

Cuando se habilita, WCFG genera automáticamente los metadatos del servicio mediante la inspección del servicio y sus puntos de conexión. Para publicar los metadatos desde un servicio, debe permitir explícitamente al comportamiento de los metadatos.

**Seguridad**  
 En WCF, incluye confidencialidad (cifrado de mensajes para evitar la interceptación), integridad (los medios para la detección de alteración del mensaje), autenticación (los medios para la validación de servidores y clientes) y autorización (el control de acceso a los recursos). Estas funciones se proporcionan mediante el uso de mecanismos de seguridad existentes, como TLS sobre HTTP (también conocido como HTTPS), o la implementación de una o varias especificaciones de WS- \* Security.

**Modo de seguridad de transporte**  
 Especifica que los mecanismos del nivel de transporte (como HTTPS) proporcionan confidencialidad, integridad y autenticación. El uso de un transporte como HTTPS en este modo tiene la ventaja de ofrecer un mejor rendimiento. También se entiende bien debido a su predominio en Internet. La desventaja es que este tipo de seguridad se aplica por separado en cada salto en la ruta de comunicación, provocando que la comunicación sea susceptible a un ataque tipo “man in the middle”.

**Modo de seguridad de mensajes**  
 Especifica que la seguridad se proporciona mediante la implementación de una o varias especificaciones de seguridad, como la especificación denominada [seguridad de servicios web: seguridad del mensaje SOAP](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf). Cada mensaje contiene los mecanismos necesarios para proporcionar la seguridad durante su tránsito y para permitir que los receptores detecten la manipulación y el descifrado de mensajes. En este sentido, la seguridad se encapsula dentro de cada mensaje, con lo que se proporciona una seguridad de extremo a extremo en varios saltos. Dado que la información de seguridad se convierte en parte del mensaje, también es posible incluir varios tipos de credenciales con el mensaje (a las que se hace referencia como _notificaciones_). Este enfoque también tiene la ventaja de permitir al mensaje viajar de manera segura sobre cualquier transporte, incluyendo varios transportes entre su origen y destino. La desventaja de este enfoque es la complejidad de los mecanismos de cifrado empleados, que afectan al rendimiento.

**Transporte con el modo de seguridad de credenciales de mensaje**  
 Especifica el uso del nivel de transporte para proporcionar la confidencialidad, autenticación e integridad de los mensajes, mientras que cada uno de los mensajes puede contener varias credenciales (notificaciones) requeridas por parte de los receptores del mensaje.

**WS\***  
 Modo abreviado para el creciente conjunto de especificaciones de servicios Web (WS) que se implementan en WCF, tales como WS-Security, WS-ReliableMessaging, etc.

## <a name="see-also"></a>Vea también

- [¿Qué es Windows Communication Foundation?](whats-wcf.md)
- [Arquitectura de Windows Communication Foundation](architecture.md)
