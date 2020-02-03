---
title: Introducción al enrutamiento
ms.date: 03/30/2017
ms.assetid: bf6ceb38-6622-433b-9ee7-f79bc93497a1
ms.openlocfilehash: 8ce98aab2ed14401fa7c2cbf43eb92a633fa96b0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746468"
---
# <a name="routing-introduction"></a>Introducción al enrutamiento

El servicio de enrutamiento proporciona un intermediario de SOAP conectable genérico que es capaz de enrutar mensajes en función de su contenido. Con el servicio de enrutamiento, puede crear una lógica de enrutamiento compleja que le permita implementar escenarios como la agregación de servicios, el control de versiones del servicio, el enrutamiento de prioridad y el enrutamiento de multidifusión. El servicio de enrutamiento también proporciona un control de errores, que le permite preparar listas de puntos de conexión de reserva a los que se envían los mensajes si se produce un error al realizar un envío al punto de conexión de destino principal.

Este tema está dirigido a aquellos usuarios que se están iniciando en el servicio de enrutamiento, y cubre la configuración básica y el hospedaje del servicio de enrutamiento.

## <a name="configuration"></a>Configuración

El servicio de enrutamiento se implementa como un servicio de WCF que expone uno o varios puntos de conexión de servicio. Estos puntos de conexión reciben mensajes de aplicaciones cliente y los enrutan a uno o más puntos de conexión de destino. El servicio proporciona <xref:System.ServiceModel.Routing.RoutingBehavior>, que se aplica a los puntos de conexión de servicio que expone el servicio. Este comportamiento se utiliza para configurar varios aspectos del funcionamiento del servicio. Para facilitar la configuración cuando se usa un archivo de configuración, los parámetros se especifican en **RoutingBehavior**. En escenarios basados en código, estos parámetros se especifican como parte de un objeto <xref:System.ServiceModel.Routing.RoutingConfiguration>, que se puede pasar a continuación a un **RoutingBehavior**.

Al iniciarse, este comportamiento agrega el objeto <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, que se utiliza para realizar el procesamiento de SOAP de mensajes, a los puntos de conexión de cliente. Esto permite al servicio de enrutamiento transmitir mensajes a los puntos de conexión que requieren un **MessageVersion** diferente que el punto de conexión en el que se recibió el mensaje. **RoutingBehavior** también registra una extensión de servicio, la <xref:System.ServiceModel.Routing.RoutingExtension>, que proporciona un punto de accesibilidad para modificar la configuración del servicio de enrutamiento en tiempo de ejecución.

La clase **RoutingConfiguration** proporciona un medio coherente para configurar y actualizar la configuración del servicio de enrutamiento.  Contiene parámetros que actúan como la configuración para el servicio de enrutamiento y se usa para configurar el **RoutingBehavior** cuando se inicia el servicio o se pasa a **RoutingExtension** para modificar la configuración de enrutamiento en tiempo de ejecución.

La lógica de enrutamiento utilizada para realizar el enrutamiento basado en el contenido de mensajes se define agrupando varios objetos <xref:System.ServiceModel.Dispatcher.MessageFilter> en tablas de filtro (objetos<xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>). Los mensajes entrantes se evalúan con los filtros de mensajes contenidos en la tabla de filtros, y para cada **MessageFilter** que coincida con el mensaje, se reenvía a un extremo de destino. La tabla de filtros que se debe usar para enrutar los mensajes se especifica mediante el uso de **RoutingBehavior** en la configuración o a través del código mediante el objeto **RoutingConfiguration** .

### <a name="defining-endpoints"></a>Definición de extremos

Pese a que pueda parecer que debería iniciar su configuración definiendo la lógica de enrutamiento que va a utilizar, el primer paso sería realmente determinar la forma de los puntos de conexión a los que va a enrutar mensajes. El servicio de enrutamiento utiliza contratos que definen la forma de los canales utilizados para recibir y enviar mensajes y, por consiguiente, la forma del canal de entrada debe coincidir con la del canal de salida.  Por ejemplo, si va a enrutar mensajes a puntos de conexión que utilizan la forma de canal "solicitud-respuesta", entonces debe utilizar un contrato compatible en los puntos de conexión entrantes, como <xref:System.ServiceModel.Routing.IRequestReplyRouter>.

Esto significa que, si sus extremos de destino utilizan contratos con varios patrones de comunicación (como la combinación de operaciones unidireccionales y bidireccionales), no puede crear ningún extremo de servicio único que pueda recibir y enrutar mensajes a todos ellos. Debe determinar qué puntos de conexión tienen formas compatibles y definir uno o varios puntos de conexión de servicio para recibir los mensajes que se van a enrutar a los puntos de conexión de destino.

> [!NOTE]
> Al trabajar con contratos que especifican varios patrones de comunicación (como una combinación de operaciones unidireccionales y bidireccionales), una solución alternativa sería usar un contrato dúplex en el servicio de enrutamiento, como <xref:System.ServiceModel.Routing.IDuplexSessionRouter>. Sin embargo, esto implica que el enlace debe ser capaz de realizar una comunicación dúplex, algo que puede no ser posible en todos los escenarios. En escenarios en los que esto no sea posible, puede ser necesario dividir la comunicación en varios puntos de conexión o modificar la aplicación.

Para obtener más información sobre los contratos de enrutamiento, consulte [enrutamiento de contratos](routing-contracts.md).

Una vez definido el punto de conexión de servicio, puede usar **RoutingBehavior** para asociar un **RoutingConfiguration** específico con el punto de conexión. Al configurar el servicio de enrutamiento mediante un archivo de configuración, **RoutingBehavior** se utiliza para especificar la tabla de filtros que contiene la lógica de enrutamiento utilizada para procesar los mensajes recibidos en este punto de conexión. Si va a configurar el servicio de enrutamiento mediante programación, puede especificar la tabla de filtros mediante **RoutingConfiguration**.

En el siguiente ejemplo, se definen los puntos de conexión de cliente y servicio que usa el servicio de enrutamiento tanto mediante programación como por medio de un archivo de configuración.

```xml
<services>
  <!--ROUTING SERVICE -->
  <service behaviorConfiguration="routingData"
            name="System.ServiceModel.Routing.RoutingService">
    <host>
      <baseAddresses>
        <add baseAddress="http://localhost:8000/routingservice/router"/>
      </baseAddresses>
    </host>
    <!-- Define the service endpoints that are receive messages -->
    <endpoint address=""
              binding="wsHttpBinding"
              name="reqReplyEndpoint"
              contract="System.ServiceModel.Routing.IRequestReplyRouter" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="routingData">
      <serviceMetadata httpGetEnabled="True"/>
      <!-- Add the RoutingBehavior and specify the Routing Table to use -->
      <routing filterTableName="routingTable1" />
    </behavior>
  </serviceBehaviors>
</behaviors>
<client>
<!-- Define the client endpoint(s) to route messages to -->
  <endpoint name="CalculatorService"
            address="http://localhost:8000/servicemodelsamples/service"
            binding="wsHttpBinding" contract="*" />
</client>
```

```csharp
//set up some communication defaults
string clientAddress = "http://localhost:8000/servicemodelsamples/service";
string routerAddress = "http://localhost:8000/routingservice/router";
Binding routerBinding = new WSHttpBinding();
Binding clientBinding = new WSHttpBinding();
//add the endpoint the router uses to receive messages
serviceHost.AddServiceEndpoint(
     typeof(IRequestReplyRouter),
     routerBinding,
     routerAddress);
//create the client endpoint the router routes messages to
ContractDescription contract = ContractDescription.GetContract(
     typeof(IRequestReplyRouter));
ServiceEndpoint client = new ServiceEndpoint(
     contract,
     clientBinding,
     new EndpointAddress(clientAddress));
//create a new routing configuration object
RoutingConfiguration rc = new RoutingConfiguration();
….
rc.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
//attach the behavior to the service host
serviceHost.Description.Behaviors.Add(
     new RoutingBehavior(rc));
```

En este ejemplo se configura el servicio de enrutamiento para exponer un punto de conexión único con una dirección de `http://localhost:8000/routingservice/router`, que se usa para recibir los mensajes que se van a enrutar. Dado que los mensajes se enrutan a puntos de conexión solicitud-respuesta, el punto de conexión de servicio utiliza el contrato <xref:System.ServiceModel.Routing.IRequestReplyRouter>. Esta configuración también define un punto de conexión de cliente único de `http://localhost:8000/servicemodelsample/service` a la que se enrutan los mensajes. La tabla de filtros (no se muestra) denominada "routingTable1" contiene la lógica de enrutamiento que se usa para enrutar los mensajes y está asociada al punto de conexión de servicio mediante **RoutingBehavior** (para un archivo de configuración) o **RoutingConfiguration** (para la configuración mediante programación).

### <a name="routing-logic"></a>Lógica de enrutamiento

Para definir la lógica de enrutamiento utilizada para enrutar los mensajes, debe determinar sobre qué datos se puede actuar de entre los contenidos dentro de los mensajes entrantes. Por ejemplo, si todos los extremos de destino a los que va a enrutar mensajes comparten las mismas acciones SOAP, el valor de la acción SOAP incluida dentro del mensaje no es un buen indicador de a qué extremo concreto se debe enrutar el mensaje. Si debe enrutar los mensajes únicamente a un punto de conexión concreto, debe filtrar según los datos que identifiquen exclusivamente el punto de conexión de destino al que se enruta el mensaje.

El servicio de enrutamiento proporciona varias implementaciones de **MessageFilter** que inspeccionan valores específicos del mensaje, como la dirección, la acción, el nombre del punto de conexión o incluso una consulta XPath. Si ninguna de estas implementaciones satisface sus necesidades, puede crear una implementación de **MessageFilter** personalizada. Para obtener más información sobre los filtros de mensajes y una comparación de las implementaciones utilizadas por el servicio de enrutamiento, vea [filtros de mensajes](message-filters.md) y [elegir un filtro](choosing-a-filter.md).

Varios filtros de mensajes se organizan juntos en tablas de filtros, que asocian cada **MessageFilter** a un extremo de destino. Opcionalmente, la tabla de filtros también se puede utilizar para especificar una lista de extremos de reserva a los que el servicio de enrutamiento intentará enviar el mensaje en caso de que se produzca un error de transmisión.

De forma predeterminada, todos los filtros de mensajes de una tabla de filtros se evalúan simultáneamente; sin embargo, puede especificar <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A> para que la evaluación de los filtros se efectúe en un orden concreto. Primero se evalúan todas las entradas de mayor prioridad y los filtros de mensaje de menor prioridad no se evalúan si se detecta una coincidencia en un nivel de prioridad más alto. Para obtener más información acerca de las tablas de filtros, vea [filtros de mensajes](message-filters.md).

En los siguientes ejemplos, se utiliza <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, que evalúa todos los mensajes como `true`. Este **MessageFilter** se agrega a la tabla de filtros "routingTable1", que asocia **MessageFilter** con el punto de conexión de cliente denominado "CalculatorService". A continuación, **RoutingBehavior** especifica que esta tabla se debe utilizar para enrutar los mensajes procesados por el punto de conexión de servicio.

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="routingData">
      <serviceMetadata httpGetEnabled="True"/>
      <!-- Add the RoutingBehavior and specify the Routing Table to use -->
      <routing filterTableName="routingTable1" />
    </behavior>
  </serviceBehaviors>
</behaviors>
<!--ROUTING SECTION -->
<routing>
  <filters>
    <filter name="MatchAllFilter1" filterType="MatchAll" />
  </filters>
  <filterTables>
    <table name="routingTable1">
      <filters>
        <add filterName="MatchAllFilter1" endpointName="CalculatorService" />
      </filters>
    </table>
  </filterTables>
</routing>
```

```csharp
//create a new routing configuration object
RoutingConfiguration rc = new RoutingConfiguration();
//create the endpoint list that contains the endpoints to route to
//in this case we have only one
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();
endpointList.Add(client);
//add a MatchAll filter to the Router's filter table
//map it to the endpoint list defined earlier
//when a message matches this filter, it is sent to the endpoint contained in the list
rc.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
```

> [!NOTE]
> De forma predeterminada, el servicio de enrutamiento solo evalúa los encabezados del mensaje. Para permitir a los filtros tener acceso al cuerpo del mensaje, debe establecer <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> en `false`.

**Multidifusión**

Aunque muchas configuraciones del servicio de enrutamiento utilizan una lógica de filtros exclusiva que enruta los mensajes solo a un punto de conexión específico, puede que tenga que enrutar un mensaje determinado a varios puntos de conexión de destino. Para difundir un mensaje a varios destinos, deben cumplirse las siguientes condiciones:

- La forma del canal no puede ser de "solicitud-respuesta" (aunque sí unidireccional o dúplex), porque la aplicación cliente solo puede recibir una respuesta para cada solicitud.

- Varios filtros deben devolver `true` al evaluar el mensaje.

Si se cumplen estas condiciones, el mensaje se enruta a todos los puntos de conexión de todos los filtros que se evalúan como `true`. En el ejemplo siguiente se define una configuración de enrutamiento que hace que los mensajes se enruten a ambos puntos de conexión si la dirección del punto de conexión en el mensaje se `http://localhost:8000/routingservice/router/rounding`.

```xml
<!--ROUTING SECTION -->
<routing>
  <filters>
    <filter name="MatchAllFilter1" filterType="MatchAll" />
    <filter name="RoundingFilter1" filterType="EndpointAddress"
            filterData="http://localhost:8000/routingservice/router/rounding" />
  </filters>
  <filterTables>
    <table name="routingTable1">
      <filters>
        <add filterName="MatchAllFilter1" endpointName="CalculatorService" />
        <add filterName="RoundingFilter1" endpointName="RoundingCalcService" />
      </filters>
    </table>
  </filterTables>
</routing>
```

```csharp
rc.FilterTable.Add(new MatchAllMessageFilter(), calculatorEndpointList);
rc.FilterTable.Add(new EndpointAddressMessageFilter(new EndpointAddress(
    "http://localhost:8000/routingservice/router/rounding")),
    roundingCalcEndpointList);
```

### <a name="soap-processing"></a>Procesamiento de SOAP

Para admitir el enrutamiento de mensajes entre protocolos distintos, **RoutingBehavior** agrega de forma predeterminada el <xref:System.ServiceModel.Routing.SoapProcessingBehavior> a todos los extremos de cliente a los que se enrutan los mensajes. Este comportamiento crea automáticamente un nuevo **messageversion** antes de enrutar el mensaje al punto de conexión, así como la creación de un **messageversion** compatible para cualquier documento de respuesta antes de devolverlo a la aplicación cliente que lo solicita.

Los pasos que se llevan a cabo para crear un nuevo **MessageVersion** para el mensaje de salida son los siguientes:

**Procesamiento de solicitudes**

- Obtiene el **MessageVersion** del enlace o canal de salida.

- Obtenga el lector del cuerpo del mensaje original.

- Cree un nuevo mensaje con la misma acción, el lector del cuerpo y un nuevo **MessageVersion**.

- Si <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Addressing. None**, copie los encabezados to, from, FaultTo y latest en el nuevo mensaje.

- Copie todas las propiedades del mensaje en el nuevo mensaje.

- Almacene el mensaje de solicitud original para utilizarlo al procesar la respuesta.

- Devuelva el nuevo mensaje de solicitud.

**Procesamiento de respuestas**

- Obtiene **MessageVersion** del mensaje de solicitud original.

- Obtenga el lector del cuerpo del mensaje de respuesta recibido.

- Cree un nuevo mensaje de respuesta con la misma acción, el lector del cuerpo y el **MessageVersion** del mensaje de solicitud original.

- Si <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Addressing. None**, copie los encabezados to, from, FaultTo y latest en el nuevo mensaje.

- Copie las propiedades del mensaje en el nuevo mensaje.

- Devuelva el nuevo mensaje de respuesta.

De forma predeterminada, el **SoapProcessingBehavior** se agrega automáticamente a los extremos de cliente por el <xref:System.ServiceModel.Routing.RoutingBehavior> cuando se inicia el servicio; sin embargo, puede controlar si el procesamiento de SOAP se agrega a todos los extremos de cliente mediante la propiedad <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A>. También puede agregar el comportamiento directamente a un punto de conexión específico, y habilitar o deshabilitar este comportamiento en los puntos de conexión si se requiere un control de procesamiento de SOAP más granular.

> [!NOTE]
> Si el procesamiento de SOAP está deshabilitado para un extremo que requiere un valor MessageVersion diferente al del mensaje de solicitud original, debe proporcionar un mecanismo personalizado para que realice todas las modificaciones de SOAP que sean necesarias antes de enviar el mensaje al extremo de destino.

En los ejemplos siguientes, se usa la propiedad **soapProcessingEnabled** para evitar que **SoapProcessingBehavior** se agregue automáticamente a todos los extremos de cliente.

```xml
<behaviors>
  <!--default routing service behavior definition-->
  <serviceBehaviors>
    <behavior name="routingConfiguration">
      <routing filterTableName="filterTable1" soapProcessingEnabled="false"/>
    </behavior>
  </serviceBehaviors>
</behaviors>
```

```csharp
//create the default RoutingConfiguration
RoutingConfiguration rc = new RoutingConfiguration();
rc.SoapProcessingEnabled = false;
```

### <a name="dynamic-configuration"></a>configuración dinámica

Al agregar puntos de conexión de cliente adicionales, o bien cuando necesite modificar los filtros que se utilizan para enrutar los mensajes, debe encontrar una forma de actualizar dinámicamente la configuración en tiempo de ejecución para evitar la interrupción del servicio en los puntos de conexión que estén recibiendo mensajes a través del servicio de enrutamiento en ese momento. Modificar un archivo de configuración o el código de la aplicación host no siempre es suficiente, porque todos los métodos necesitan que se recicle la aplicación y esto conduciría a la pérdida potencial de todos los mensajes que estuvieran en tránsito en ese momento, así como a un posible tiempo de inactividad mientras se aguarda al reinicio del servicio.

Solo puede modificar el **RoutingConfiguration** mediante programación. Aunque puede configurar inicialmente el servicio mediante un archivo de configuración, solo puede modificar la configuración en tiempo de ejecución si crea un nuevo **RoutingConfiguration** y lo pasa como parámetro al método <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> expuesto por la extensión de servicio <xref:System.ServiceModel.Routing.RoutingExtension>. Los mensajes que se encuentran actualmente en tránsito continúan siendo enrutados con la configuración anterior, mientras que los mensajes recibidos después de la llamada a **ApplyConfiguration** usan la nueva configuración. En el siguiente ejemplo, se muestra cómo crear una instancia del servicio de enrutamiento y cómo modificar después la configuración.

```csharp
RoutingConfiguration routingConfig = new RoutingConfiguration();
routingConfig.RouteOnHeadersOnly = true;
routingConfig.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
RoutingBehavior routing = new RoutingBehavior(routingConfig);
routerHost.Description.Behaviors.Add(routing);
routerHost.Open();
// Construct a new RoutingConfiguration
RoutingConfiguration rc2 = new RoutingConfiguration();
ServiceEndpoint clientEndpoint = new ServiceEndpoint();
ServiceEndpoint clientEndpoint2 = new ServiceEndpoint();
// Add filters to the FilterTable in the new configuration
rc2.FilterTable.add(new MatchAllMessageFilter(),
       new List<ServiceEndpoint>() { clientEndpoint });
rc2.FilterTable.add(new MatchAllMessageFilter(),
       new List<ServiceEndpoint>() { clientEndpoint2 });
rc2.RouteOnHeadersOnly = false;
// Apply the new configuration to the Routing Service hosted in
routerHost.routerHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc2);
```

> [!NOTE]
> Al actualizar el servicio de enrutamiento de esta manera, solo es posible pasar una nueva configuración. No se puede modificar únicamente elementos determinados de la configuración actual o anexar nuevas entradas a la configuración actual. Debe crear y pasar una nueva configuración que reemplace la existente.

> [!NOTE]
> Todas las sesiones que se abrieron con la configuración anterior seguirán utilizándola. Sólo las nuevas sesiones usarán la configuración nueva.

## <a name="error-handling"></a>Tratamiento de errores

Si se encuentra algún valor <xref:System.ServiceModel.CommunicationException> al intentar enviar un mensaje, tiene lugar el control de errores. Estas excepciones indican normalmente que se encontró un problema al intentar establecer comunicación con el extremo de cliente definido, como <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> o <xref:System.ServiceModel.CommunicationObjectFaultedException>. El código de control de errores también detectará e intentará volver a realizar el envío cuando se produzca una <xref:System.TimeoutException>, que es otra excepción común que no se deriva de **CommunicationException**.

Cuando se produce una de las excepciones anteriores, el servicio de enrutamiento no puede establecer comunicación con una lista de puntos de conexión de reserva. Si se produce un error de comunicación en todos los puntos de conexión de reserva, o bien si un punto de conexión devuelve una excepción que indica un error dentro del servicio de destino, el servicio de enrutamiento devuelve un error a la aplicación cliente.

> [!NOTE]
> La funcionalidad del control de errores captura y administra excepciones que se producen al intentar enviar un mensaje y al intentar cerrar un canal. El código de control de errores no está diseñado para detectar o administrar excepciones creadas por los puntos de conexión de la aplicación con los que se comunica; un <xref:System.ServiceModel.FaultException> producido por un servicio aparece en el servicio de enrutamiento como **FaultMessage** y se devuelve al cliente.
>
> Si se produce un error cuando el servicio de enrutamiento intenta retransmitir un mensaje, puede obtener un objeto <xref:System.ServiceModel.FaultException> en el lado cliente, en lugar del <xref:System.ServiceModel.EndpointNotFoundException> que obtendría normalmente en ausencia del servicio de enrutamiento. Un servicio de enrutamiento puede por tanto enmascarar las excepciones y no proporcionar una transparencia completa a menos que se examinen las excepciones anidadas.

### <a name="tracing-exceptions"></a>Traza de excepciones

Cuando se produce un error al enviar un mensaje a un punto de conexión en una lista, el servicio de enrutamiento realiza un seguimiento de los datos de excepción resultantes y adjunta los detalles de la excepción como una propiedad de mensaje denominada **Exceptions**. Esto conserva los datos de la excepción y permite al usuario tener acceso mediante programación a través de un inspector del mensaje.  Los datos de la excepción se almacenan por mensaje en un diccionario que asigna el nombre del punto de conexión a los detalles de la excepción producidos al intentar enviarle un mensaje.

### <a name="backup-endpoints"></a>puntos de conexión de reserva

Las entradas de la tabla de filtros pueden especificar también una lista de puntos de conexión de reserva que se utilizarán cuando se produzcan errores de transmisión al enviar mensajes al punto de conexión principal. Si se produce este tipo de error, el servicio de enrutamiento intenta transmitir el mensaje a la primera entrada de la lista de extremos de reserva. Si este intento resulta fallido también, se prueba con el punto de conexión de reserva siguiente de la lista. El servicio de enrutamiento sigue enviando el mensaje a cada uno de los extremos de la lista hasta que el mensaje se recibe correctamente, todos los extremos devuelven un error de transmisión o se produce un error distinto en el extremo.

En los siguientes ejemplos, se configura el servicio de enrutamiento para que utilice una lista de reserva.

```xml
<routing>
  <filters>
    <!-- Create a MatchAll filter that catches all messages -->
    <filter name="MatchAllFilter1" filterType="MatchAll" />
  </filters>
  <filterTables>
    <!-- Set up the Routing Service's Message Filter Table -->
    <filterTable name="filterTable1">
        <!-- Add an entry that maps the MatchAllMessageFilter to the dead destination -->
        <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->
        <!-- Listed in the backupEndpointList -->
        <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>
    </filterTable>
  </filterTables>
  <!-- Create the backup endpoint list -->
  <backupLists>
    <!-- Add an endpoint list that contains the backup destinations -->
    <backupList name="backupEndpointList">
      <add endpointName="realDestination" />
      <add endpointName="backupDestination" />
    </backupList>
  </backupLists>
</routing>
```

```csharp
//create the endpoint list that contains the service endpoints we want to route to
List<ServiceEndpoint> backupList = new List<ServiceEndpoint>();
//add the endpoints in the order that the Routing Service should contact them
//first add the endpoint that we know is down
//clearly, normally you wouldn't know that this endpoint was down by default
backupList.Add(fakeDestination);
//then add the real Destination endpoint
//the Routing Service attempts to send to this endpoint only if it
//encounters a TimeOutException or CommunicationException when sending
//to the previous endpoint in the list.
backupList.Add(realDestination);
//add the backupDestination endpoint
//the Routing Service attempts to send to this endpoint only if it
//encounters a TimeOutException or CommunicationsException when sending
//to the previous endpoints in the list
backupList.Add(backupDestination);
//create the default RoutingConfiguration option
RoutingConfiguration rc = new RoutingConfiguration();
//add a MatchAll filter to the Routing Configuration's filter table
//map it to the list of endpoints defined above
//when a message matches this filter, it is sent to the endpoints in the list in order
//if an endpoint is down or does not respond (which the first endpoint won't
//since the client does not exist), the Routing Service automatically moves the message
//to the next endpoint in the list and try again.
rc.FilterTable.Add(new MatchAllMessageFilter(), backupList);
```

### <a name="supported-error-patterns"></a>Patrones de error admitidos

En la siguiente tabla, se describen los patrones que son compatibles con el uso de listas de puntos de conexión de reserva, junto con notas en las que se describen los detalles del control de errores de patrones específicos.

|Patrón|Sesión|Transacción|Contexto de recepción|Lista de reserva admitida|Notas|
|-------------|-------------|-----------------|---------------------|---------------------------|-----------|
|Unidireccional||||Sí|Intenta reenviar el mensaje a un punto de conexión de reserva. Si este mensaje se envía por multidifusión, solo el mensaje del canal fallido se mueve a su destino de reserva.|
|Unidireccional||✔️||No|Se lanza una excepción y se deshace la transacción.|
|Unidireccional|||✔️|Sí|Intenta reenviar el mensaje a un punto de conexión de reserva. Una vez recibido correctamente el mensaje, rellene todos los contextos de recepción. Si ninguno de los extremos recibe correctamente el mensaje, no rellene el contexto de recepción.<br /><br /> Cuando este mensaje se envía por multidifusión, el contexto de recepción solo se rellena si al menos un punto de conexión (principal o de reserva) recibe correctamente el mensaje. Si ninguno de los puntos de conexión de las rutas de acceso de multidifusión recibe el mensaje correctamente, no rellene el contexto de recepción.|
|Unidireccional||✔️|✔️|Sí|Anule la transacción anterior, cree una transacción nueva y reenvíe todos los mensajes. Los mensajes que detectaron un error se transmiten a un destino de copia de seguridad.<br /><br /> Una vez creada una transacción que realiza correctamente todas las transmisiones, rellene los contextos de recepción y confirme la transacción.|
|Unidireccional|✔️|||Sí|Intenta reenviar el mensaje a un punto de conexión de reserva. En un escenario de multidifusión solo se reenvían a destinos de reserva los mensajes de sesiones en las que se produjo un error o que no pudieron cerrarse.|
|Unidireccional|✔️|✔️||No|Se lanza una excepción y se deshace la transacción.|
|Unidireccional|✔️||✔️|Sí|Intenta reenviar el mensaje a un punto de conexión de reserva. Una vez que todos los envíos de mensaje se realizan correctamente, la sesión indica que no hay más mensajes y el servicio de enrutamiento cierra todos los canales de sesión salientes, se rellenan todos los contextos de recepción y se cierra el canal de sesión entrante.|
|Unidireccional|✔️|✔️|✔️|Sí|Anule la transacción actual y cree una nueva. Reenvíe todos los mensajes anteriores de la sesión. Una vez que se crea una transacción en la que todos los mensajes se envían correctamente y la sesión indica que no hay más mensajes, se cierran todos los canales de sesión salientes, se rellenan todos los contextos de recepción con la transacción, se cierra el canal de sesión entrante y se confirma la transacción.<br /><br /> Cuando las sesiones son de multidifusión, los mensajes que no produjeron errores se reenvían al mismo destino y los mensajes que sí los produjeron se envían a los destinos de reserva.|
|Bidireccional||||Sí|Realice un envío a un destino de reserva.  Una vez que el canal devuelve un mensaje de respuesta, devuelva la respuesta al cliente original.|
|Bidireccional|✔️|||Sí|Envíe todos los mensajes del canal a un destino de reserva.  Una vez que el canal devuelve un mensaje de respuesta, devuelva la respuesta al cliente original.|
|Bidireccional||✔️||No|Se lanza una excepción y se deshace la transacción.|
|Bidireccional|✔️|✔️||No|Se lanza una excepción y se deshace la transacción.|
|Dúplex||||No|Actualmente, no se admite una comunicación dúplex que no sea de sesiones.|
|Dúplex|✔️|||Sí|Realice un envío a un destino de reserva.|

## <a name="hosting"></a>Hospedaje

Dado que el servicio de enrutamiento se implementa como un servicio WCF, debe auto-hospedarse en una aplicación o ser hospedado por un servidor IIS o WAS. Se recomienda que el servicio de enrutamiento se hospede bien en un IIS, en un WAS o en una aplicación de un servicio Windows para que pueda aprovecharse de las características de administración de ciclo de vida y de inicio automático que están disponibles en estos entornos de hospedaje.

En el siguiente ejemplo, se muestra cómo hospedar el servicio de enrutamiento en una aplicación.

```csharp
using (ServiceHost serviceHost =
                new ServiceHost(typeof(RoutingService)))
```

Para hospedar el servicio de enrutamiento dentro de un IIS o WAS, debe crear un archivo de servicio (.svc) o utilizar la activación basada en configuración del servicio. Al utilizar un archivo de servicio, debe especificar la clase <xref:System.ServiceModel.Routing.RoutingService> que utiliza el parámetro del servicio. El siguiente ejemplo contiene un archivo de servicio de ejemplo que se puede utilizar para hospedar el servicio de enrutamiento con IIS o WAS.

```aspx-csharp
<%@ ServiceHost Language="C#" Debug="true" Service="System.ServiceModel.Routing.RoutingService,
     System.ServiceModel.Routing, version=4.0.0.0, Culture=neutral,
     PublicKeyToken=31bf3856ad364e35" %>
```

## <a name="routing-service-and-impersonation"></a>Servicio de enrutamiento y suplantación

El Servicio de enrutamiento de WCF se puede usar con suplantación para enviar y recibir mensajes. Todas las restricciones habituales de Windows de suplantación se aplican. Si hubiera necesitado configurar permisos de servicio o de cuenta para usar la suplantación al escribir su propio servicio, tendría que realizar los mismos pasos para usar la suplantación con el servicio de enrutamiento. Para obtener más información, consulte [delegación y suplantación](delegation-and-impersonation-with-wcf.md).

La suplantación con el servicio de enrutamiento necesita tanto el uso de la suplantación de ASP.NET mientras está en modo de compatibilidad de ASP.NET como el uso de credenciales de Windows que se han configurado para permitir la suplantación. Para obtener más información sobre el modo de compatibilidad de ASP.NET, consulte [servicios WCF y ASP.net](wcf-services-and-aspnet.md).

> [!WARNING]
> El Servicio de enrutamiento de WCF no admite la suplantación con la autenticación básica.

Para usar la suplantación de ASP.NET con el servicio de enrutamiento, habilite el modo de compatibilidad de ASP.NET en el entorno de hospedaje del servicio. El servicio de enrutamiento se ha ya marcado como que permite el modo de compatibilidad de ASP.NET y la suplantación se habilitará automáticamente. La suplantación es el único uso admitido de la integración de ASP.NET con el servicio de enrutamiento.

Para usar la suplantación de la credencial de Windows con el servicio de enrutamiento, necesita configurar las credenciales y el servicio. El objeto de credenciales de cliente (<xref:System.ServiceModel.Security.WindowsClientCredential>, accesible desde <xref:System.ServiceModel.ChannelFactory>) define una propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> que se debe establecer para permitir la suplantación. Finalmente, en el servicio se debe configurar el comportamiento <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> para establecer `ImpersonateCallerForAllOperations` en `true`. El servicio de enrutamiento usa esta marca para decidir si crear los clientes para reenviar mensajes con la suplantación habilitada.

## <a name="see-also"></a>Consulte también

- [Filtros de mensajes](message-filters.md)
- [Enrutamiento de contratos](routing-contracts.md)
- [Elección de un filtro](choosing-a-filter.md)
