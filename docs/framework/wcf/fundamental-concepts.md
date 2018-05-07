---
title: Conceptos básicos de Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], concepts
- concepts [WCF]
- fundamentals [WCF]
- Windows Communication Foundation [WCF], concepts
ms.assetid: 3e7e0afd-7913-499d-bafb-eac7caacbc7a
ms.openlocfilehash: 44b36fc917ceb30141d7d2235b8bb364d3b998c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="fundamental-windows-communication-foundation-concepts"></a>Conceptos básicos de Windows Communication Foundation
Este documento proporciona una visión general de la arquitectura de Windows Communication Foundation (WCF). Pretende explicar los conceptos clave y cómo encajan entre ellos. Para obtener un tutorial sobre la creación de la versión más sencilla de un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] servicio y el cliente, vea [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md). Para obtener información sobre [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] de programación, vea [programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="wcf-fundamentals"></a>Fundamentos de WCF  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] es un tiempo de ejecución y un conjunto de API para la creación de sistemas que envíen mensajes entre servicios y clientes. La misma infraestructura y API se utilizan para crear aplicaciones que se comuniquen con otras aplicaciones en el mismo sistema del equipo o en un sistema que resida en otra compañía y a la que se obtenga acceso a través de Internet.  
  
### <a name="messaging-and-endpoints"></a>Mensajería y extremos  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se basa en la noción de comunicación basada en mensajes, y cualquier cosa que se pueda modelar como un mensaje (por ejemplo, una solicitud HTTP o un transporte de cola de mensajes (también conocido como MSMQ)) se puede representar de manera uniforme en el modelo de programación. Esto habilita una API unificada en todos los mecanismos de transporte diferentes.  
  
 El modelo distingue entre *clientes*, que son aplicaciones que inician la comunicación y *services*, que son aplicaciones que esperan a que los clientes para comunicarse con ellos y responder a la comunicación. Una única aplicación puede actuar como cliente y como servicio. Para obtener ejemplos, vea [servicios dúplex](../../../docs/framework/wcf/feature-details/duplex-services.md) y [redes Peer-to-Peer](../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
 Los mensajes se envían entre puntos de conexión. *Los puntos de conexión* son los lugares donde los mensajes se envían o reciben (o ambos), y definen toda la información necesaria para el intercambio de mensajes. Un servicio expone uno o más puntos de conexión de la aplicación (y a cero o más puntos de conexión de la infraestructura), y el cliente genera un punto de conexión que es compatible con uno de los puntos de conexión del servicio.  
  
 Un *extremo* describe de una manera basada en estándar dónde se deberían enviar los mensajes, cómo se deberían enviar y aspecto de los mensajes. Un servicio puede exponer esta información como metadatos que los clientes pueden procesar para generar adecuado [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] los clientes y la comunicación *pilas*.  
  
### <a name="communication-protocols"></a>Protocolos de comunicaciones  
 Un elemento necesario de la pila de comunicación del *protocolo de transporte*. Los mensajes se pueden enviar a través de intranets e Internet utilizando transportes comunes, como HTTP y TCP. Otros transportes incluidos admiten la comunicación con aplicaciones Message Queuing (MSMQ) y nodos en una malla de redes del mismo nivel. Se pueden agregar más mecanismos de transporte utilizando los puntos de la extensión integrados de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
 Otro elemento necesario en la pila de comunicación es la codificación que especifica cómo se da formato a cualquier mensaje determinado. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] proporciona las codificaciones siguientes:  
  
-   Codificación de texto, una codificación interoperable.  
  
-   Codificación Mecanismo de optimización de transmisión de mensajes (MTOM), que es una manera interoperable de enviar eficazmente datos binarios no estructurados a y desde un servicio.  
  
-   Codificación binaria para una transferencia eficaz.  
  
 Se pueden agregar más mecanismos de codificación (por ejemplo, una codificación de compresión) utilizando los puntos de extensión integrados de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
### <a name="message-patterns"></a>Patrones de mensajes  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] admite varios patrones de mensajería, incluida la comunicación de solicitud-respuesta unidireccional y dúplex. Los transportes diferentes admiten patrones de mensajería diferentes y, por consiguiente, afectan a los tipos de interacciones que admiten. El tiempo de ejecución y las API de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] también le ayudan a enviar mensajes de manera segura y fiable.  
  
## <a name="wcf-terms"></a>Términos de WCF  
 Entre otros conceptos y términos usados en la documentación de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se incluyen los siguientes.  
  
 message  
 Unidad autónoma de datos que puede constar de varias partes, incluyendo un cuerpo y encabezados.  
  
 servicio  
 Construcción que expone uno o más puntos de conexión, y en la que cada punto de conexión expone una o más operaciones de servicio.  
  
 punto de conexión  
 Construcción en la que se envían o reciben mensajes (o ambos). Está compuesto por una ubicación (una dirección) que define a dónde se pueden enviar mensajes, una especificación del mecanismo de comunicación (un enlace) que describe cómo se deberían enviar los mensajes y una definición de un conjunto de mensajes que se pueden enviar o recibir (o ambos) en esa ubicación (un contrato de servicio) que describe qué mensajes se pueden enviar.  
  
 Un servicio de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] se expone al mundo como una colección de extremos.  
  
 punto de conexión de la aplicación  
 Un punto de conexión expuesto por la aplicación y que corresponde a un contrato de servicios implementado por la aplicación.  
  
 extremo de infraestructura  
 Un extremo que expone la infraestructura para facilitar la funcionalidad necesaria o proporcionada por el servicio que no se relaciona con un contrato de servicios. Por ejemplo, un servicio podría tener un extremo de la infraestructura que proporciona información de metadatos.  
  
 address  
 Especifica la ubicación donde se reciben los mensajes. Se especifica como un identificador uniforme de recursos (URI). La parte del esquema URI nombra el mecanismo de transporte que se ha de utilizar para alcanzar la dirección, por ejemplo HTTP y TCP. La parte jerárquica del URI contiene una ubicación única cuyo formato depende del mecanismo de transporte.  
  
 La dirección del punto de conexión le permite crear direcciones únicas de puntos de conexión para cada punto de conexión de un servicio o, bajo ciertas condiciones, compartir una dirección en los puntos de conexión. El siguiente ejemplo muestra una dirección que utiliza el protocolo HTTPS con un puerto no predeterminado:  
  
```  
HTTPS://cohowinery:8005/ServiceModelSamples/CalculatorService  
```  
  
 enlace  
 Define cómo se comunica un extremo con el mundo. Consta de un conjunto de componentes llamados elementos de enlace que se "apilan" uno sobre el otro para crear la infraestructura de comunicaciones. Como mínimo, un enlace define el transporte (como HTTP o TCP) y la codificación utilizada (por ejemplo, de texto o binaria). Un enlace puede contener elementos de enlace que especifican detalles, por ejemplo los mecanismos de seguridad utilizados para proteger los mensajes o el patrón de mensaje utilizado por un punto de conexión. Para obtener más información, consulte [configurar Services](../../../docs/framework/wcf/configuring-services.md).  
  
 elemento de enlace  
 Representa una parte determinada del enlace, por ejemplo un transporte, una codificación, una implementación de un protocolo del nivel de infraestructura (como WS-ReliableMessaging), o cualquier otro componente de la pila de comunicaciones.  
  
 comportamientos  
 Componente que controla varios aspectos del tiempo de ejecución de un servicio, un punto de conexión, una operación determinada o un cliente. Los comportamientos están agrupados en función del ámbito: los comportamientos comunes afectan globalmente a todos los puntos de conexión, los comportamientos de servicios sólo afectan a los aspectos relacionados con servicios, los comportamientos de puntos de conexión sólo afectan a las propiedades relacionadas con los puntos de conexión y los comportamientos de operaciones afectan a las operaciones determinadas. Por ejemplo, un comportamiento del servicio está limitando que especifica cómo un servicio reacciona cuando un exceso de mensajes amenaza agobiar sus funciones del control. Un comportamiento de extremos, por otro lado, solo controla los aspectos relacionados con los extremos, como, por ejemplo, cómo y dónde encontrar una credencial de seguridad.  
  
 enlaces proporcionados por el sistema  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] incluye varios enlaces proporcionados por el sistema. Éstas son colecciones de elementos de enlace optimizados para escenarios concretos. Por ejemplo, el <xref:System.ServiceModel.WSHttpBinding> está diseñado para la interoperabilidad con servicios que implementan varias especificaciones WS - *. Estos enlaces predefinidos ahorran tiempo al presentar sólo las opciones que se pueden aplicar correctamente al escenario en cuestión. Si un enlace predefinido no cumple sus requisitos, puede crear su propio enlace personalizado.  
  
 configuración frente a codificación  
 El control de una aplicación puede realizarse mediante codificación, configuración o a mediante una combinación de ambas. La configuración tiene la ventaja de que permite a alguien que no sea el programador (por ejemplo, un administrador de redes) establecer parámetros de servicio y de cliente después de que el código se haya escrito y sin necesidad de recompilar. La configuración no sólo permite establecer valores como las direcciones de los extremos, sino que también proporciona un control adicional al permitir la agregación de extremos, enlaces y comportamientos. La codificación permite al desarrollador retener un control estricto sobre todos los componentes del servicio o cliente, y cualquier ajuste realizado a través de la configuración se puede inspeccionar y, si fuese necesario, podría invalidarse mediante el código.  
  
 operación de servicio  
 Procedimiento definido en el código de un servicio que implementa la funcionalidad de una operación. Esta operación se expone a los clientes como métodos en un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. El método puede devolver un valor y tomar un número opcional de argumentos, o no tomar ningún argumento y no devolver ninguna respuesta. Por ejemplo, una operación que funciona como un simple "Hola" se puede utilizar para notificar acerca de la presencia de un cliente y para comenzar una serie de operaciones.  
  
 contrato de servicio  
 Une varias operaciones relacionadas en una unidad funcional única. El contrato puede definir ajustes del nivel de servicio, como el espacio de nombres del servicio, un contrato de devolución de llamadas correspondiente y otros ajustes de este tipo. En la mayoría de los casos, el contrato se define mediante la creación de una interfaz en el lenguaje de programación que elija y la aplicación del atributo <xref:System.ServiceModel.ServiceContractAttribute> a la interfaz. El código de servicio real se obtiene al implementar la interfaz.  
  
 contrato de operación  
 Un contrato de operación define los parámetros y el tipo de valor devuelto de una operación. Al crear una interfaz que define el contrato de servicio, se significa un contrato de operación mediante la aplicación del atributo <xref:System.ServiceModel.OperationContractAttribute> a cada definición de método que forma parte del contrato. Las operaciones se pueden modelar para que acepten un único mensaje y devuelvan también un único mensaje, o para que acepten un conjunto de tipos y devuelvan un tipo. En el último caso, el sistema determinará el formato de los mensajes que han de intercambiarse para esa operación.  
  
 contrato de mensaje  
 Describe el formato de un mensaje. Por ejemplo, declara si los elementos del mensaje deberían ir en encabezados frente al cuerpo, qué nivel de seguridad debería aplicarse a qué elementos del mensaje, etc.  
  
 contrato de error  
 Puede estar asociado a una operación de servicio para denotar errores que se pueden devolver al autor de la llamada. Una operación puede tener cero o más errores asociados a ella. Estos errores son errores de SOAP que se modelan como excepciones en el modelo de programación.  
  
 contrato de datos  
 Las descripciones en los metadatos de los tipos de datos que usa un servicio. Esto permite a otros interoperar con el servicio. Los tipos de datos se pueden usar en cualquier parte de un mensaje; por ejemplo, como parámetros o tipos de valores devueltos. Si el servicio sólo utiliza tipos simples, no hay necesidad de utilizar explícitamente contratos de datos.  
  
 hospedaje  
 Un servicio debe hospedarse en algún proceso. A *host* es una aplicación que controla la duración del servicio. Los servicios pueden ser autohospedados o estar administrados por un proceso de hospedaje existente.  
  
 servicio independiente  
 Es aquel que se ejecuta dentro de una aplicación de proceso que creó el desarrollador. El desarrollador controla su duración, establece las propiedades del servicio, abre el servicio (que lo establece en un modo de escucha) y cierra el servicio.  
  
 proceso de alojamiento  
 Aplicación diseñada para hospedar servicios. Entre ellos se incluyen Internet Information Services (IIS), Windows Activation Services (WAS) y Windows Services. En estos escenarios hospedados, el host controla la duración del servicio. Por ejemplo, mediante IIS puede configurar un directorio virtual que contenga el ensamblado del servicio y el archivo de configuración. Cuando se recibe un mensaje, IIS inicia el servicio y controla su duración.  
  
 crear instancias  
 Un servicio tiene un modelo de creación de instancias. Hay tres modelos de creación de instancias: "único" en el que un objeto CLR único repara todos los clientes; "por llamada", en el que un nuevo objeto CLR se crea para administrar cada llamada de cliente; y "por sesión", en el que se crea un conjunto de objetos CLR, uno para cada sesión individual. Para elegir un modelo de creación de instancias se han de tener en cuenta los requisitos de aplicación y el patrón de uso esperado del servicio.  
  
 aplicación cliente  
 Programa que intercambia mensajes con uno o varios puntos de conexión. La aplicación de cliente comienza creando una instancia de un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y llamando métodos del cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]. Es importante tener en cuenta que una única aplicación pueda ser cliente y servicio.  
  
 canal  
 Implementación concreta de un elemento de enlace. El enlace representa la configuración, y el canal es la implementación asociada a esa configuración. Por consiguiente, hay un canal asociado a cada elemento de enlace. Los canales se apilan uno sobre otro para crear la implementación concreta del enlace: la pila de canales.  
  
 cliente [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]  
 Construcción de la aplicación cliente que expone las operaciones de servicio como métodos (en el lenguaje de programación [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] de su elección, como Visual Basic o Visual C#). Cualquier aplicación puede alojar a un cliente de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], incluso una aplicación que aloje un servicio. Por consiguiente, es posible crear un servicio que incluya clientes de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] de otros servicios.  
  
 A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] cliente se puede generar automáticamente mediante el uso de la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) y para que apunte a un servicio en ejecución que publica los metadatos.  
  
 metadatos  
 En un servicio, describen las características de este que tiene que comprender una entidad externa para comunicarse con él. Metadatos pueden ser utilizado por el [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar un [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] cliente y la configuración complementaria que una aplicación cliente puede usar para interactuar con el servicio.  
  
 Los metadatos expuestos por el servicio incluyen documentos de esquema XML, que definen el contrato de datos del servicio, y documentos WSDL, que describen los métodos del servicio.  
  
 Cuando se habilita, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] genera automáticamente los metadatos para el servicio mediante la inspección del servicio y sus extremos. Para publicar los metadatos desde un servicio, debe permitir explícitamente al comportamiento de los metadatos.  
  
 seguridad  
 En [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], incluye confidencialidad (cifrado de mensajes para evitar las escuchas no autorizadas), integridad (los recursos para la detección de la manipulación del mensaje), autenticación (los recursos para la validación de servidores y clientes) y autorización (el control del acceso a los recursos). Estas funciones se proporcionan mediante la reutilización de mecanismos de seguridad existentes, como TLS sobre HTTP (también conocido como HTTPS) o la implementación de una o más de las numerosas especificaciones de seguridad WS - *.  
  
 modo de seguridad de transporte  
 Especifica que los mecanismos del nivel de transporte (como HTTPS) proporcionan confidencialidad, integridad y autenticación. El uso de un transporte como HTTPS en este modo tiene la ventaja de ofrecer un mejor rendimiento. También se entiende bien debido a su predominio en Internet. La desventaja es que este tipo de seguridad se aplica por separado en cada salto en la ruta de comunicación, provocando que la comunicación sea susceptible a un ataque tipo “man in the middle”.  
  
 modo de seguridad de mensajes  
 Especifica que se proporciona seguridad mediante la implementación de una o varias de las especificaciones de seguridad, como la especificación denominado [Web Services Security: SOAP Message Security](http://go.microsoft.com/fwlink/?LinkId=94684). Cada mensaje contiene los mecanismos necesarios para proporcionar la seguridad durante su tránsito y para permitir que los receptores detecten la manipulación y el descifrado de mensajes. En este sentido, la seguridad se encapsula dentro de cada mensaje, con lo que se proporciona una seguridad de extremo a extremo en varios saltos. Dado que la información de seguridad se convierte en parte del mensaje, también es posible incluir varios tipos de credenciales con el mensaje (estos se conocen como *notificaciones*). Este enfoque también tiene la ventaja de permitir al mensaje viajar de manera segura sobre cualquier transporte, incluyendo varios transportes entre su origen y destino. La desventaja de este enfoque es la complejidad de los mecanismos de cifrado empleados, que afectan al rendimiento.  
  
 transporte con modo de seguridad de credencial de mensajes  
 Especifica el uso del nivel de transporte para proporcionar la confidencialidad, autenticación e integridad de los mensajes, mientras que cada uno de los mensajes puede contener varias credenciales (notificaciones) requeridas por parte de los receptores del mensaje.  
  
 WS-*  
 Modo abreviado para el creciente conjunto de especificaciones de servicios Web (WS), tales como WS-Security, WS-ReliableMessaging, etc., que se implementan en [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [¿Qué es Windows Communication Foundation?](../../../docs/framework/wcf/whats-wcf.md)  
 [Arquitectura de Windows Communication Foundation](../../../docs/framework/wcf/architecture.md)  
 [Arquitectura de seguridad](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
