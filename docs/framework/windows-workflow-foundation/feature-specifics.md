---
title: Detalles de las características de Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: 11bde5edea44f09ef1a5658cdf0e20ec1349c84b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182920"
---
# <a name="windows-workflow-foundation-feature-specifics"></a>Detalles de las características de Windows Workflow Foundation

.NET Framework 4 agrega una serie de características a Windows Workflow Foundation. Este documento describe algunas de las nuevas características y proporciona detalles sobre los escenarios en que pueden ser útiles.

## <a name="messaging-activities"></a>Actividades de mensajería

Las actividades de<xref:System.ServiceModel.Activities.Receive> <xref:System.ServiceModel.Activities.SendReply>mensajería ( , , <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) se usan para enviar y recibir mensajes WCF desde el flujo de trabajo. <xref:System.ServiceModel.Activities.Receive>y <xref:System.ServiceModel.Activities.SendReply> las actividades se usan para formar una operación de servicio de Windows Communication Foundation (WCF) que se expone a través de WSDL al igual que los servicios web WCF estándar. <xref:System.ServiceModel.Activities.Send>y <xref:System.ServiceModel.Activities.ReceiveReply> se usan para consumir un <xref:System.ServiceModel.ChannelFactory>servicio web similar a un WCF; También existe una experiencia **Agregar referencia** de servicio para Workflow Foundation que genera actividades preconfiguradas.

### <a name="getting-started-with-messaging-activities"></a>Introducción a las actividades de mensajería

- En Visual Studio 2012, cree un proyecto de aplicación de servicio de flujo de trabajo WCF. Se colocará un par <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply> en el lienzo.

- Haga clic con el botón derecho en el proyecto y seleccione **Agregar referencia de servicio**. Seleccione un WSDL de servicio web existente y haga clic en **Aceptar**. Compile el proyecto para mostrar las actividades <xref:System.ServiceModel.Activities.Send> <xref:System.ServiceModel.Activities.ReceiveReply>generadas (implementadas mediante y ) en la caja de herramientas.

- [Documentación de servicios de flujo de trabajo](../wcf/feature-details/workflow-services.md)

### <a name="messaging-activities-example-scenario"></a>Escenario de ejemplo de actividades de mensajería

Un `BestPriceFinder` servicio llama a varios servicios de aerolíneas para encontrar el mejor precio de billete para una ruta en particular. La implementación de este escenario requeriría usar las actividades de mensaje para recibir la solicitud de precio, recuperar los precios de los servicios back-end y responder a la solicitud de precio con el mejor precio. También requeriría que utilice otras actividades listas para usar para crear la lógica de negocios para calcular el mejor precio.

## <a name="workflowservicehost"></a>WorkflowServiceHost

Es <xref:System.ServiceModel.WorkflowServiceHost> el host de flujo de trabajo listo para usar que admite varias instancias, configuración y mensajería WCF (aunque los flujos de trabajo no son necesarios para usar la mensajería para hospedarse). También se integra con la persistencia, el seguimiento y el control de instancias a través de un conjunto de comportamientos de servicio. Al igual que <xref:System.ServiceModel.ServiceHost>WCF, se <xref:System.ServiceModel.WorkflowServiceHost> puede hospedar automáticamente en una consola/aplicación WinForms/WPF o servicio de Windows, o hospedado en web (como un archivo .xamlx) en IIS o WAS.

### <a name="getting-started-with-workflow-service-host"></a>Introducción a host de servicio de flujo de trabajo

- En Visual Studio 2010, cree un proyecto de aplicación de <xref:System.ServiceModel.WorkflowServiceHost> servicio de flujo de trabajo de WCF: este proyecto se configurará para usaren en un entorno de host web.

- Para hospedar un flujo de trabajo que no sea de mensajería, agregue un elemento <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> personalizado que creará la instancia basándose en un mensaje.

- Las instancias de flujo de trabajo se pueden controlar (por ejemplo suspender o finalizar) agregando un elemento <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> al host <xref:System.ServiceModel.WorkflowServiceHost> y utilizando después un elemento <xref:System.ServiceModel.Activities.WorkflowControlClient>.

- Los ejemplos para <xref:System.ServiceModel.WorkflowServiceHost> se pueden encontrar en las siguientes secciones:

  - [Ejecución](./samples/execution.md)

  - Aplicación: Administración de [instancias suspendidas](./samples/suspended-instance-management.md)

- [Descripción general de los servicios de flujo de trabajo de hospedaje](../wcf/feature-details/hosting-workflow-services-overview.md)

### <a name="workflowservicehost-scenario"></a>Escenario de WorkflowServiceHost

Un servicio BestPriceFinder llama a varios servicios de aerolíneas para encontrar el mejor precio de boleto para una ruta en particular. La implementación de este escenario <xref:System.ServiceModel.WorkflowServiceHost>requeriría hospedar el flujo de trabajo en . También utilizaría las actividades de mensajes para recibir la solicitud de precio, recuperar los precios de los servicios back-end y responder a la solicitud de precio con el mejor precio.

## <a name="correlation"></a>Correlation

Una correlación es una de estas dos cosas:

- Una forma de agrupar mensajes; es decir, la relación entre un mensaje de solicitud y su respuesta.

- Una forma de asignar un fragmento de datos a una instancia de servicio.

### <a name="getting-started"></a>Introducción

- Para iniciarse en la correlación, cree un nuevo proyecto en Visual Studio. Cree una variable de tipo <xref:System.ServiceModel.Activities.CorrelationHandle>.

- Un ejemplo de correlación utilizado para agrupar mensajes es una correlación solicitud-respuesta que agrupa los mensajes.

  - En <xref:System.ServiceModel.Activities.Receive> una actividad, <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> haga clic <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> en la propiedad y agregue un using el CorrelationHandle creado en el primer paso anterior.

  - Cree <xref:System.ServiceModel.Activities.SendReply> una actividad haciendo clic <xref:System.ServiceModel.Activities.Receive> con el botón derecho en el botón derecho y haciendo clic en "Crear SendReply". Péguela en su flujo de trabajo después de la actividad <xref:System.ServiceModel.Activities.Receive>.

- Un ejemplo de asignación de un fragmento de datos a una instancia de servicio es la correlación basada en contenido que asigna un fragmento de datos (por ejemplo, un identificador de pedido) a una instancia de flujo de trabajo en particular.

  - En cualquier actividad de mensajería, haga clic en la propiedad `CorrelationInitializers` y agregue un elemento <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> utilizando la variable <xref:System.ServiceModel.Activities.CorrelationHandle> creada anteriormente. Haga doble clic en la propiedad deseada en el mensaje (por ejemplo, OrderID) del menú desplegable. Establezca la propiedad `CorrelatesWith` en la variable <xref:System.ServiceModel.Activities.CorrelationHandle> utilizada anteriormente.

- [Documentación conceptual de correlación](../wcf/feature-details/correlation.md)

### <a name="correlation-scenario"></a>Escenario de correlación

Un flujo de trabajo de procesamiento de pedidos se utiliza para gestionar la creación de nuevos pedidos y la actualización de pedidos existentes que están en proceso. Implementar este escenario requeriría hospedar el <xref:System.ServiceModel.WorkflowServiceHost> flujo de trabajo y usar las actividades de mensajería. También requeriría correlación basada `orderId` en el para asegurarse de que las actualizaciones se realizan en el flujo de trabajo correcto.

## <a name="simplified-configuration"></a>Configuración simplificada

El esquema de configuración de WCF es complejo y proporciona a los usuarios muchas características difíciles de encontrar. En [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], nos hemos centrado en ayudar a los usuarios de WCF a configurar sus servicios con las siguientes características:

- Eliminar la necesidad de configuración por servicio explícita. Si no configura \<ningún servicio> elementos para el servicio y el servicio no define mediante programación ningún punto de conexión, se agregará automáticamente un conjunto de puntos de conexión al servicio, uno por dirección base de servicio y por contrato implementado por el servicio.

- Permite al usuario definir valores predeterminados para los comportamientos y enlaces de WCF, que se aplicarán a los servicios sin ninguna configuración explícita.

- Los puntos de conexión estándar definen puntos de conexión preconfigurados reutilizables, que tienen valores fijos para una o varias propiedades de punto de conexión (dirección, enlace y contrato), y permiten la definición de propiedades personalizadas.

- Por último, permite <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> realizar la administración central de la configuración de cliente WCF, útil en escenarios en los que se selecciona o cambia la configuración después del tiempo de carga del dominio de aplicación.

### <a name="getting-started"></a>Introducción

- [Guía del desarrollador para WCF 4.0](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))

- [Generador de canales de configuración](xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601)

- [Elemento de extremo estándar](xref:System.ServiceModel.Configuration.StandardEndpointElement)

- [Mejoras en la configuración del servicio en .NET Framework 4](https://docs.microsoft.com/archive/blogs/endpoint/service-configuration-improvements-in-net-4)

- [Error común del usuario en .NET 4: escribir incorrectamente el nombre de configuración de servicio de WF/WCF](https://docs.microsoft.com/archive/blogs/endpoint/common-user-mistake-in-net-4-mistyping-the-wfwcf-service-configuration-name)

### <a name="simplified-configuration-scenarios"></a>Escenarios de configuración simplificados

- Un desarrollador ASMX experimentado desea empezar a usar WCF. Sin embargo, WCF parece demasiado complicado! ¿Qué es toda la información que necesito escribir en un archivo de configuración? En .NET 4, se puede decidir incluso no tener un archivo de configuración en absoluto.

- Un conjunto existente de servicios de WCF es muy difícil de configurar y mantener. El archivo de configuración tiene miles de líneas de código XML cuya modificación es sumamente peligrosa. Se necesita ayuda para reducir esa cantidad de código a algo más fácil de tratar.

## <a name="data-contract-resolver"></a>Resolución del contrato de datos

En .NET 3.5, había unas cuantas limitaciones en el diseño de tipos conocidos:

- No era posible agregar tipos conocidos dinámicamente durante la serialización o la deserialización.

- Los serializadores no podían tratar información de xsi:type desconocida.

- No era posible que los usuarios especificasen qué xsi:type preferirían que apareciese en la conexión para, por ejemplo, reducir el tamaño de una instancia de serialización en la conexión.

[DataContractResolver](../wcf/samples/datacontractresolver.md) resuelve estos problemas en .NET 4.5.

### <a name="getting-started"></a>Introducción

- [Documentación de la API de resolución del contrato de datos](xref:System.Runtime.Serialization.DataContractResolver)

- [Introducir la resolución del contrato de datos](https://docs.microsoft.com/archive/blogs/youssefm/configuring-known-types-dynamically-introducing-the-datacontractresolver)

- Ejemplos:

  - [DataContractResolver](../wcf/samples/datacontractresolver.md)

  - [KnownAssemblyAttribute](../wcf/samples/knownassemblyattribute.md)

### <a name="data-contract-resolver-scenarios"></a>Escenarios de resolución del contrato de datos

- Evitar tener que declarar decenas de objetos <xref:System.Runtime.Serialization.KnownTypeAttribute> en un servicio.

- Reducir el tamaño del blob XML.

## <a name="flowchart"></a>Diagrama de flujo

El diagrama de flujo es un paradigma conocido para representar visualmente los problemas de dominio. Es un nuevo estilo de flujo de control que estamos introduciendo en .NET 4. Una característica básica de diagrama de flujo es que solo se ejecuta una actividad en un momento dado. Los diagramas de flujo pueden expresar bucles y resultados alternativos, pero no pueden expresar de forma nativa la ejecución simultánea de varios nodos.

### <a name="getting-started"></a>Introducción

- En Visual Studio 2012, cree una aplicación de consola de flujo de trabajo. Agregue un diagrama de flujo en el diseñador de flujo de trabajo.

- La característica de diagrama de flujo utiliza las siguientes clases:

  - <xref:System.Activities.Statements.Flowchart>

  - <xref:System.Activities.Statements.FlowNode>

  - <xref:System.Activities.Statements.FlowDecision>

  - <xref:System.Activities.Statements.FlowStep>

  - <xref:System.Activities.Statements.FlowSwitch%601>

- Ejemplos:

  - [Control de errores en una actividad de diagrama de flujo utilizando TryCatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

  - [Proceso de contratación](./samples/hiring-process.md)

- Documentación del diseñador:

  - [Diseñadores de actividad de diagrama de flujo](/visualstudio/workflow-designer/flowchart-activity-designers)

### <a name="flowchart-scenarios"></a>Escenarios de diagrama de flujo

Una actividad de diagrama de flujo se puede utilizar para implementar un juego de adivinanzas. Este juego es muy simple: el equipo selecciona un número aleatorio y el jugador tiene que adivinar el número. Cuando el jugador envía cada conjetura, el ordenador le muestra una pista (es decir, "probar un número más bajo"). Si el jugador encuentra el número en menos de 7 intentos, recibe una felicitación especial de la computadora. Este juego se puede implementar con una combinación de las siguientes actividades de procedimiento:

- <xref:System.Activities.Statements.Sequence>

- <xref:System.Activities.Statements.While>

- <xref:System.Activities.Statements.Switch%601>

- <xref:System.Activities.Statements.TryCatch>

- <xref:System.Activities.Statements.Assign%601>

- <xref:System.Activities.Statements.If>

## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a>Actividades de procedimiento (Sequence, If, ForEach, Switch, Assign, DoWhile, While)

Las actividades de procedimiento proporcionan un mecanismo para modelar el flujo de control secuencial utilizando conceptos familiares para los programadores. Estas actividades permiten construcciones de lenguaje de programación estructuradas tradicionalmente y, cuando corresponda, proporcionan paridad de lenguaje con lenguajes de procedimiento comunes, como C- y Visual Basic.

### <a name="getting-started"></a>Introducción

- En Visual Studio 2012, cree una aplicación de consola de flujo de trabajo. Agregue actividades de procedimiento en el diseñador de flujo de trabajo.

- Ejemplos:

  - [Proceso de contratación](./samples/hiring-process.md)

  - [Proceso de compra corporativa](./samples/corporate-purchase-process.md)

- Documentación del diseñador:

  - [Diseñador de actividad Parallel](/visualstudio/workflow-designer/parallel-activity-designer)

  - [ParallelForEach\<T> diseñador de actividades](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)

### <a name="procedural-activity-scenarios"></a>Escenarios de actividad de procedimiento

- <xref:System.Activities.Statements.Parallel>: un sistema de gestión de documentos de intranet tiene un flujo de trabajo de aprobación de documentos. Los documentos necesitan ser aprobados por personas en varios departamentos antes de poderse publicar en la intranet. No hay un orden establecido para las aprobaciones; pueden ocurrir en cualquier momento mientras el documento está en la fase de "aprobación pendiente". Cuando un usuario envía un documento para su revisión, debe ser aprobado por su administrador directo, el administrador de intranet y el administrador de comunicaciones interna.

- <xref:System.Activities.Statements.ParallelForEach%601>: una aplicación de WF administra las compras corporativas dentro de una gran compañía. Las reglas corporativas establecen que, antes de planear cualquier operación de compra, se requieren las valoraciones de tres proveedores diferentes. Un empleado del departamento de compras selecciona tres proveedores de la lista de proveedores de la empresa. Una vez seleccionados e informados estos proveedores, la compañía esperará a que realicen sus propuestas económicas. Las propuestas pueden llegar en cualquier orden. Para implementar este escenario en WF, se utiliza un elemento <xref:System.Activities.Statements.ParallelForEach%601> que recorrerá en iteración la colección de proveedores y pedirá sus propuestas económicas. Una vez reunidas todas las ofertas, se selecciona y se muestra la mejor.

## <a name="invokemethod"></a>InvokeMethod

La actividad <xref:System.Activities.Statements.InvokeMethod> permite invocar métodos públicos en objetos o tipos dentro del ámbito. Admite la invocación de métodos estáticos y de instancia con o sin parámetros (incluidas matrices de parámetros) y de métodos genéricos. También permite la ejecución de métodos sincrónica y asincrónicamente.

### <a name="getting-started"></a>Introducción

- En Visual Studio 2012, cree una aplicación de consola de flujo de trabajo. Agregue una actividad <xref:System.Activities.Statements.InvokeMethod> en el diseñador de flujo de trabajo y configure en él métodos estáticos y de instancia.

- Documentación del diseñador: [InvokeMethod Activity Designer](/visualstudio/workflow-designer/invokemethod-activity-designer)

### <a name="invokemethod-scenarios"></a>Escenarios de InvokeMethod

- Se necesita invocar un método en un objeto dentro del ámbito. Por ejemplo, se necesita agregar un valor a un diccionario. Se invoca el método Add de la instancia del diccionario y se proporcionan la clave y el valor.

- Se necesita invocar un método en un objeto CLR heredado. En lugar de crear una actividad personalizada para encapsular la llamada a esa clase heredada, si permanece dentro del ámbito durante la ejecución del flujo de trabajo, se puede utilizar <xref:System.Activities.Statements.InvokeMethod>.

## <a name="error-handling-activities"></a>Actividades de control de errores

La <xref:System.Activities.Statements.TryCatch> actividad proporciona un mecanismo para detectar excepciones que se producen durante la ejecución de un conjunto de actividades contenidas (similar a la Try/Catch construcción en C - y Visual Basic). <xref:System.Activities.Statements.TryCatch> proporciona control de excepciones en el nivel de flujo de trabajo. Cuando se produce una excepción no controlada, se anula el flujo de trabajo y el finally bloque no se ejecutará. Este comportamiento es coherente con C#.

### <a name="getting-started"></a>Introducción

- En Visual Studio 2012, cree una aplicación de consola de flujo de trabajo. Agregue una actividad <xref:System.Activities.Statements.TryCatch> en el diseñador de flujo de trabajo.

- Ejemplo: Manejo de errores en una actividad de diagrama de [flujo mediante TryCatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

- Documentación del diseñador: [Diseñadores](/visualstudio/workflow-designer/error-handling-activity-designers) de actividad de manejo de errores

### <a name="error-handling-scenarios"></a>Escenarios de control de errores

Necesita ejecutarse un conjunto de actividades y es necesaria la ejecución de una lógica específica cuando se produce un error. Si durante esa lógica de control de errores se encuentra que el error no es recuperable, volverá a producirse la excepción y la actividad primaria (o el host) abordará el problema.

## <a name="pick-activity"></a>Actividad Pick

La actividad <xref:System.Activities.Statements.Pick> proporciona un modelado de flujo de control basado en eventos en WF. <xref:System.Activities.Statements.Pick> contiene muchas bifurcaciones donde cada bifurcación espera que se produzca un evento determinado antes de ejecutarse. En esta configuración, el comportamiento de <xref:System.Activities.Statements.Pick> es similar al de <xref:System.Activities.Statements.Switch%601>, ya que la actividad solo ejecutará un evento del conjunto de eventos de los que está realizando escuchas. Cada bifurcación está orientada a eventos y el evento que se produzca ejecutará primero la bifurcación correspondiente. El resto de bifurcaciones se cancelan y se dejan de realizar escuchas de eventos.

### <a name="getting-started"></a>Introducción

- En Visual Studio 2012, cree una aplicación de consola de flujo de trabajo. Agregue una actividad <xref:System.Activities.Statements.Pick> en el diseñador de flujo de trabajo.

- Ejemplo: [Uso de la actividad Pick](./samples/using-the-pick-activity.md)

- Documentación del diseñador: [Elija el Diseñador de actividades](/visualstudio/workflow-designer/pick-activity-designer)

### <a name="pick-scenario"></a>Escenario de Pick

Se necesita solicitar una entrada a un usuario. En circunstancias normales, el desarrollador <xref:System.Console.ReadLine%2A> usaría una llamada al método como para solicitar la entrada de un usuario. El problema con esta configuración es que el programa espera hasta que el usuario especifica algo. En este escenario, se necesita un tiempo de espera para desbloquear una actividad de bloqueo. Un escenario común es el que requiere que una tarea se complete dentro de un período de tiempo determinado. El agotamiento del tiempo de espera de una actividad de bloqueo es un escenario en el que Pick agrega gran cantidad de valor.

## <a name="wcf-routing-service"></a>Servicio de enrutamiento de WCF

El servicio de enrutamiento está diseñado para ser un enrutador de software genérico que le permite controlar cómo fluyen los mensajes WCF entre los clientes y los servicios. El servicio de enrutamiento le permite desacoplar a sus clientes de sus servicios, lo que le da mucha más libertad en términos de las configuraciones que puede admitir y la flexibilidad que tiene al considerar cómo hospedar sus servicios. En .NET 3.5, los clientes y los servicios estaban estrechamente acoplados; un cliente tenía que saber sobre todos los servicios que necesitaba para hablar y dónde se encontraban. Además, WCF en .NET Framework 3.5 tenía las siguientes limitaciones:

- El control de errores era complejo, ya que esta lógica tenía que codificarse de forma rígida en el cliente.

- Los clientes y los servicios tenían que utilizar siempre los mismos enlaces.

- Los servicios raramente se factorizaban correctamente: es más fácil que el cliente hable con un servicio que implementa todo en lugar de tener que elegir entre varios servicios.

El servicio de enrutamiento de .NET 4 está diseñado para facilitar la resolución de estos problemas. El nuevo servicio de enrutamiento tiene las siguientes características:

1. Enrutamiento basado en contenido (los objetos <xref:System.ServiceModel.Dispatcher.MessageFilter> examinan un mensaje para determinar dónde se debe enviar).

2. Puente de protocolo (mensaje de transporte &)

3. Control de errores (el enrutador detecta excepciones de comunicación y no puede establecer comunicación con los puntos de conexión de reserva)

4. Actualización dinámica (en memoria) de <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> y configuración de enrutamiento.

### <a name="getting-started"></a>Introducción

1. Documentación: [Enrutamiento](../wcf/feature-details/routing.md)

2. Ejemplos: [servicios de enrutamiento &#91;ejemplos de WCF&#93;](../wcf/samples/routing-services.md)

3. Blog: [¡Reglas de enrutamiento!](https://docs.microsoft.com/archive/blogs/RoutingRules/)

### <a name="routing-scenarios"></a>Escenarios de enrutamiento

El servicio de enrutamiento es útil en los siguientes escenarios:

- Los clientes pueden hablar con varios servicios sin tener que dirigirse a todos ellos directamente.

- Los clientes pueden realizar lógica adicional en la solicitud de un cliente para determinar dónde hay que enrutarlo.

- Descomponer las operaciones que un cliente realiza en varias implementaciones de servicio sin refactorizar el cliente.

- Los clientes y los servicios pueden hablar con enlaces diferentes que tienen configuraciones de seguridad diferentes.

- Puede habilitarse a los clientes para que sean más sólidos ante errores o la no disponibilidad de servicios.

## <a name="wcf-discovery"></a>Detección de WCF

Detección de WCF es una tecnología de marco de trabajo que le permite incorporar un mecanismo de detección a la infraestructura de la aplicación. Puede utilizarla para hacer su servicio reconocible y configurar los clientes para buscar los servicios. Los clientes ya no necesitan estar codificados de forma rígida con el extremo, lo que hace que la aplicación sea más sólida y tolerante a los errores. La detección es la plataforma perfecta para integrar capacidades de autoconfiguración en la aplicación.

El producto se basa en la norma WS-Discovery. Está diseñado para ser interoperable, extensible y genérico. El producto admite dos modos de operación:

1. Administrado: donde hay una entidad en la red con gran conocimiento de los servicios existentes; los clientes la consultan directamente para obtener información. Esto es análogo a Active Directory.

2. Ad hoc: donde los clientes utilizan los mensajes de multidifusión para buscar los servicios.

Además, los mensajes de detección son válidos para distintos protocolos de red; pueden utilizarse sobre cualquier protocolo que admita los requisitos de modo. Por ejemplo, los mensajes de multidifusión de detección se pueden enviar a través del canal UDP o de cualquier otra red que admita la mensajería de multidifusión. Estos puntos de diseño, combinados con la flexibilidad de las características, le permiten adaptar el descubrimiento específicamente a su solución.

### <a name="getting-started"></a>Introducción

- Documentación: [Detección de WCF](../wcf/feature-details/wcf-discovery.md)

- Ejemplos: [Descubrimiento (muestras)](../wcf/samples/discovery-samples.md)

### <a name="discovery-scenarios"></a>Escenarios de detección

Un desarrollador no desea programar de forma rígida los puntos de conexión, porque no se sabe cuándo estará disponible un servicio determinado. En su lugar, desea elegir un servicio en tiempo de ejecución. Se necesita más desacoplamiento, solidez y autoconfiguración entre los componentes de la aplicación.

## <a name="tracking"></a>Seguimiento

El seguimiento del flujo de trabajo proporciona información sobre la ejecución de una instancia de flujo de trabajo. Los eventos de seguimiento se emiten desde un flujo de trabajo en el nivel de instancia de flujo de trabajo y cuando se ejecutan actividades dentro del flujo de trabajo. Se necesita agregar un participante de seguimiento de flujo de trabajo al host de flujo de trabajo para suscribirse a los registros de seguimiento. Los registros de seguimiento se filtran utilizando un perfil de seguimiento. .NET Framework proporciona un participante de seguimiento ETW (Seguimiento de eventos para Windows) y se instala un perfil básico en el archivo machine.config.

### <a name="getting-started"></a>Introducción

1. En Visual Studio 2010, cree un proyecto de aplicación de servicio de flujo de trabajo WCF. Se colocará un par <xref:System.ServiceModel.Activities.Receive> y <xref:System.ServiceModel.Activities.SendReply> en el lienzo para empezar.

2. Abra web.config y agregue un comportamiento de seguimiento de ETW sin ningún perfil.

    1. Se utiliza el perfil predeterminado.

    2. Abra el visor de eventos y habilite el canal analítico en el siguiente nodo: **Visor**de eventos , **Registros**de aplicaciones y servicios , **Microsoft**, **Windows**, Aplicaciones de **servidor de**aplicaciones . Haga clic con el botón derecho en **Analítico** y seleccione **Habilitar registro**.

    3. Ejecute el servicio de flujo de trabajo.

    4. Observe los eventos de seguimiento de flujo de trabajo en el visor de eventos.

3. Ejemplos: [Seguimiento](./samples/tracking.md)

4. Documentación conceptual: [Seguimiento y seguimiento](workflow-tracking-and-tracing.md) del flujo de trabajo

## <a name="sql-workflow-instance-store"></a>Almacén de instancias de flujo de trabajo de SQL

<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> es una implementación basada en SQL Server de un almacén de instancias. Un almacén de instancias almacena el estado de una instancia en ejecución junto con todos los datos necesarios para cargar y reanudar esa instancia. El host de servicio indica al almacén de instancias que guarde el estado de la instancia si el flujo de trabajo persiste y le indica también que cargue el estado de la instancia cuando llegue un mensaje para esa instancia o expire una actividad Delay.

### <a name="getting-started"></a>Introducción

1. En Visual Studio 2012, cree un flujo <xref:System.Activities.Statements.Persist> de trabajo que contenga una actividad implícita o explícita. Agregue el comportamiento de <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> al host de servicio de flujo de trabajo. Esto se puede realizar en el código o en el archivo de configuración de la aplicación.

2. Muestras: [Persistencia](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))

3. Documentación conceptual: Almacén de [instancias](sql-workflow-instance-store.md)de flujo de trabajo de SQL .
