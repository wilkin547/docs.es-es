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
# <a name="routing-introduction"></a><span data-ttu-id="a0992-102">Introducción al enrutamiento</span><span class="sxs-lookup"><span data-stu-id="a0992-102">Routing Introduction</span></span>

<span data-ttu-id="a0992-103">El servicio de enrutamiento proporciona un intermediario de SOAP conectable genérico que es capaz de enrutar mensajes en función de su contenido.</span><span class="sxs-lookup"><span data-stu-id="a0992-103">The Routing Service provides a generic pluggable SOAP intermediary that is capable of routing messages based on message content.</span></span> <span data-ttu-id="a0992-104">Con el servicio de enrutamiento, puede crear una lógica de enrutamiento compleja que le permita implementar escenarios como la agregación de servicios, el control de versiones del servicio, el enrutamiento de prioridad y el enrutamiento de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="a0992-104">With the Routing Service, you can create complex routing logic that allows you to implement scenarios such as service aggregation, service versioning, priority routing, and multicast routing.</span></span> <span data-ttu-id="a0992-105">El servicio de enrutamiento también proporciona un control de errores, que le permite preparar listas de puntos de conexión de reserva a los que se envían los mensajes si se produce un error al realizar un envío al punto de conexión de destino principal.</span><span class="sxs-lookup"><span data-stu-id="a0992-105">The Routing Service also provides error handling that allows you to set up lists of backup endpoints, to which messages are sent if a failure occurs when sending to the primary destination endpoint.</span></span>

<span data-ttu-id="a0992-106">Este tema está dirigido a aquellos usuarios que se están iniciando en el servicio de enrutamiento, y cubre la configuración básica y el hospedaje del servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a0992-106">This topic is intended for those new to the Routing Service and covers basic configuration and hosting of the Routing Service.</span></span>

## <a name="configuration"></a><span data-ttu-id="a0992-107">Configuración</span><span class="sxs-lookup"><span data-stu-id="a0992-107">Configuration</span></span>

<span data-ttu-id="a0992-108">El servicio de enrutamiento se implementa como un servicio de WCF que expone uno o varios puntos de conexión de servicio. Estos puntos de conexión reciben mensajes de aplicaciones cliente y los enrutan a uno o más puntos de conexión de destino.</span><span class="sxs-lookup"><span data-stu-id="a0992-108">The Routing Service is implemented as a WCF service that exposes one or more service endpoints that receive messages from client applications and route the messages to one or more destination endpoints.</span></span> <span data-ttu-id="a0992-109">El servicio proporciona <xref:System.ServiceModel.Routing.RoutingBehavior>, que se aplica a los puntos de conexión de servicio que expone el servicio.</span><span class="sxs-lookup"><span data-stu-id="a0992-109">The service provides a <xref:System.ServiceModel.Routing.RoutingBehavior>, which is applied to the service endpoints exposed by the service.</span></span> <span data-ttu-id="a0992-110">Este comportamiento se utiliza para configurar varios aspectos del funcionamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="a0992-110">This behavior is used to configure various aspects of how the service operates.</span></span> <span data-ttu-id="a0992-111">Para facilitar la configuración cuando se usa un archivo de configuración, los parámetros se especifican en **RoutingBehavior**.</span><span class="sxs-lookup"><span data-stu-id="a0992-111">For ease of configuration when using a configuration file, the parameters are specified on the **RoutingBehavior**.</span></span> <span data-ttu-id="a0992-112">En escenarios basados en código, estos parámetros se especifican como parte de un objeto <xref:System.ServiceModel.Routing.RoutingConfiguration>, que se puede pasar a continuación a un **RoutingBehavior**.</span><span class="sxs-lookup"><span data-stu-id="a0992-112">In code-based scenarios, these parameters would be specified as part of a <xref:System.ServiceModel.Routing.RoutingConfiguration> object, which can then be passed to a **RoutingBehavior**.</span></span>

<span data-ttu-id="a0992-113">Al iniciarse, este comportamiento agrega el objeto <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, que se utiliza para realizar el procesamiento de SOAP de mensajes, a los puntos de conexión de cliente.</span><span class="sxs-lookup"><span data-stu-id="a0992-113">When starting, this behavior adds the <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, which is used to perform SOAP processing of messages, to the client endpoints.</span></span> <span data-ttu-id="a0992-114">Esto permite al servicio de enrutamiento transmitir mensajes a los puntos de conexión que requieren un **MessageVersion** diferente que el punto de conexión en el que se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-114">This allows the Routing Service to transmit messages to endpoints that require a different **MessageVersion** than the endpoint the message was received over.</span></span> <span data-ttu-id="a0992-115">**RoutingBehavior** también registra una extensión de servicio, la <xref:System.ServiceModel.Routing.RoutingExtension>, que proporciona un punto de accesibilidad para modificar la configuración del servicio de enrutamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a0992-115">The **RoutingBehavior** also registers a service extension, the <xref:System.ServiceModel.Routing.RoutingExtension>, which provides an accessibility point for modifying the Routing Service configuration at run time.</span></span>

<span data-ttu-id="a0992-116">La clase **RoutingConfiguration** proporciona un medio coherente para configurar y actualizar la configuración del servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a0992-116">The **RoutingConfiguration** class provides a consistent means of configuring and updating the configuration of the Routing Service.</span></span>  <span data-ttu-id="a0992-117">Contiene parámetros que actúan como la configuración para el servicio de enrutamiento y se usa para configurar el **RoutingBehavior** cuando se inicia el servicio o se pasa a **RoutingExtension** para modificar la configuración de enrutamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a0992-117">It contains parameters that act as the settings for the Routing Service and is used to configure the **RoutingBehavior** when the service starts, or is passed to the **RoutingExtension** to modify routing configuration at run time.</span></span>

<span data-ttu-id="a0992-118">La lógica de enrutamiento utilizada para realizar el enrutamiento basado en el contenido de mensajes se define agrupando varios objetos <xref:System.ServiceModel.Dispatcher.MessageFilter> en tablas de filtro (objetos<xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>).</span><span class="sxs-lookup"><span data-stu-id="a0992-118">The routing logic used to perform content-based routing of messages is defined by grouping multiple <xref:System.ServiceModel.Dispatcher.MessageFilter> objects together into filter tables (<xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> objects).</span></span> <span data-ttu-id="a0992-119">Los mensajes entrantes se evalúan con los filtros de mensajes contenidos en la tabla de filtros, y para cada **MessageFilter** que coincida con el mensaje, se reenvía a un extremo de destino.</span><span class="sxs-lookup"><span data-stu-id="a0992-119">Incoming messages are evaluated against the message filters contained in the filter table, and for each **MessageFilter** that matches the message, forwarded to a destination endpoint.</span></span> <span data-ttu-id="a0992-120">La tabla de filtros que se debe usar para enrutar los mensajes se especifica mediante el uso de **RoutingBehavior** en la configuración o a través del código mediante el objeto **RoutingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a0992-120">The filter table that should be used to route messages is specified by using either the **RoutingBehavior** in configuration or through code by using the **RoutingConfiguration** object.</span></span>

### <a name="defining-endpoints"></a><span data-ttu-id="a0992-121">Definición de extremos</span><span class="sxs-lookup"><span data-stu-id="a0992-121">Defining Endpoints</span></span>

<span data-ttu-id="a0992-122">Pese a que pueda parecer que debería iniciar su configuración definiendo la lógica de enrutamiento que va a utilizar, el primer paso sería realmente determinar la forma de los puntos de conexión a los que va a enrutar mensajes.</span><span class="sxs-lookup"><span data-stu-id="a0992-122">While it may seem that you should start your configuration by defining the routing logic you will use, your first step should actually be to determine the shape of the endpoints you will be routing messages to.</span></span> <span data-ttu-id="a0992-123">El servicio de enrutamiento utiliza contratos que definen la forma de los canales utilizados para recibir y enviar mensajes y, por consiguiente, la forma del canal de entrada debe coincidir con la del canal de salida.</span><span class="sxs-lookup"><span data-stu-id="a0992-123">The Routing Service uses contracts that define the shape of the channels used to receive and send messages, and therefore the shape of the input channel must match that of the output channel.</span></span>  <span data-ttu-id="a0992-124">Por ejemplo, si va a enrutar mensajes a puntos de conexión que utilizan la forma de canal "solicitud-respuesta", entonces debe utilizar un contrato compatible en los puntos de conexión entrantes, como <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span><span class="sxs-lookup"><span data-stu-id="a0992-124">For example, if you are routing to endpoints that use the request-reply channel shape, then you must use a compatible contract on the inbound endpoints, such as the <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span></span>

<span data-ttu-id="a0992-125">Esto significa que, si sus extremos de destino utilizan contratos con varios patrones de comunicación (como la combinación de operaciones unidireccionales y bidireccionales), no puede crear ningún extremo de servicio único que pueda recibir y enrutar mensajes a todos ellos.</span><span class="sxs-lookup"><span data-stu-id="a0992-125">This means that if your destination endpoints use contracts with multiple communication patterns (such as mixing one-way and two-way operations,) you cannot create a single service endpoint that can receive and route messages to all of them.</span></span> <span data-ttu-id="a0992-126">Debe determinar qué puntos de conexión tienen formas compatibles y definir uno o varios puntos de conexión de servicio para recibir los mensajes que se van a enrutar a los puntos de conexión de destino.</span><span class="sxs-lookup"><span data-stu-id="a0992-126">You must determine which endpoints have compatible shapes and define one or more service endpoints that will be used to receive messages to be routed to the destination endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="a0992-127">Al trabajar con contratos que especifican varios patrones de comunicación (como una combinación de operaciones unidireccionales y bidireccionales), una solución alternativa sería usar un contrato dúplex en el servicio de enrutamiento, como <xref:System.ServiceModel.Routing.IDuplexSessionRouter>.</span><span class="sxs-lookup"><span data-stu-id="a0992-127">When working with contracts that specify multiple communication patterns (such as a mix of one-way and two-way operations,) a workaround is to use a duplex contract at the Routing Service such as <xref:System.ServiceModel.Routing.IDuplexSessionRouter>.</span></span> <span data-ttu-id="a0992-128">Sin embargo, esto implica que el enlace debe ser capaz de realizar una comunicación dúplex, algo que puede no ser posible en todos los escenarios.</span><span class="sxs-lookup"><span data-stu-id="a0992-128">However this means that the binding must be capable of duplex communication, which may not be possible for all scenarios.</span></span> <span data-ttu-id="a0992-129">En escenarios en los que esto no sea posible, puede ser necesario dividir la comunicación en varios puntos de conexión o modificar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a0992-129">In scenarios where this is not possible, factoring the communication into multiple endpoints or modifying the application may be necessary.</span></span>

<span data-ttu-id="a0992-130">Para obtener más información sobre los contratos de enrutamiento, consulte [enrutamiento de contratos](routing-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="a0992-130">For more information about routing contracts, see [Routing Contracts](routing-contracts.md).</span></span>

<span data-ttu-id="a0992-131">Una vez definido el punto de conexión de servicio, puede usar **RoutingBehavior** para asociar un **RoutingConfiguration** específico con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a0992-131">After the service endpoint is defined, you can use the **RoutingBehavior** to associate a specific **RoutingConfiguration** with the endpoint.</span></span> <span data-ttu-id="a0992-132">Al configurar el servicio de enrutamiento mediante un archivo de configuración, **RoutingBehavior** se utiliza para especificar la tabla de filtros que contiene la lógica de enrutamiento utilizada para procesar los mensajes recibidos en este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a0992-132">When configuring the Routing Service by using a configuration file, the **RoutingBehavior** is used to specify the filter table that contains the routing logic used to process messages received on this endpoint.</span></span> <span data-ttu-id="a0992-133">Si va a configurar el servicio de enrutamiento mediante programación, puede especificar la tabla de filtros mediante **RoutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a0992-133">If you are configuring the Routing Service programmatically you can specify the filter table by using the **RoutingConfiguration**.</span></span>

<span data-ttu-id="a0992-134">En el siguiente ejemplo, se definen los puntos de conexión de cliente y servicio que usa el servicio de enrutamiento tanto mediante programación como por medio de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a0992-134">The following example defines the service and client endpoints that are used by the Routing Service both programmatically and by using a configuration file.</span></span>

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

<span data-ttu-id="a0992-135">En este ejemplo se configura el servicio de enrutamiento para exponer un punto de conexión único con una dirección de `http://localhost:8000/routingservice/router`, que se usa para recibir los mensajes que se van a enrutar.</span><span class="sxs-lookup"><span data-stu-id="a0992-135">This example configures the Routing Service to expose a single endpoint with an address of `http://localhost:8000/routingservice/router`, which is used to receive messages to be routed.</span></span> <span data-ttu-id="a0992-136">Dado que los mensajes se enrutan a puntos de conexión solicitud-respuesta, el punto de conexión de servicio utiliza el contrato <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span><span class="sxs-lookup"><span data-stu-id="a0992-136">Because the messages are routed to request-reply endpoints, the service endpoint uses the <xref:System.ServiceModel.Routing.IRequestReplyRouter> contract.</span></span> <span data-ttu-id="a0992-137">Esta configuración también define un punto de conexión de cliente único de `http://localhost:8000/servicemodelsample/service` a la que se enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a0992-137">This configuration also defines a single client endpoint of `http://localhost:8000/servicemodelsample/service` that messages are routed to.</span></span> <span data-ttu-id="a0992-138">La tabla de filtros (no se muestra) denominada "routingTable1" contiene la lógica de enrutamiento que se usa para enrutar los mensajes y está asociada al punto de conexión de servicio mediante **RoutingBehavior** (para un archivo de configuración) o **RoutingConfiguration** (para la configuración mediante programación).</span><span class="sxs-lookup"><span data-stu-id="a0992-138">The filter table (not shown) named "routingTable1" contains the routing logic used to route messages, and is associated with the service endpoint by using the **RoutingBehavior** (for a configuration file) or **RoutingConfiguration** (for programmatic configuration).</span></span>

### <a name="routing-logic"></a><span data-ttu-id="a0992-139">Lógica de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="a0992-139">Routing Logic</span></span>

<span data-ttu-id="a0992-140">Para definir la lógica de enrutamiento utilizada para enrutar los mensajes, debe determinar sobre qué datos se puede actuar de entre los contenidos dentro de los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="a0992-140">To define the routing logic used to route messages, you must determine what data contained within the incoming messages can be uniquely acted upon.</span></span> <span data-ttu-id="a0992-141">Por ejemplo, si todos los extremos de destino a los que va a enrutar mensajes comparten las mismas acciones SOAP, el valor de la acción SOAP incluida dentro del mensaje no es un buen indicador de a qué extremo concreto se debe enrutar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-141">For example, if all the destination endpoints you are routing to share the same SOAP Actions, the value of the Action contained within the message is not a good indicator of which specific endpoint the message should be routed to.</span></span> <span data-ttu-id="a0992-142">Si debe enrutar los mensajes únicamente a un punto de conexión concreto, debe filtrar según los datos que identifiquen exclusivamente el punto de conexión de destino al que se enruta el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-142">If you must uniquely route messages to one specific endpoint, you should filter upon data that uniquely identifies the destination endpoint that the message is routed to.</span></span>

<span data-ttu-id="a0992-143">El servicio de enrutamiento proporciona varias implementaciones de **MessageFilter** que inspeccionan valores específicos del mensaje, como la dirección, la acción, el nombre del punto de conexión o incluso una consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="a0992-143">The Routing Service provides several **MessageFilter** implementations that inspect specific values within the message, such as the address, action, endpoint name, or even an XPath query.</span></span> <span data-ttu-id="a0992-144">Si ninguna de estas implementaciones satisface sus necesidades, puede crear una implementación de **MessageFilter** personalizada.</span><span class="sxs-lookup"><span data-stu-id="a0992-144">If none of these implementations meet your needs you can create a custom **MessageFilter** implementation.</span></span> <span data-ttu-id="a0992-145">Para obtener más información sobre los filtros de mensajes y una comparación de las implementaciones utilizadas por el servicio de enrutamiento, vea [filtros de mensajes](message-filters.md) y [elegir un filtro](choosing-a-filter.md).</span><span class="sxs-lookup"><span data-stu-id="a0992-145">For more information about message filters and a comparison of the implementations used by the Routing Service, see [Message Filters](message-filters.md) and [Choosing a Filter](choosing-a-filter.md).</span></span>

<span data-ttu-id="a0992-146">Varios filtros de mensajes se organizan juntos en tablas de filtros, que asocian cada **MessageFilter** a un extremo de destino.</span><span class="sxs-lookup"><span data-stu-id="a0992-146">Multiple message filters are organized together into filter tables, which associate each **MessageFilter** with a destination endpoint.</span></span> <span data-ttu-id="a0992-147">Opcionalmente, la tabla de filtros también se puede utilizar para especificar una lista de extremos de reserva a los que el servicio de enrutamiento intentará enviar el mensaje en caso de que se produzca un error de transmisión.</span><span class="sxs-lookup"><span data-stu-id="a0992-147">Optionally, the filter table can also be used to specify a list of back-up endpoints that the Routing Service will attempt to send the message to in the event of a transmission failure.</span></span>

<span data-ttu-id="a0992-148">De forma predeterminada, todos los filtros de mensajes de una tabla de filtros se evalúan simultáneamente; sin embargo, puede especificar <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A> para que la evaluación de los filtros se efectúe en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="a0992-148">By default all message filters within a filter table are evaluated simultaneously; however, you can specify a <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A> that causes the message filters to be evaluated in a specific order.</span></span> <span data-ttu-id="a0992-149">Primero se evalúan todas las entradas de mayor prioridad y los filtros de mensaje de menor prioridad no se evalúan si se detecta una coincidencia en un nivel de prioridad más alto.</span><span class="sxs-lookup"><span data-stu-id="a0992-149">All entries with the highest priority are evaluated first, and message filters of lower priorities are not evaluated if a match is found at a higher priority level.</span></span> <span data-ttu-id="a0992-150">Para obtener más información acerca de las tablas de filtros, vea [filtros de mensajes](message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="a0992-150">For more information about filter tables, see [Message Filters](message-filters.md).</span></span>

<span data-ttu-id="a0992-151">En los siguientes ejemplos, se utiliza <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, que evalúa todos los mensajes como `true`.</span><span class="sxs-lookup"><span data-stu-id="a0992-151">The following examples use the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, which evaluates to `true` for all messages.</span></span> <span data-ttu-id="a0992-152">Este **MessageFilter** se agrega a la tabla de filtros "routingTable1", que asocia **MessageFilter** con el punto de conexión de cliente denominado "CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="a0992-152">This **MessageFilter** is added to the "routingTable1" filter table, which associates the **MessageFilter** with the client endpoint named "CalculatorService".</span></span> <span data-ttu-id="a0992-153">A continuación, **RoutingBehavior** especifica que esta tabla se debe utilizar para enrutar los mensajes procesados por el punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="a0992-153">The **RoutingBehavior** then specifies that this table should be used to route messages processed by the service endpoint.</span></span>

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
> <span data-ttu-id="a0992-154">De forma predeterminada, el servicio de enrutamiento solo evalúa los encabezados del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-154">By default, the Routing Service only evaluates the headers of the message.</span></span> <span data-ttu-id="a0992-155">Para permitir a los filtros tener acceso al cuerpo del mensaje, debe establecer <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="a0992-155">To allow the filters to access the message body, you must set <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> to `false`.</span></span>

<span data-ttu-id="a0992-156">**Multidifusión**</span><span class="sxs-lookup"><span data-stu-id="a0992-156">**Multicast**</span></span>

<span data-ttu-id="a0992-157">Aunque muchas configuraciones del servicio de enrutamiento utilizan una lógica de filtros exclusiva que enruta los mensajes solo a un punto de conexión específico, puede que tenga que enrutar un mensaje determinado a varios puntos de conexión de destino.</span><span class="sxs-lookup"><span data-stu-id="a0992-157">While many Routing Service configurations use exclusive filter logic that routes messages to only one specific endpoint, you may need to route a given message to multiple destination endpoints.</span></span> <span data-ttu-id="a0992-158">Para difundir un mensaje a varios destinos, deben cumplirse las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="a0992-158">To multicast a message to multiple destinations, the following conditions must be true:</span></span>

- <span data-ttu-id="a0992-159">La forma del canal no puede ser de "solicitud-respuesta" (aunque sí unidireccional o dúplex), porque la aplicación cliente solo puede recibir una respuesta para cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="a0992-159">The channel shape must not be request-reply (though may be one-way or duplex,) because only one reply can be received by the client application in response to the request.</span></span>

- <span data-ttu-id="a0992-160">Varios filtros deben devolver `true` al evaluar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-160">Multiple filters must return `true` when evaluating the message.</span></span>

<span data-ttu-id="a0992-161">Si se cumplen estas condiciones, el mensaje se enruta a todos los puntos de conexión de todos los filtros que se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="a0992-161">If these conditions are met, the message is routed to all endpoints of all filters that evaluate to `true`.</span></span> <span data-ttu-id="a0992-162">En el ejemplo siguiente se define una configuración de enrutamiento que hace que los mensajes se enruten a ambos puntos de conexión si la dirección del punto de conexión en el mensaje se `http://localhost:8000/routingservice/router/rounding`.</span><span class="sxs-lookup"><span data-stu-id="a0992-162">The following example defines a routing configuration that results in messages being routed to both endpoints if the endpoint address in the message is `http://localhost:8000/routingservice/router/rounding`.</span></span>

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

### <a name="soap-processing"></a><span data-ttu-id="a0992-163">Procesamiento de SOAP</span><span class="sxs-lookup"><span data-stu-id="a0992-163">SOAP Processing</span></span>

<span data-ttu-id="a0992-164">Para admitir el enrutamiento de mensajes entre protocolos distintos, **RoutingBehavior** agrega de forma predeterminada el <xref:System.ServiceModel.Routing.SoapProcessingBehavior> a todos los extremos de cliente a los que se enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a0992-164">To support the routing of messages between dissimilar protocols, the **RoutingBehavior** by default adds the <xref:System.ServiceModel.Routing.SoapProcessingBehavior> to all client endpoint(s) that messages are routed to.</span></span> <span data-ttu-id="a0992-165">Este comportamiento crea automáticamente un nuevo **messageversion** antes de enrutar el mensaje al punto de conexión, así como la creación de un **messageversion** compatible para cualquier documento de respuesta antes de devolverlo a la aplicación cliente que lo solicita.</span><span class="sxs-lookup"><span data-stu-id="a0992-165">This behavior automatically creates a new **MessageVersion** before routing the message to the endpoint, as well as creating a compatible **MessageVersion** for any response document before returning it to the requesting client application.</span></span>

<span data-ttu-id="a0992-166">Los pasos que se llevan a cabo para crear un nuevo **MessageVersion** para el mensaje de salida son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="a0992-166">The steps taken to create a new **MessageVersion** for the outbound message are as follows:</span></span>

<span data-ttu-id="a0992-167">**Procesamiento de solicitudes**</span><span class="sxs-lookup"><span data-stu-id="a0992-167">**Request processing**</span></span>

- <span data-ttu-id="a0992-168">Obtiene el **MessageVersion** del enlace o canal de salida.</span><span class="sxs-lookup"><span data-stu-id="a0992-168">Get the **MessageVersion** of the outbound binding/channel.</span></span>

- <span data-ttu-id="a0992-169">Obtenga el lector del cuerpo del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="a0992-169">Get the body reader for the original message.</span></span>

- <span data-ttu-id="a0992-170">Cree un nuevo mensaje con la misma acción, el lector del cuerpo y un nuevo **MessageVersion**.</span><span class="sxs-lookup"><span data-stu-id="a0992-170">Create a new message with the same action, body reader, and a new **MessageVersion**.</span></span>

- <span data-ttu-id="a0992-171">Si <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Addressing. None**, copie los encabezados to, from, FaultTo y latest en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-171">If <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> != **Addressing.None**, copy the To, From, FaultTo, and RelatesTo headers to the new message.</span></span>

- <span data-ttu-id="a0992-172">Copie todas las propiedades del mensaje en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-172">Copy all message properties to the new message.</span></span>

- <span data-ttu-id="a0992-173">Almacene el mensaje de solicitud original para utilizarlo al procesar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="a0992-173">Store the original request message to use when processing the response.</span></span>

- <span data-ttu-id="a0992-174">Devuelva el nuevo mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="a0992-174">Return the new request message.</span></span>

<span data-ttu-id="a0992-175">**Procesamiento de respuestas**</span><span class="sxs-lookup"><span data-stu-id="a0992-175">**Response processing**</span></span>

- <span data-ttu-id="a0992-176">Obtiene **MessageVersion** del mensaje de solicitud original.</span><span class="sxs-lookup"><span data-stu-id="a0992-176">Get the **MessageVersion** of the original request message.</span></span>

- <span data-ttu-id="a0992-177">Obtenga el lector del cuerpo del mensaje de respuesta recibido.</span><span class="sxs-lookup"><span data-stu-id="a0992-177">Get the body reader for the received response message.</span></span>

- <span data-ttu-id="a0992-178">Cree un nuevo mensaje de respuesta con la misma acción, el lector del cuerpo y el **MessageVersion** del mensaje de solicitud original.</span><span class="sxs-lookup"><span data-stu-id="a0992-178">Create a new response message with the same action, body reader, and the **MessageVersion** of the original request message.</span></span>

- <span data-ttu-id="a0992-179">Si <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Addressing. None**, copie los encabezados to, from, FaultTo y latest en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-179">If <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> != **Addressing.None**, copy the To, From, FaultTo, and RelatesTo headers to the new message.</span></span>

- <span data-ttu-id="a0992-180">Copie las propiedades del mensaje en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-180">Copy the message properties to the new message.</span></span>

- <span data-ttu-id="a0992-181">Devuelva el nuevo mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a0992-181">Return the new response message.</span></span>

<span data-ttu-id="a0992-182">De forma predeterminada, el **SoapProcessingBehavior** se agrega automáticamente a los extremos de cliente por el <xref:System.ServiceModel.Routing.RoutingBehavior> cuando se inicia el servicio; sin embargo, puede controlar si el procesamiento de SOAP se agrega a todos los extremos de cliente mediante la propiedad <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="a0992-182">By default, the **SoapProcessingBehavior** is automatically added to the client endpoints by the <xref:System.ServiceModel.Routing.RoutingBehavior> when the service starts; however, you can control whether SOAP processing is added to all client endpoints by using the <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A> property.</span></span> <span data-ttu-id="a0992-183">También puede agregar el comportamiento directamente a un punto de conexión específico, y habilitar o deshabilitar este comportamiento en los puntos de conexión si se requiere un control de procesamiento de SOAP más granular.</span><span class="sxs-lookup"><span data-stu-id="a0992-183">You can also add the behavior directly to a specific endpoint and enable or disable this behavior at the endpoint level if a more granular control of SOAP processing is required.</span></span>

> [!NOTE]
> <span data-ttu-id="a0992-184">Si el procesamiento de SOAP está deshabilitado para un extremo que requiere un valor MessageVersion diferente al del mensaje de solicitud original, debe proporcionar un mecanismo personalizado para que realice todas las modificaciones de SOAP que sean necesarias antes de enviar el mensaje al extremo de destino.</span><span class="sxs-lookup"><span data-stu-id="a0992-184">If SOAP processing is disabled for an endpoint that requires a different MessageVersion than that of the original request message, you must provide a custom mechanism for performing any SOAP modifications that are required before sending the message to the destination endpoint.</span></span>

<span data-ttu-id="a0992-185">En los ejemplos siguientes, se usa la propiedad **soapProcessingEnabled** para evitar que **SoapProcessingBehavior** se agregue automáticamente a todos los extremos de cliente.</span><span class="sxs-lookup"><span data-stu-id="a0992-185">In the following examples, the **soapProcessingEnabled** property is used to prevent the **SoapProcessingBehavior** from being automatically added to all client endpoints.</span></span>

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

### <a name="dynamic-configuration"></a><span data-ttu-id="a0992-186">configuración dinámica</span><span class="sxs-lookup"><span data-stu-id="a0992-186">Dynamic Configuration</span></span>

<span data-ttu-id="a0992-187">Al agregar puntos de conexión de cliente adicionales, o bien cuando necesite modificar los filtros que se utilizan para enrutar los mensajes, debe encontrar una forma de actualizar dinámicamente la configuración en tiempo de ejecución para evitar la interrupción del servicio en los puntos de conexión que estén recibiendo mensajes a través del servicio de enrutamiento en ese momento.</span><span class="sxs-lookup"><span data-stu-id="a0992-187">When you add additional client endpoints, or need to modify the filters that are used to route messages, you must have a way to update the configuration dynamically at run time to prevent interrupting the service to the endpoints currently receiving messages through the Routing Service.</span></span> <span data-ttu-id="a0992-188">Modificar un archivo de configuración o el código de la aplicación host no siempre es suficiente, porque todos los métodos necesitan que se recicle la aplicación y esto conduciría a la pérdida potencial de todos los mensajes que estuvieran en tránsito en ese momento, así como a un posible tiempo de inactividad mientras se aguarda al reinicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="a0992-188">Modifying a configuration file or the code of the host application is not always sufficient, because either method requires recycling the application, which would lead to the potential loss of any messages currently in transit and the potential for downtime while waiting on the service to restart.</span></span>

<span data-ttu-id="a0992-189">Solo puede modificar el **RoutingConfiguration** mediante programación.</span><span class="sxs-lookup"><span data-stu-id="a0992-189">You can only modify the **RoutingConfiguration** programmatically.</span></span> <span data-ttu-id="a0992-190">Aunque puede configurar inicialmente el servicio mediante un archivo de configuración, solo puede modificar la configuración en tiempo de ejecución si crea un nuevo **RoutingConfiguration** y lo pasa como parámetro al método <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> expuesto por la extensión de servicio <xref:System.ServiceModel.Routing.RoutingExtension>.</span><span class="sxs-lookup"><span data-stu-id="a0992-190">While you can initially configure the service by using a configuration file, you can only modify the configuration at run time by constructing a new **RoutingConfiguration** and passing it as a parameter to the <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> method exposed by the <xref:System.ServiceModel.Routing.RoutingExtension> service extension.</span></span> <span data-ttu-id="a0992-191">Los mensajes que se encuentran actualmente en tránsito continúan siendo enrutados con la configuración anterior, mientras que los mensajes recibidos después de la llamada a **ApplyConfiguration** usan la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="a0992-191">Any messages currently in transit continue to be routed using the previous configuration, while messages received after the call to **ApplyConfiguration** use the new configuration.</span></span> <span data-ttu-id="a0992-192">En el siguiente ejemplo, se muestra cómo crear una instancia del servicio de enrutamiento y cómo modificar después la configuración.</span><span class="sxs-lookup"><span data-stu-id="a0992-192">The following example demonstrates creating an instance of the Routing Service and then subsequently modifying the configuration.</span></span>

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
> <span data-ttu-id="a0992-193">Al actualizar el servicio de enrutamiento de esta manera, solo es posible pasar una nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="a0992-193">When updating the Routing Service in this manner it is only possible to pass a new configuration.</span></span> <span data-ttu-id="a0992-194">No se puede modificar únicamente elementos determinados de la configuración actual o anexar nuevas entradas a la configuración actual. Debe crear y pasar una nueva configuración que reemplace la existente.</span><span class="sxs-lookup"><span data-stu-id="a0992-194">It is not possible to modify only select elements of the current configuration or append new entries to the current configuration; you must create and pass a new configuration that replaces the existing one.</span></span>

> [!NOTE]
> <span data-ttu-id="a0992-195">Todas las sesiones que se abrieron con la configuración anterior seguirán utilizándola.</span><span class="sxs-lookup"><span data-stu-id="a0992-195">Any sessions opened using the previous configuration continue using the previous configuration.</span></span> <span data-ttu-id="a0992-196">Sólo las nuevas sesiones usarán la configuración nueva.</span><span class="sxs-lookup"><span data-stu-id="a0992-196">The new configuration is only used by new sessions.</span></span>

## <a name="error-handling"></a><span data-ttu-id="a0992-197">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="a0992-197">Error Handling</span></span>

<span data-ttu-id="a0992-198">Si se encuentra algún valor <xref:System.ServiceModel.CommunicationException> al intentar enviar un mensaje, tiene lugar el control de errores.</span><span class="sxs-lookup"><span data-stu-id="a0992-198">If any <xref:System.ServiceModel.CommunicationException> is encountered while attempting to send a message, error handling take place.</span></span> <span data-ttu-id="a0992-199">Estas excepciones indican normalmente que se encontró un problema al intentar establecer comunicación con el extremo de cliente definido, como <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> o <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span><span class="sxs-lookup"><span data-stu-id="a0992-199">These exceptions typically indicate that a problem was encountered while attempting to communicate with the defined client endpoint, such as an <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException>, or <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span></span> <span data-ttu-id="a0992-200">El código de control de errores también detectará e intentará volver a realizar el envío cuando se produzca una <xref:System.TimeoutException>, que es otra excepción común que no se deriva de **CommunicationException**.</span><span class="sxs-lookup"><span data-stu-id="a0992-200">The error handling-code will also catch and attempt to retry sending when a <xref:System.TimeoutException> occurs, which is another common exception that is not derived from **CommunicationException**.</span></span>

<span data-ttu-id="a0992-201">Cuando se produce una de las excepciones anteriores, el servicio de enrutamiento no puede establecer comunicación con una lista de puntos de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-201">When one of the preceding exceptions occurs, the Routing Service fails over to a list of backup endpoints.</span></span> <span data-ttu-id="a0992-202">Si se produce un error de comunicación en todos los puntos de conexión de reserva, o bien si un punto de conexión devuelve una excepción que indica un error dentro del servicio de destino, el servicio de enrutamiento devuelve un error a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="a0992-202">If all backup endpoints fail with a communications failure, or if an endpoint returns an exception that indicates a failure within the destination service, the Routing Service returns a fault to the client application.</span></span>

> [!NOTE]
> <span data-ttu-id="a0992-203">La funcionalidad del control de errores captura y administra excepciones que se producen al intentar enviar un mensaje y al intentar cerrar un canal.</span><span class="sxs-lookup"><span data-stu-id="a0992-203">The error-handling functionality captures and handles exceptions that occur when attempting to send a message and when attempting to close a channel.</span></span> <span data-ttu-id="a0992-204">El código de control de errores no está diseñado para detectar o administrar excepciones creadas por los puntos de conexión de la aplicación con los que se comunica; un <xref:System.ServiceModel.FaultException> producido por un servicio aparece en el servicio de enrutamiento como **FaultMessage** y se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="a0992-204">The error-handling code is not intended to detect or handle exceptions created by the application endpoints it is communicating with; a <xref:System.ServiceModel.FaultException> thrown by a service appears at the Routing Service as a **FaultMessage** and is flowed back to the client.</span></span>
>
> <span data-ttu-id="a0992-205">Si se produce un error cuando el servicio de enrutamiento intenta retransmitir un mensaje, puede obtener un objeto <xref:System.ServiceModel.FaultException> en el lado cliente, en lugar del <xref:System.ServiceModel.EndpointNotFoundException> que obtendría normalmente en ausencia del servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a0992-205">If an error occurs when the routing service tries to relay a message, you may  get a <xref:System.ServiceModel.FaultException> on the client side, rather than a <xref:System.ServiceModel.EndpointNotFoundException> you would normally get in the absence of the routing service.</span></span> <span data-ttu-id="a0992-206">Un servicio de enrutamiento puede por tanto enmascarar las excepciones y no proporcionar una transparencia completa a menos que se examinen las excepciones anidadas.</span><span class="sxs-lookup"><span data-stu-id="a0992-206">A routing service may thus mask exceptions and not provide full transparency unless you examine nested exceptions.</span></span>

### <a name="tracing-exceptions"></a><span data-ttu-id="a0992-207">Traza de excepciones</span><span class="sxs-lookup"><span data-stu-id="a0992-207">Tracing Exceptions</span></span>

<span data-ttu-id="a0992-208">Cuando se produce un error al enviar un mensaje a un punto de conexión en una lista, el servicio de enrutamiento realiza un seguimiento de los datos de excepción resultantes y adjunta los detalles de la excepción como una propiedad de mensaje denominada **Exceptions**.</span><span class="sxs-lookup"><span data-stu-id="a0992-208">When sending a message to an endpoint in a list fails, the Routing Service traces the resulting exception data and attaches the exception details as a message property named **Exceptions**.</span></span> <span data-ttu-id="a0992-209">Esto conserva los datos de la excepción y permite al usuario tener acceso mediante programación a través de un inspector del mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-209">This preserves the exception data and allows a user programmatic access through a message inspector.</span></span>  <span data-ttu-id="a0992-210">Los datos de la excepción se almacenan por mensaje en un diccionario que asigna el nombre del punto de conexión a los detalles de la excepción producidos al intentar enviarle un mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-210">The exception data is stored per message in a dictionary that maps the endpoint name to the exception details encountered when trying to send a message to it.</span></span>

### <a name="backup-endpoints"></a><span data-ttu-id="a0992-211">puntos de conexión de reserva</span><span class="sxs-lookup"><span data-stu-id="a0992-211">Backup Endpoints</span></span>

<span data-ttu-id="a0992-212">Las entradas de la tabla de filtros pueden especificar también una lista de puntos de conexión de reserva que se utilizarán cuando se produzcan errores de transmisión al enviar mensajes al punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="a0992-212">Each filter entry within the filter table can optionally specify a list of backup endpoints, which are used in the event of a transmission failure when sending to the primary endpoint.</span></span> <span data-ttu-id="a0992-213">Si se produce este tipo de error, el servicio de enrutamiento intenta transmitir el mensaje a la primera entrada de la lista de extremos de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-213">If such a failure occurs, the Routing Service attempts to transmit the message to the first entry in the backup endpoint list.</span></span> <span data-ttu-id="a0992-214">Si este intento resulta fallido también, se prueba con el punto de conexión de reserva siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="a0992-214">If this send attempt also encounters a transmission failure, the next endpoint in the backup list is tried.</span></span> <span data-ttu-id="a0992-215">El servicio de enrutamiento sigue enviando el mensaje a cada uno de los extremos de la lista hasta que el mensaje se recibe correctamente, todos los extremos devuelven un error de transmisión o se produce un error distinto en el extremo.</span><span class="sxs-lookup"><span data-stu-id="a0992-215">The Routing Service continues sending the message to each endpoint in the list until the message is successfully received, all endpoints return a transmission failure, or a non-transmission failure is returned by an endpoint.</span></span>

<span data-ttu-id="a0992-216">En los siguientes ejemplos, se configura el servicio de enrutamiento para que utilice una lista de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-216">The following examples configure the Routing Service to use a backup list.</span></span>

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

### <a name="supported-error-patterns"></a><span data-ttu-id="a0992-217">Patrones de error admitidos</span><span class="sxs-lookup"><span data-stu-id="a0992-217">Supported Error Patterns</span></span>

<span data-ttu-id="a0992-218">En la siguiente tabla, se describen los patrones que son compatibles con el uso de listas de puntos de conexión de reserva, junto con notas en las que se describen los detalles del control de errores de patrones específicos.</span><span class="sxs-lookup"><span data-stu-id="a0992-218">The following table describes the patterns that are compatible with the use of backup endpoint lists, along with notes describing the details of error handling for specific patterns.</span></span>

|<span data-ttu-id="a0992-219">Patrón</span><span class="sxs-lookup"><span data-stu-id="a0992-219">Pattern</span></span>|<span data-ttu-id="a0992-220">Sesión</span><span class="sxs-lookup"><span data-stu-id="a0992-220">Session</span></span>|<span data-ttu-id="a0992-221">Transacción</span><span class="sxs-lookup"><span data-stu-id="a0992-221">Transaction</span></span>|<span data-ttu-id="a0992-222">Contexto de recepción</span><span class="sxs-lookup"><span data-stu-id="a0992-222">Receive Context</span></span>|<span data-ttu-id="a0992-223">Lista de reserva admitida</span><span class="sxs-lookup"><span data-stu-id="a0992-223">Backup List Supported</span></span>|<span data-ttu-id="a0992-224">Notas</span><span class="sxs-lookup"><span data-stu-id="a0992-224">Notes</span></span>|
|-------------|-------------|-----------------|---------------------|---------------------------|-----------|
|<span data-ttu-id="a0992-225">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-225">One-Way</span></span>||||<span data-ttu-id="a0992-226">Sí</span><span class="sxs-lookup"><span data-stu-id="a0992-226">Yes</span></span>|<span data-ttu-id="a0992-227">Intenta reenviar el mensaje a un punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-227">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="a0992-228">Si este mensaje se envía por multidifusión, solo el mensaje del canal fallido se mueve a su destino de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-228">If this message is being multicast, only the message on the failed channel is moved to its backup destination.</span></span>|
|<span data-ttu-id="a0992-229">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-229">One-Way</span></span>||<span data-ttu-id="a0992-230">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-230">✔️</span></span>||<span data-ttu-id="a0992-231">No</span><span class="sxs-lookup"><span data-stu-id="a0992-231">No</span></span>|<span data-ttu-id="a0992-232">Se lanza una excepción y se deshace la transacción.</span><span class="sxs-lookup"><span data-stu-id="a0992-232">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="a0992-233">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-233">One-Way</span></span>|||<span data-ttu-id="a0992-234">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-234">✔️</span></span>|<span data-ttu-id="a0992-235">Sí</span><span class="sxs-lookup"><span data-stu-id="a0992-235">Yes</span></span>|<span data-ttu-id="a0992-236">Intenta reenviar el mensaje a un punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-236">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="a0992-237">Una vez recibido correctamente el mensaje, rellene todos los contextos de recepción.</span><span class="sxs-lookup"><span data-stu-id="a0992-237">After the message is successfully received, complete all receive contexts.</span></span> <span data-ttu-id="a0992-238">Si ninguno de los extremos recibe correctamente el mensaje, no rellene el contexto de recepción.</span><span class="sxs-lookup"><span data-stu-id="a0992-238">If the message is not successfully received by any endpoint, do not complete the receive context.</span></span><br /><br /> <span data-ttu-id="a0992-239">Cuando este mensaje se envía por multidifusión, el contexto de recepción solo se rellena si al menos un punto de conexión (principal o de reserva) recibe correctamente el mensaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-239">When this message is being multicast, the receive context is only completed if the message is successfully received by at least one endpoint (primary or backup).</span></span> <span data-ttu-id="a0992-240">Si ninguno de los puntos de conexión de las rutas de acceso de multidifusión recibe el mensaje correctamente, no rellene el contexto de recepción.</span><span class="sxs-lookup"><span data-stu-id="a0992-240">If none of the endpoints in any of the multicast paths successfully receive the message, do not complete the receive context.</span></span>|
|<span data-ttu-id="a0992-241">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-241">One-Way</span></span>||<span data-ttu-id="a0992-242">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-242">✔️</span></span>|<span data-ttu-id="a0992-243">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-243">✔️</span></span>|<span data-ttu-id="a0992-244">Sí</span><span class="sxs-lookup"><span data-stu-id="a0992-244">Yes</span></span>|<span data-ttu-id="a0992-245">Anule la transacción anterior, cree una transacción nueva y reenvíe todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a0992-245">Abort the previous transaction, create a new transaction, and resend all messages.</span></span> <span data-ttu-id="a0992-246">Los mensajes que detectaron un error se transmiten a un destino de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a0992-246">Messages that encountered an error are transmitted to a backup destination.</span></span><br /><br /> <span data-ttu-id="a0992-247">Una vez creada una transacción que realiza correctamente todas las transmisiones, rellene los contextos de recepción y confirme la transacción.</span><span class="sxs-lookup"><span data-stu-id="a0992-247">After a transaction has been created in which all transmissions succeed, complete the receive contexts and commit the transaction.</span></span>|
|<span data-ttu-id="a0992-248">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-248">One-Way</span></span>|<span data-ttu-id="a0992-249">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-249">✔️</span></span>|||<span data-ttu-id="a0992-250">Sí</span><span class="sxs-lookup"><span data-stu-id="a0992-250">Yes</span></span>|<span data-ttu-id="a0992-251">Intenta reenviar el mensaje a un punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-251">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="a0992-252">En un escenario de multidifusión solo se reenvían a destinos de reserva los mensajes de sesiones en las que se produjo un error o que no pudieron cerrarse.</span><span class="sxs-lookup"><span data-stu-id="a0992-252">In a multicast scenario only the messages in a session that encountered an error or in a session whose session close failed are resent to backup destinations.</span></span>|
|<span data-ttu-id="a0992-253">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-253">One-Way</span></span>|<span data-ttu-id="a0992-254">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-254">✔️</span></span>|<span data-ttu-id="a0992-255">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-255">✔️</span></span>||<span data-ttu-id="a0992-256">No</span><span class="sxs-lookup"><span data-stu-id="a0992-256">No</span></span>|<span data-ttu-id="a0992-257">Se lanza una excepción y se deshace la transacción.</span><span class="sxs-lookup"><span data-stu-id="a0992-257">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="a0992-258">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-258">One-Way</span></span>|<span data-ttu-id="a0992-259">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-259">✔️</span></span>||<span data-ttu-id="a0992-260">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-260">✔️</span></span>|<span data-ttu-id="a0992-261">Sí</span><span class="sxs-lookup"><span data-stu-id="a0992-261">Yes</span></span>|<span data-ttu-id="a0992-262">Intenta reenviar el mensaje a un punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-262">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="a0992-263">Una vez que todos los envíos de mensaje se realizan correctamente, la sesión indica que no hay más mensajes y el servicio de enrutamiento cierra todos los canales de sesión salientes, se rellenan todos los contextos de recepción y se cierra el canal de sesión entrante.</span><span class="sxs-lookup"><span data-stu-id="a0992-263">After all message sends complete without error, the session indicates no more messages and the Routing Service successfully closes all outbound session channel(s), all receive contexts are completed, and the inbound session channel is closed.</span></span>|
|<span data-ttu-id="a0992-264">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-264">One-Way</span></span>|<span data-ttu-id="a0992-265">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-265">✔️</span></span>|<span data-ttu-id="a0992-266">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-266">✔️</span></span>|<span data-ttu-id="a0992-267">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-267">✔️</span></span>|<span data-ttu-id="a0992-268">Sí</span><span class="sxs-lookup"><span data-stu-id="a0992-268">Yes</span></span>|<span data-ttu-id="a0992-269">Anule la transacción actual y cree una nueva.</span><span class="sxs-lookup"><span data-stu-id="a0992-269">Abort the current transaction and create a new one.</span></span> <span data-ttu-id="a0992-270">Reenvíe todos los mensajes anteriores de la sesión.</span><span class="sxs-lookup"><span data-stu-id="a0992-270">Resend all previous messages in the session.</span></span> <span data-ttu-id="a0992-271">Una vez que se crea una transacción en la que todos los mensajes se envían correctamente y la sesión indica que no hay más mensajes, se cierran todos los canales de sesión salientes, se rellenan todos los contextos de recepción con la transacción, se cierra el canal de sesión entrante y se confirma la transacción.</span><span class="sxs-lookup"><span data-stu-id="a0992-271">After a transaction has been created in which all messages have been successfully sent and the session indicates no more messages, all the outbound session channels are closed, receive contexts are all completed with the transaction, the inbound session channel is closed, and the transaction is committed.</span></span><br /><br /> <span data-ttu-id="a0992-272">Cuando las sesiones son de multidifusión, los mensajes que no produjeron errores se reenvían al mismo destino y los mensajes que sí los produjeron se envían a los destinos de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-272">When the sessions are being multicast the messages that had no error are resent to the same destination as before, and messages that encountered an error are sent to backup destinations.</span></span>|
|<span data-ttu-id="a0992-273">Bidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-273">Two-Way</span></span>||||<span data-ttu-id="a0992-274">Sí</span><span class="sxs-lookup"><span data-stu-id="a0992-274">Yes</span></span>|<span data-ttu-id="a0992-275">Realice un envío a un destino de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-275">Send to a backup destination.</span></span>  <span data-ttu-id="a0992-276">Una vez que el canal devuelve un mensaje de respuesta, devuelva la respuesta al cliente original.</span><span class="sxs-lookup"><span data-stu-id="a0992-276">After a channel returns a response message, return the response to the original client.</span></span>|
|<span data-ttu-id="a0992-277">Bidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-277">Two-Way</span></span>|<span data-ttu-id="a0992-278">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-278">✔️</span></span>|||<span data-ttu-id="a0992-279">Sí</span><span class="sxs-lookup"><span data-stu-id="a0992-279">Yes</span></span>|<span data-ttu-id="a0992-280">Envíe todos los mensajes del canal a un destino de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-280">Send all messages on the channel to a backup destination.</span></span>  <span data-ttu-id="a0992-281">Una vez que el canal devuelve un mensaje de respuesta, devuelva la respuesta al cliente original.</span><span class="sxs-lookup"><span data-stu-id="a0992-281">After a channel returns a response message, return the response to the original client.</span></span>|
|<span data-ttu-id="a0992-282">Bidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-282">Two-Way</span></span>||<span data-ttu-id="a0992-283">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-283">✔️</span></span>||<span data-ttu-id="a0992-284">No</span><span class="sxs-lookup"><span data-stu-id="a0992-284">No</span></span>|<span data-ttu-id="a0992-285">Se lanza una excepción y se deshace la transacción.</span><span class="sxs-lookup"><span data-stu-id="a0992-285">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="a0992-286">Bidireccional</span><span class="sxs-lookup"><span data-stu-id="a0992-286">Two-Way</span></span>|<span data-ttu-id="a0992-287">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-287">✔️</span></span>|<span data-ttu-id="a0992-288">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-288">✔️</span></span>||<span data-ttu-id="a0992-289">No</span><span class="sxs-lookup"><span data-stu-id="a0992-289">No</span></span>|<span data-ttu-id="a0992-290">Se lanza una excepción y se deshace la transacción.</span><span class="sxs-lookup"><span data-stu-id="a0992-290">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="a0992-291">Dúplex</span><span class="sxs-lookup"><span data-stu-id="a0992-291">Duplex</span></span>||||<span data-ttu-id="a0992-292">No</span><span class="sxs-lookup"><span data-stu-id="a0992-292">No</span></span>|<span data-ttu-id="a0992-293">Actualmente, no se admite una comunicación dúplex que no sea de sesiones.</span><span class="sxs-lookup"><span data-stu-id="a0992-293">Non-session duplex communication is not currently supported.</span></span>|
|<span data-ttu-id="a0992-294">Dúplex</span><span class="sxs-lookup"><span data-stu-id="a0992-294">Duplex</span></span>|<span data-ttu-id="a0992-295">✔️</span><span class="sxs-lookup"><span data-stu-id="a0992-295">✔️</span></span>|||<span data-ttu-id="a0992-296">Sí</span><span class="sxs-lookup"><span data-stu-id="a0992-296">Yes</span></span>|<span data-ttu-id="a0992-297">Realice un envío a un destino de reserva.</span><span class="sxs-lookup"><span data-stu-id="a0992-297">Send to a backup destination.</span></span>|

## <a name="hosting"></a><span data-ttu-id="a0992-298">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="a0992-298">Hosting</span></span>

<span data-ttu-id="a0992-299">Dado que el servicio de enrutamiento se implementa como un servicio WCF, debe auto-hospedarse en una aplicación o ser hospedado por un servidor IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="a0992-299">Because the Routing Service is implemented as a WCF service, it must be either self-hosted within an application or hosted by IIS or WAS.</span></span> <span data-ttu-id="a0992-300">Se recomienda que el servicio de enrutamiento se hospede bien en un IIS, en un WAS o en una aplicación de un servicio Windows para que pueda aprovecharse de las características de administración de ciclo de vida y de inicio automático que están disponibles en estos entornos de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="a0992-300">It is recommended that the Routing Service be hosted in either IIS, WAS, or a Windows Service application to take advantage of the automatic start and life-cycle management features available in these hosting environments.</span></span>

<span data-ttu-id="a0992-301">En el siguiente ejemplo, se muestra cómo hospedar el servicio de enrutamiento en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a0992-301">The following example demonstrates hosting the Routing Service in an application.</span></span>

```csharp
using (ServiceHost serviceHost =
                new ServiceHost(typeof(RoutingService)))
```

<span data-ttu-id="a0992-302">Para hospedar el servicio de enrutamiento dentro de un IIS o WAS, debe crear un archivo de servicio (.svc) o utilizar la activación basada en configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="a0992-302">To host the Routing Service within IIS or WAS, you must either create a service file (.svc) or use configuration-based activation of the service.</span></span> <span data-ttu-id="a0992-303">Al utilizar un archivo de servicio, debe especificar la clase <xref:System.ServiceModel.Routing.RoutingService> que utiliza el parámetro del servicio.</span><span class="sxs-lookup"><span data-stu-id="a0992-303">When using a service file, you must specify the <xref:System.ServiceModel.Routing.RoutingService> using the Service parameter.</span></span> <span data-ttu-id="a0992-304">El siguiente ejemplo contiene un archivo de servicio de ejemplo que se puede utilizar para hospedar el servicio de enrutamiento con IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="a0992-304">The following example contains a sample service file that can be used to host the Routing Service with IIS or WAS.</span></span>

```aspx-csharp
<%@ ServiceHost Language="C#" Debug="true" Service="System.ServiceModel.Routing.RoutingService,
     System.ServiceModel.Routing, version=4.0.0.0, Culture=neutral,
     PublicKeyToken=31bf3856ad364e35" %>
```

## <a name="routing-service-and-impersonation"></a><span data-ttu-id="a0992-305">Servicio de enrutamiento y suplantación</span><span class="sxs-lookup"><span data-stu-id="a0992-305">Routing Service and Impersonation</span></span>

<span data-ttu-id="a0992-306">El Servicio de enrutamiento de WCF se puede usar con suplantación para enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="a0992-306">The WCF Routing Service can be used with impersonation for both sending and receiving messages.</span></span> <span data-ttu-id="a0992-307">Todas las restricciones habituales de Windows de suplantación se aplican.</span><span class="sxs-lookup"><span data-stu-id="a0992-307">All of the usual Windows constraints of impersonation apply.</span></span> <span data-ttu-id="a0992-308">Si hubiera necesitado configurar permisos de servicio o de cuenta para usar la suplantación al escribir su propio servicio, tendría que realizar los mismos pasos para usar la suplantación con el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a0992-308">If you would have needed to set up service or account permissions to use impersonation when writing your own service, then you’ll have to do those same steps to use impersonation with the routing service.</span></span> <span data-ttu-id="a0992-309">Para obtener más información, consulte [delegación y suplantación](delegation-and-impersonation-with-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="a0992-309">For more information, see [Delegation and Impersonation](delegation-and-impersonation-with-wcf.md).</span></span>

<span data-ttu-id="a0992-310">La suplantación con el servicio de enrutamiento necesita tanto el uso de la suplantación de ASP.NET mientras está en modo de compatibilidad de ASP.NET como el uso de credenciales de Windows que se han configurado para permitir la suplantación.</span><span class="sxs-lookup"><span data-stu-id="a0992-310">Impersonation with the routing service requires either the use of ASP.NET impersonation while in ASP.NET compatibility mode or the use of Windows credentials that have been configured to allow impersonation.</span></span> <span data-ttu-id="a0992-311">Para obtener más información sobre el modo de compatibilidad de ASP.NET, consulte [servicios WCF y ASP.net](wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="a0992-311">For more information about ASP.NET compatibility mode, see [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span></span>

> [!WARNING]
> <span data-ttu-id="a0992-312">El Servicio de enrutamiento de WCF no admite la suplantación con la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="a0992-312">The WCF Routing Service does not support impersonation with basic authentication.</span></span>

<span data-ttu-id="a0992-313">Para usar la suplantación de ASP.NET con el servicio de enrutamiento, habilite el modo de compatibilidad de ASP.NET en el entorno de hospedaje del servicio.</span><span class="sxs-lookup"><span data-stu-id="a0992-313">To use ASP.NET impersonation with the routing service, enable ASP.NET compatibility mode on the service hosting environment.</span></span> <span data-ttu-id="a0992-314">El servicio de enrutamiento se ha ya marcado como que permite el modo de compatibilidad de ASP.NET y la suplantación se habilitará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a0992-314">The routing service has already been marked as allowing ASP.NET compatibility mode and impersonation will automatically be enabled.</span></span> <span data-ttu-id="a0992-315">La suplantación es el único uso admitido de la integración de ASP.NET con el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a0992-315">Impersonation is the only supported use of ASP.NET integration with the routing service.</span></span>

<span data-ttu-id="a0992-316">Para usar la suplantación de la credencial de Windows con el servicio de enrutamiento, necesita configurar las credenciales y el servicio.</span><span class="sxs-lookup"><span data-stu-id="a0992-316">To use Windows credential impersonation with the routing service you need to configure both the credentials and the service.</span></span> <span data-ttu-id="a0992-317">El objeto de credenciales de cliente (<xref:System.ServiceModel.Security.WindowsClientCredential>, accesible desde <xref:System.ServiceModel.ChannelFactory>) define una propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> que se debe establecer para permitir la suplantación.</span><span class="sxs-lookup"><span data-stu-id="a0992-317">The client credentials object (<xref:System.ServiceModel.Security.WindowsClientCredential>, accessable from the <xref:System.ServiceModel.ChannelFactory>) defines an <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> property that must be set to permit impersonation.</span></span> <span data-ttu-id="a0992-318">Finalmente, en el servicio se debe configurar el comportamiento <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> para establecer `ImpersonateCallerForAllOperations` en `true`.</span><span class="sxs-lookup"><span data-stu-id="a0992-318">Finally, on the service you need to configure the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> behavior to set `ImpersonateCallerForAllOperations` to `true`.</span></span> <span data-ttu-id="a0992-319">El servicio de enrutamiento usa esta marca para decidir si crear los clientes para reenviar mensajes con la suplantación habilitada.</span><span class="sxs-lookup"><span data-stu-id="a0992-319">The routing service uses this flag to decide whether to create the clients for forwarding messages with impersonation enabled.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0992-320">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a0992-320">See also</span></span>

- [<span data-ttu-id="a0992-321">Filtros de mensajes</span><span class="sxs-lookup"><span data-stu-id="a0992-321">Message Filters</span></span>](message-filters.md)
- [<span data-ttu-id="a0992-322">Enrutamiento de contratos</span><span class="sxs-lookup"><span data-stu-id="a0992-322">Routing Contracts</span></span>](routing-contracts.md)
- [<span data-ttu-id="a0992-323">Elección de un filtro</span><span class="sxs-lookup"><span data-stu-id="a0992-323">Choosing a Filter</span></span>](choosing-a-filter.md)
