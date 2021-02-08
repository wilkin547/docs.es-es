---
description: 'Más información sobre: Introducción al enrutamiento'
title: Introducción al enrutamiento
ms.date: 03/30/2017
ms.assetid: bf6ceb38-6622-433b-9ee7-f79bc93497a1
ms.openlocfilehash: 86f5b5dcc0bea067ac3dcfc8a87331da42c642aa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779899"
---
# <a name="routing-introduction"></a><span data-ttu-id="1a616-103">Introducción al enrutamiento</span><span class="sxs-lookup"><span data-stu-id="1a616-103">Routing Introduction</span></span>

<span data-ttu-id="1a616-104">El servicio de enrutamiento proporciona un intermediario de SOAP conectable genérico que es capaz de enrutar mensajes en función de su contenido.</span><span class="sxs-lookup"><span data-stu-id="1a616-104">The Routing Service provides a generic pluggable SOAP intermediary that is capable of routing messages based on message content.</span></span> <span data-ttu-id="1a616-105">Con el servicio de enrutamiento, puede crear una lógica de enrutamiento compleja que le permita implementar escenarios como la agregación de servicios, el control de versiones del servicio, el enrutamiento de prioridad y el enrutamiento de multidifusión.</span><span class="sxs-lookup"><span data-stu-id="1a616-105">With the Routing Service, you can create complex routing logic that allows you to implement scenarios such as service aggregation, service versioning, priority routing, and multicast routing.</span></span> <span data-ttu-id="1a616-106">El servicio de enrutamiento también proporciona un control de errores, que le permite preparar listas de puntos de conexión de reserva a los que se envían los mensajes si se produce un error al realizar un envío al punto de conexión de destino principal.</span><span class="sxs-lookup"><span data-stu-id="1a616-106">The Routing Service also provides error handling that allows you to set up lists of backup endpoints, to which messages are sent if a failure occurs when sending to the primary destination endpoint.</span></span>

<span data-ttu-id="1a616-107">Este tema está dirigido a aquellos usuarios que se están iniciando en el servicio de enrutamiento, y cubre la configuración básica y el hospedaje del servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="1a616-107">This topic is intended for those new to the Routing Service and covers basic configuration and hosting of the Routing Service.</span></span>

## <a name="configuration"></a><span data-ttu-id="1a616-108">Configuración</span><span class="sxs-lookup"><span data-stu-id="1a616-108">Configuration</span></span>

<span data-ttu-id="1a616-109">El servicio de enrutamiento se implementa como un servicio de WCF que expone uno o varios puntos de conexión de servicio. Estos puntos de conexión reciben mensajes de aplicaciones cliente y los enrutan a uno o más puntos de conexión de destino.</span><span class="sxs-lookup"><span data-stu-id="1a616-109">The Routing Service is implemented as a WCF service that exposes one or more service endpoints that receive messages from client applications and route the messages to one or more destination endpoints.</span></span> <span data-ttu-id="1a616-110">El servicio proporciona <xref:System.ServiceModel.Routing.RoutingBehavior>, que se aplica a los puntos de conexión de servicio que expone el servicio.</span><span class="sxs-lookup"><span data-stu-id="1a616-110">The service provides a <xref:System.ServiceModel.Routing.RoutingBehavior>, which is applied to the service endpoints exposed by the service.</span></span> <span data-ttu-id="1a616-111">Este comportamiento se utiliza para configurar varios aspectos del funcionamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="1a616-111">This behavior is used to configure various aspects of how the service operates.</span></span> <span data-ttu-id="1a616-112">Para facilitar la configuración cuando se usa un archivo de configuración, los parámetros se especifican en **RoutingBehavior**.</span><span class="sxs-lookup"><span data-stu-id="1a616-112">For ease of configuration when using a configuration file, the parameters are specified on the **RoutingBehavior**.</span></span> <span data-ttu-id="1a616-113">En escenarios basados en código, estos parámetros se especifican como parte de un <xref:System.ServiceModel.Routing.RoutingConfiguration> objeto, que se puede pasar a continuación a un **RoutingBehavior**.</span><span class="sxs-lookup"><span data-stu-id="1a616-113">In code-based scenarios, these parameters would be specified as part of a <xref:System.ServiceModel.Routing.RoutingConfiguration> object, which can then be passed to a **RoutingBehavior**.</span></span>

<span data-ttu-id="1a616-114">Al iniciarse, este comportamiento agrega el objeto <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, que se utiliza para realizar el procesamiento de SOAP de mensajes, a los puntos de conexión de cliente.</span><span class="sxs-lookup"><span data-stu-id="1a616-114">When starting, this behavior adds the <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, which is used to perform SOAP processing of messages, to the client endpoints.</span></span> <span data-ttu-id="1a616-115">Esto permite al servicio de enrutamiento transmitir mensajes a los puntos de conexión que requieren un **MessageVersion** diferente que el punto de conexión en el que se recibió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-115">This allows the Routing Service to transmit messages to endpoints that require a different **MessageVersion** than the endpoint the message was received over.</span></span> <span data-ttu-id="1a616-116">**RoutingBehavior** también registra una extensión de servicio, <xref:System.ServiceModel.Routing.RoutingExtension> que proporciona un punto de accesibilidad para modificar la configuración del servicio de enrutamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1a616-116">The **RoutingBehavior** also registers a service extension, the <xref:System.ServiceModel.Routing.RoutingExtension>, which provides an accessibility point for modifying the Routing Service configuration at run time.</span></span>

<span data-ttu-id="1a616-117">La clase **RoutingConfiguration** proporciona un medio coherente para configurar y actualizar la configuración del servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="1a616-117">The **RoutingConfiguration** class provides a consistent means of configuring and updating the configuration of the Routing Service.</span></span>  <span data-ttu-id="1a616-118">Contiene parámetros que actúan como la configuración para el servicio de enrutamiento y se usa para configurar el **RoutingBehavior** cuando se inicia el servicio o se pasa a **RoutingExtension** para modificar la configuración de enrutamiento en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1a616-118">It contains parameters that act as the settings for the Routing Service and is used to configure the **RoutingBehavior** when the service starts, or is passed to the **RoutingExtension** to modify routing configuration at run time.</span></span>

<span data-ttu-id="1a616-119">La lógica de enrutamiento utilizada para realizar el enrutamiento basado en el contenido de mensajes se define agrupando varios objetos <xref:System.ServiceModel.Dispatcher.MessageFilter> en tablas de filtro (objetos<xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>).</span><span class="sxs-lookup"><span data-stu-id="1a616-119">The routing logic used to perform content-based routing of messages is defined by grouping multiple <xref:System.ServiceModel.Dispatcher.MessageFilter> objects together into filter tables (<xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> objects).</span></span> <span data-ttu-id="1a616-120">Los mensajes entrantes se evalúan con los filtros de mensajes contenidos en la tabla de filtros, y para cada **MessageFilter** que coincida con el mensaje, se reenvía a un extremo de destino.</span><span class="sxs-lookup"><span data-stu-id="1a616-120">Incoming messages are evaluated against the message filters contained in the filter table, and for each **MessageFilter** that matches the message, forwarded to a destination endpoint.</span></span> <span data-ttu-id="1a616-121">La tabla de filtros que se debe usar para enrutar los mensajes se especifica mediante el uso de **RoutingBehavior** en la configuración o a través del código mediante el objeto **RoutingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1a616-121">The filter table that should be used to route messages is specified by using either the **RoutingBehavior** in configuration or through code by using the **RoutingConfiguration** object.</span></span>

### <a name="defining-endpoints"></a><span data-ttu-id="1a616-122">Definición de extremos</span><span class="sxs-lookup"><span data-stu-id="1a616-122">Defining Endpoints</span></span>

<span data-ttu-id="1a616-123">Pese a que pueda parecer que debería iniciar su configuración definiendo la lógica de enrutamiento que va a utilizar, el primer paso sería realmente determinar la forma de los puntos de conexión a los que va a enrutar mensajes.</span><span class="sxs-lookup"><span data-stu-id="1a616-123">While it may seem that you should start your configuration by defining the routing logic you will use, your first step should actually be to determine the shape of the endpoints you will be routing messages to.</span></span> <span data-ttu-id="1a616-124">El servicio de enrutamiento utiliza contratos que definen la forma de los canales utilizados para recibir y enviar mensajes y, por consiguiente, la forma del canal de entrada debe coincidir con la del canal de salida.</span><span class="sxs-lookup"><span data-stu-id="1a616-124">The Routing Service uses contracts that define the shape of the channels used to receive and send messages, and therefore the shape of the input channel must match that of the output channel.</span></span>  <span data-ttu-id="1a616-125">Por ejemplo, si va a enrutar mensajes a puntos de conexión que utilizan la forma de canal "solicitud-respuesta", entonces debe utilizar un contrato compatible en los puntos de conexión entrantes, como <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span><span class="sxs-lookup"><span data-stu-id="1a616-125">For example, if you are routing to endpoints that use the request-reply channel shape, then you must use a compatible contract on the inbound endpoints, such as the <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span></span>

<span data-ttu-id="1a616-126">Esto significa que, si sus extremos de destino utilizan contratos con varios patrones de comunicación (como la combinación de operaciones unidireccionales y bidireccionales), no puede crear ningún extremo de servicio único que pueda recibir y enrutar mensajes a todos ellos.</span><span class="sxs-lookup"><span data-stu-id="1a616-126">This means that if your destination endpoints use contracts with multiple communication patterns (such as mixing one-way and two-way operations,) you cannot create a single service endpoint that can receive and route messages to all of them.</span></span> <span data-ttu-id="1a616-127">Debe determinar qué puntos de conexión tienen formas compatibles y definir uno o varios puntos de conexión de servicio para recibir los mensajes que se van a enrutar a los puntos de conexión de destino.</span><span class="sxs-lookup"><span data-stu-id="1a616-127">You must determine which endpoints have compatible shapes and define one or more service endpoints that will be used to receive messages to be routed to the destination endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="1a616-128">Al trabajar con contratos que especifican varios patrones de comunicación (como una combinación de operaciones unidireccionales y bidireccionales), una solución alternativa sería usar un contrato dúplex en el servicio de enrutamiento, como <xref:System.ServiceModel.Routing.IDuplexSessionRouter>.</span><span class="sxs-lookup"><span data-stu-id="1a616-128">When working with contracts that specify multiple communication patterns (such as a mix of one-way and two-way operations,) a workaround is to use a duplex contract at the Routing Service such as <xref:System.ServiceModel.Routing.IDuplexSessionRouter>.</span></span> <span data-ttu-id="1a616-129">Sin embargo, esto implica que el enlace debe ser capaz de realizar una comunicación dúplex, algo que puede no ser posible en todos los escenarios.</span><span class="sxs-lookup"><span data-stu-id="1a616-129">However this means that the binding must be capable of duplex communication, which may not be possible for all scenarios.</span></span> <span data-ttu-id="1a616-130">En escenarios en los que esto no sea posible, puede ser necesario dividir la comunicación en varios puntos de conexión o modificar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1a616-130">In scenarios where this is not possible, factoring the communication into multiple endpoints or modifying the application may be necessary.</span></span>

<span data-ttu-id="1a616-131">Para obtener más información sobre los contratos de enrutamiento, consulte [enrutamiento de contratos](routing-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="1a616-131">For more information about routing contracts, see [Routing Contracts](routing-contracts.md).</span></span>

<span data-ttu-id="1a616-132">Una vez definido el punto de conexión de servicio, puede usar **RoutingBehavior** para asociar un **RoutingConfiguration** específico con el punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1a616-132">After the service endpoint is defined, you can use the **RoutingBehavior** to associate a specific **RoutingConfiguration** with the endpoint.</span></span> <span data-ttu-id="1a616-133">Al configurar el servicio de enrutamiento mediante un archivo de configuración, **RoutingBehavior** se utiliza para especificar la tabla de filtros que contiene la lógica de enrutamiento utilizada para procesar los mensajes recibidos en este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1a616-133">When configuring the Routing Service by using a configuration file, the **RoutingBehavior** is used to specify the filter table that contains the routing logic used to process messages received on this endpoint.</span></span> <span data-ttu-id="1a616-134">Si va a configurar el servicio de enrutamiento mediante programación, puede especificar la tabla de filtros mediante **RoutingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1a616-134">If you are configuring the Routing Service programmatically you can specify the filter table by using the **RoutingConfiguration**.</span></span>

<span data-ttu-id="1a616-135">En el siguiente ejemplo, se definen los puntos de conexión de cliente y servicio que usa el servicio de enrutamiento tanto mediante programación como por medio de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1a616-135">The following example defines the service and client endpoints that are used by the Routing Service both programmatically and by using a configuration file.</span></span>

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

<span data-ttu-id="1a616-136">En este ejemplo se configura el servicio de enrutamiento para exponer un punto de conexión único con una dirección de `http://localhost:8000/routingservice/router` , que se utiliza para recibir los mensajes que se van a enrutar.</span><span class="sxs-lookup"><span data-stu-id="1a616-136">This example configures the Routing Service to expose a single endpoint with an address of `http://localhost:8000/routingservice/router`, which is used to receive messages to be routed.</span></span> <span data-ttu-id="1a616-137">Dado que los mensajes se enrutan a puntos de conexión solicitud-respuesta, el punto de conexión de servicio utiliza el contrato <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span><span class="sxs-lookup"><span data-stu-id="1a616-137">Because the messages are routed to request-reply endpoints, the service endpoint uses the <xref:System.ServiceModel.Routing.IRequestReplyRouter> contract.</span></span> <span data-ttu-id="1a616-138">Esta configuración también define un punto de conexión de cliente único de `http://localhost:8000/servicemodelsample/service` al que se enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="1a616-138">This configuration also defines a single client endpoint of `http://localhost:8000/servicemodelsample/service` that messages are routed to.</span></span> <span data-ttu-id="1a616-139">La tabla de filtros (no se muestra) denominada "routingTable1" contiene la lógica de enrutamiento que se usa para enrutar los mensajes y está asociada al punto de conexión de servicio mediante **RoutingBehavior** (para un archivo de configuración) o **RoutingConfiguration** (para la configuración mediante programación).</span><span class="sxs-lookup"><span data-stu-id="1a616-139">The filter table (not shown) named "routingTable1" contains the routing logic used to route messages, and is associated with the service endpoint by using the **RoutingBehavior** (for a configuration file) or **RoutingConfiguration** (for programmatic configuration).</span></span>

### <a name="routing-logic"></a><span data-ttu-id="1a616-140">Lógica de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="1a616-140">Routing Logic</span></span>

<span data-ttu-id="1a616-141">Para definir la lógica de enrutamiento utilizada para enrutar los mensajes, debe determinar sobre qué datos se puede actuar de entre los contenidos dentro de los mensajes entrantes.</span><span class="sxs-lookup"><span data-stu-id="1a616-141">To define the routing logic used to route messages, you must determine what data contained within the incoming messages can be uniquely acted upon.</span></span> <span data-ttu-id="1a616-142">Por ejemplo, si todos los extremos de destino a los que va a enrutar mensajes comparten las mismas acciones SOAP, el valor de la acción SOAP incluida dentro del mensaje no es un buen indicador de a qué extremo concreto se debe enrutar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-142">For example, if all the destination endpoints you are routing to share the same SOAP Actions, the value of the Action contained within the message is not a good indicator of which specific endpoint the message should be routed to.</span></span> <span data-ttu-id="1a616-143">Si debe enrutar los mensajes únicamente a un punto de conexión concreto, debe filtrar según los datos que identifiquen exclusivamente el punto de conexión de destino al que se enruta el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-143">If you must uniquely route messages to one specific endpoint, you should filter upon data that uniquely identifies the destination endpoint that the message is routed to.</span></span>

<span data-ttu-id="1a616-144">El servicio de enrutamiento proporciona varias implementaciones de **MessageFilter** que inspeccionan valores específicos del mensaje, como la dirección, la acción, el nombre del punto de conexión o incluso una consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="1a616-144">The Routing Service provides several **MessageFilter** implementations that inspect specific values within the message, such as the address, action, endpoint name, or even an XPath query.</span></span> <span data-ttu-id="1a616-145">Si ninguna de estas implementaciones satisface sus necesidades, puede crear una implementación de **MessageFilter** personalizada.</span><span class="sxs-lookup"><span data-stu-id="1a616-145">If none of these implementations meet your needs you can create a custom **MessageFilter** implementation.</span></span> <span data-ttu-id="1a616-146">Para obtener más información sobre los filtros de mensajes y una comparación de las implementaciones utilizadas por el servicio de enrutamiento, vea [filtros de mensajes](message-filters.md) y [elegir un filtro](choosing-a-filter.md).</span><span class="sxs-lookup"><span data-stu-id="1a616-146">For more information about message filters and a comparison of the implementations used by the Routing Service, see [Message Filters](message-filters.md) and [Choosing a Filter](choosing-a-filter.md).</span></span>

<span data-ttu-id="1a616-147">Varios filtros de mensajes se organizan juntos en tablas de filtros, que asocian cada **MessageFilter** a un extremo de destino.</span><span class="sxs-lookup"><span data-stu-id="1a616-147">Multiple message filters are organized together into filter tables, which associate each **MessageFilter** with a destination endpoint.</span></span> <span data-ttu-id="1a616-148">Opcionalmente, la tabla de filtros también se puede utilizar para especificar una lista de extremos de reserva a los que el servicio de enrutamiento intentará enviar el mensaje en caso de que se produzca un error de transmisión.</span><span class="sxs-lookup"><span data-stu-id="1a616-148">Optionally, the filter table can also be used to specify a list of back-up endpoints that the Routing Service will attempt to send the message to in the event of a transmission failure.</span></span>

<span data-ttu-id="1a616-149">De forma predeterminada, todos los filtros de mensajes de una tabla de filtros se evalúan simultáneamente; sin embargo, puede especificar <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A> para que la evaluación de los filtros se efectúe en un orden concreto.</span><span class="sxs-lookup"><span data-stu-id="1a616-149">By default all message filters within a filter table are evaluated simultaneously; however, you can specify a <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A> that causes the message filters to be evaluated in a specific order.</span></span> <span data-ttu-id="1a616-150">Primero se evalúan todas las entradas de mayor prioridad y los filtros de mensaje de menor prioridad no se evalúan si se detecta una coincidencia en un nivel de prioridad más alto.</span><span class="sxs-lookup"><span data-stu-id="1a616-150">All entries with the highest priority are evaluated first, and message filters of lower priorities are not evaluated if a match is found at a higher priority level.</span></span> <span data-ttu-id="1a616-151">Para obtener más información acerca de las tablas de filtros, vea [filtros de mensajes](message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="1a616-151">For more information about filter tables, see [Message Filters](message-filters.md).</span></span>

<span data-ttu-id="1a616-152">En los siguientes ejemplos, se utiliza <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, que evalúa todos los mensajes como `true`.</span><span class="sxs-lookup"><span data-stu-id="1a616-152">The following examples use the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, which evaluates to `true` for all messages.</span></span> <span data-ttu-id="1a616-153">Este **MessageFilter** se agrega a la tabla de filtros "routingTable1", que asocia **MessageFilter** con el punto de conexión de cliente denominado "CalculatorService".</span><span class="sxs-lookup"><span data-stu-id="1a616-153">This **MessageFilter** is added to the "routingTable1" filter table, which associates the **MessageFilter** with the client endpoint named "CalculatorService".</span></span> <span data-ttu-id="1a616-154">A continuación, **RoutingBehavior** especifica que esta tabla se debe utilizar para enrutar los mensajes procesados por el punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="1a616-154">The **RoutingBehavior** then specifies that this table should be used to route messages processed by the service endpoint.</span></span>

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
> <span data-ttu-id="1a616-155">De forma predeterminada, el servicio de enrutamiento solo evalúa los encabezados del mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-155">By default, the Routing Service only evaluates the headers of the message.</span></span> <span data-ttu-id="1a616-156">Para permitir a los filtros tener acceso al cuerpo del mensaje, debe establecer <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> en `false`.</span><span class="sxs-lookup"><span data-stu-id="1a616-156">To allow the filters to access the message body, you must set <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> to `false`.</span></span>

<span data-ttu-id="1a616-157">**Multidifusión**</span><span class="sxs-lookup"><span data-stu-id="1a616-157">**Multicast**</span></span>

<span data-ttu-id="1a616-158">Aunque muchas configuraciones del servicio de enrutamiento utilizan una lógica de filtros exclusiva que enruta los mensajes solo a un punto de conexión específico, puede que tenga que enrutar un mensaje determinado a varios puntos de conexión de destino.</span><span class="sxs-lookup"><span data-stu-id="1a616-158">While many Routing Service configurations use exclusive filter logic that routes messages to only one specific endpoint, you may need to route a given message to multiple destination endpoints.</span></span> <span data-ttu-id="1a616-159">Para difundir un mensaje a varios destinos, deben cumplirse las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="1a616-159">To multicast a message to multiple destinations, the following conditions must be true:</span></span>

- <span data-ttu-id="1a616-160">La forma del canal no puede ser de "solicitud-respuesta" (aunque sí unidireccional o dúplex), porque la aplicación cliente solo puede recibir una respuesta para cada solicitud.</span><span class="sxs-lookup"><span data-stu-id="1a616-160">The channel shape must not be request-reply (though may be one-way or duplex,) because only one reply can be received by the client application in response to the request.</span></span>

- <span data-ttu-id="1a616-161">Varios filtros deben devolver `true` al evaluar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-161">Multiple filters must return `true` when evaluating the message.</span></span>

<span data-ttu-id="1a616-162">Si se cumplen estas condiciones, el mensaje se enruta a todos los puntos de conexión de todos los filtros que se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="1a616-162">If these conditions are met, the message is routed to all endpoints of all filters that evaluate to `true`.</span></span> <span data-ttu-id="1a616-163">En el ejemplo siguiente se define una configuración de enrutamiento que hace que los mensajes se enruten a ambos extremos si la dirección del punto de conexión en el mensaje es `http://localhost:8000/routingservice/router/rounding` .</span><span class="sxs-lookup"><span data-stu-id="1a616-163">The following example defines a routing configuration that results in messages being routed to both endpoints if the endpoint address in the message is `http://localhost:8000/routingservice/router/rounding`.</span></span>

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

### <a name="soap-processing"></a><span data-ttu-id="1a616-164">Procesamiento de SOAP</span><span class="sxs-lookup"><span data-stu-id="1a616-164">SOAP Processing</span></span>

<span data-ttu-id="1a616-165">Para admitir el enrutamiento de mensajes entre protocolos distintos, **RoutingBehavior** agrega de forma predeterminada <xref:System.ServiceModel.Routing.SoapProcessingBehavior> a todos los extremos de cliente a los que se enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="1a616-165">To support the routing of messages between dissimilar protocols, the **RoutingBehavior** by default adds the <xref:System.ServiceModel.Routing.SoapProcessingBehavior> to all client endpoint(s) that messages are routed to.</span></span> <span data-ttu-id="1a616-166">Este comportamiento crea automáticamente un nuevo **messageversion** antes de enrutar el mensaje al punto de conexión, así como la creación de un **messageversion** compatible para cualquier documento de respuesta antes de devolverlo a la aplicación cliente que lo solicita.</span><span class="sxs-lookup"><span data-stu-id="1a616-166">This behavior automatically creates a new **MessageVersion** before routing the message to the endpoint, as well as creating a compatible **MessageVersion** for any response document before returning it to the requesting client application.</span></span>

<span data-ttu-id="1a616-167">Los pasos que se llevan a cabo para crear un nuevo **MessageVersion** para el mensaje de salida son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="1a616-167">The steps taken to create a new **MessageVersion** for the outbound message are as follows:</span></span>

<span data-ttu-id="1a616-168">**Procesamiento de solicitudes**</span><span class="sxs-lookup"><span data-stu-id="1a616-168">**Request processing**</span></span>

- <span data-ttu-id="1a616-169">Obtiene el **MessageVersion** del enlace o canal de salida.</span><span class="sxs-lookup"><span data-stu-id="1a616-169">Get the **MessageVersion** of the outbound binding/channel.</span></span>

- <span data-ttu-id="1a616-170">Obtenga el lector del cuerpo del mensaje original.</span><span class="sxs-lookup"><span data-stu-id="1a616-170">Get the body reader for the original message.</span></span>

- <span data-ttu-id="1a616-171">Cree un nuevo mensaje con la misma acción, el lector del cuerpo y un nuevo **MessageVersion**.</span><span class="sxs-lookup"><span data-stu-id="1a616-171">Create a new message with the same action, body reader, and a new **MessageVersion**.</span></span>

- <span data-ttu-id="1a616-172">Si <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> ! = **Addressing. None**, copie los encabezados to, from, FaultTo y latest en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-172">If <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> != **Addressing.None**, copy the To, From, FaultTo, and RelatesTo headers to the new message.</span></span>

- <span data-ttu-id="1a616-173">Copie todas las propiedades del mensaje en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-173">Copy all message properties to the new message.</span></span>

- <span data-ttu-id="1a616-174">Almacene el mensaje de solicitud original para utilizarlo al procesar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="1a616-174">Store the original request message to use when processing the response.</span></span>

- <span data-ttu-id="1a616-175">Devuelva el nuevo mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="1a616-175">Return the new request message.</span></span>

<span data-ttu-id="1a616-176">**Procesamiento de respuestas**</span><span class="sxs-lookup"><span data-stu-id="1a616-176">**Response processing**</span></span>

- <span data-ttu-id="1a616-177">Obtiene **MessageVersion** del mensaje de solicitud original.</span><span class="sxs-lookup"><span data-stu-id="1a616-177">Get the **MessageVersion** of the original request message.</span></span>

- <span data-ttu-id="1a616-178">Obtenga el lector del cuerpo del mensaje de respuesta recibido.</span><span class="sxs-lookup"><span data-stu-id="1a616-178">Get the body reader for the received response message.</span></span>

- <span data-ttu-id="1a616-179">Cree un nuevo mensaje de respuesta con la misma acción, el lector del cuerpo y el **MessageVersion** del mensaje de solicitud original.</span><span class="sxs-lookup"><span data-stu-id="1a616-179">Create a new response message with the same action, body reader, and the **MessageVersion** of the original request message.</span></span>

- <span data-ttu-id="1a616-180">Si <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> ! = **Addressing. None**, copie los encabezados to, from, FaultTo y latest en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-180">If <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> != **Addressing.None**, copy the To, From, FaultTo, and RelatesTo headers to the new message.</span></span>

- <span data-ttu-id="1a616-181">Copie las propiedades del mensaje en el nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-181">Copy the message properties to the new message.</span></span>

- <span data-ttu-id="1a616-182">Devuelva el nuevo mensaje de respuesta.</span><span class="sxs-lookup"><span data-stu-id="1a616-182">Return the new response message.</span></span>

<span data-ttu-id="1a616-183">De forma predeterminada, cuando se inicia el servicio, el **SoapProcessingBehavior** se agrega automáticamente a los puntos de conexión de cliente <xref:System.ServiceModel.Routing.RoutingBehavior> ; sin embargo, puede controlar si el procesamiento de SOAP se agrega a todos los extremos de cliente mediante la <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="1a616-183">By default, the **SoapProcessingBehavior** is automatically added to the client endpoints by the <xref:System.ServiceModel.Routing.RoutingBehavior> when the service starts; however, you can control whether SOAP processing is added to all client endpoints by using the <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A> property.</span></span> <span data-ttu-id="1a616-184">También puede agregar el comportamiento directamente a un punto de conexión específico, y habilitar o deshabilitar este comportamiento en los puntos de conexión si se requiere un control de procesamiento de SOAP más granular.</span><span class="sxs-lookup"><span data-stu-id="1a616-184">You can also add the behavior directly to a specific endpoint and enable or disable this behavior at the endpoint level if a more granular control of SOAP processing is required.</span></span>

> [!NOTE]
> <span data-ttu-id="1a616-185">Si el procesamiento de SOAP está deshabilitado para un extremo que requiere un valor MessageVersion diferente al del mensaje de solicitud original, debe proporcionar un mecanismo personalizado para que realice todas las modificaciones de SOAP que sean necesarias antes de enviar el mensaje al extremo de destino.</span><span class="sxs-lookup"><span data-stu-id="1a616-185">If SOAP processing is disabled for an endpoint that requires a different MessageVersion than that of the original request message, you must provide a custom mechanism for performing any SOAP modifications that are required before sending the message to the destination endpoint.</span></span>

<span data-ttu-id="1a616-186">En los ejemplos siguientes, se usa la propiedad **soapProcessingEnabled** para evitar que **SoapProcessingBehavior** se agregue automáticamente a todos los extremos de cliente.</span><span class="sxs-lookup"><span data-stu-id="1a616-186">In the following examples, the **soapProcessingEnabled** property is used to prevent the **SoapProcessingBehavior** from being automatically added to all client endpoints.</span></span>

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

### <a name="dynamic-configuration"></a><span data-ttu-id="1a616-187">Configuración dinámica</span><span class="sxs-lookup"><span data-stu-id="1a616-187">Dynamic Configuration</span></span>

<span data-ttu-id="1a616-188">Al agregar puntos de conexión de cliente adicionales, o bien cuando necesite modificar los filtros que se utilizan para enrutar los mensajes, debe encontrar una forma de actualizar dinámicamente la configuración en tiempo de ejecución para evitar la interrupción del servicio en los puntos de conexión que estén recibiendo mensajes a través del servicio de enrutamiento en ese momento.</span><span class="sxs-lookup"><span data-stu-id="1a616-188">When you add additional client endpoints, or need to modify the filters that are used to route messages, you must have a way to update the configuration dynamically at run time to prevent interrupting the service to the endpoints currently receiving messages through the Routing Service.</span></span> <span data-ttu-id="1a616-189">Modificar un archivo de configuración o el código de la aplicación host no siempre es suficiente, porque todos los métodos necesitan que se recicle la aplicación y esto conduciría a la pérdida potencial de todos los mensajes que estuvieran en tránsito en ese momento, así como a un posible tiempo de inactividad mientras se aguarda al reinicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="1a616-189">Modifying a configuration file or the code of the host application is not always sufficient, because either method requires recycling the application, which would lead to the potential loss of any messages currently in transit and the potential for downtime while waiting on the service to restart.</span></span>

<span data-ttu-id="1a616-190">Solo puede modificar el **RoutingConfiguration** mediante programación.</span><span class="sxs-lookup"><span data-stu-id="1a616-190">You can only modify the **RoutingConfiguration** programmatically.</span></span> <span data-ttu-id="1a616-191">Aunque puede configurar inicialmente el servicio mediante un archivo de configuración, solo puede modificar la configuración en tiempo de ejecución si crea un nuevo **RoutingConfiguration** y lo pasa como parámetro al <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> método expuesto por la <xref:System.ServiceModel.Routing.RoutingExtension> extensión de servicio.</span><span class="sxs-lookup"><span data-stu-id="1a616-191">While you can initially configure the service by using a configuration file, you can only modify the configuration at run time by constructing a new **RoutingConfiguration** and passing it as a parameter to the <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> method exposed by the <xref:System.ServiceModel.Routing.RoutingExtension> service extension.</span></span> <span data-ttu-id="1a616-192">Los mensajes que se encuentran actualmente en tránsito continúan siendo enrutados con la configuración anterior, mientras que los mensajes recibidos después de la llamada a **ApplyConfiguration** usan la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="1a616-192">Any messages currently in transit continue to be routed using the previous configuration, while messages received after the call to **ApplyConfiguration** use the new configuration.</span></span> <span data-ttu-id="1a616-193">En el siguiente ejemplo, se muestra cómo crear una instancia del servicio de enrutamiento y cómo modificar después la configuración.</span><span class="sxs-lookup"><span data-stu-id="1a616-193">The following example demonstrates creating an instance of the Routing Service and then subsequently modifying the configuration.</span></span>

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
> <span data-ttu-id="1a616-194">Al actualizar el servicio de enrutamiento de esta manera, solo es posible pasar una nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="1a616-194">When updating the Routing Service in this manner it is only possible to pass a new configuration.</span></span> <span data-ttu-id="1a616-195">No se puede modificar únicamente elementos determinados de la configuración actual o anexar nuevas entradas a la configuración actual. Debe crear y pasar una nueva configuración que reemplace la existente.</span><span class="sxs-lookup"><span data-stu-id="1a616-195">It is not possible to modify only select elements of the current configuration or append new entries to the current configuration; you must create and pass a new configuration that replaces the existing one.</span></span>

> [!NOTE]
> <span data-ttu-id="1a616-196">Todas las sesiones que se abrieron con la configuración anterior seguirán utilizándola.</span><span class="sxs-lookup"><span data-stu-id="1a616-196">Any sessions opened using the previous configuration continue using the previous configuration.</span></span> <span data-ttu-id="1a616-197">Sólo las nuevas sesiones usarán la configuración nueva.</span><span class="sxs-lookup"><span data-stu-id="1a616-197">The new configuration is only used by new sessions.</span></span>

## <a name="error-handling"></a><span data-ttu-id="1a616-198">Tratamiento de errores</span><span class="sxs-lookup"><span data-stu-id="1a616-198">Error Handling</span></span>

<span data-ttu-id="1a616-199">Si se encuentra algún valor <xref:System.ServiceModel.CommunicationException> al intentar enviar un mensaje, tiene lugar el control de errores.</span><span class="sxs-lookup"><span data-stu-id="1a616-199">If any <xref:System.ServiceModel.CommunicationException> is encountered while attempting to send a message, error handling take place.</span></span> <span data-ttu-id="1a616-200">Estas excepciones indican normalmente que se encontró un problema al intentar establecer comunicación con el extremo de cliente definido, como <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> o <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span><span class="sxs-lookup"><span data-stu-id="1a616-200">These exceptions typically indicate that a problem was encountered while attempting to communicate with the defined client endpoint, such as an <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException>, or <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span></span> <span data-ttu-id="1a616-201">El código de control de errores también detectará e intentará volver a realizar el envío cuando <xref:System.TimeoutException> se produzca una, que es otra excepción común que no se deriva de **CommunicationException**.</span><span class="sxs-lookup"><span data-stu-id="1a616-201">The error handling-code will also catch and attempt to retry sending when a <xref:System.TimeoutException> occurs, which is another common exception that is not derived from **CommunicationException**.</span></span>

<span data-ttu-id="1a616-202">Cuando se produce una de las excepciones anteriores, el servicio de enrutamiento no puede establecer comunicación con una lista de puntos de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-202">When one of the preceding exceptions occurs, the Routing Service fails over to a list of backup endpoints.</span></span> <span data-ttu-id="1a616-203">Si se produce un error de comunicación en todos los puntos de conexión de reserva, o bien si un punto de conexión devuelve una excepción que indica un error dentro del servicio de destino, el servicio de enrutamiento devuelve un error a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="1a616-203">If all backup endpoints fail with a communications failure, or if an endpoint returns an exception that indicates a failure within the destination service, the Routing Service returns a fault to the client application.</span></span>

> [!NOTE]
> <span data-ttu-id="1a616-204">La funcionalidad del control de errores captura y administra excepciones que se producen al intentar enviar un mensaje y al intentar cerrar un canal.</span><span class="sxs-lookup"><span data-stu-id="1a616-204">The error-handling functionality captures and handles exceptions that occur when attempting to send a message and when attempting to close a channel.</span></span> <span data-ttu-id="1a616-205">El código de control de errores no está diseñado para detectar o administrar excepciones creadas por los puntos de conexión de la aplicación con los que se comunica; un <xref:System.ServiceModel.FaultException> Iniciado por un servicio aparece en el servicio de enrutamiento como **FaultMessage** y se devuelve al cliente.</span><span class="sxs-lookup"><span data-stu-id="1a616-205">The error-handling code is not intended to detect or handle exceptions created by the application endpoints it is communicating with; a <xref:System.ServiceModel.FaultException> thrown by a service appears at the Routing Service as a **FaultMessage** and is flowed back to the client.</span></span>
>
> <span data-ttu-id="1a616-206">Si se produce un error cuando el servicio de enrutamiento intenta retransmitir un mensaje, puede obtener un objeto <xref:System.ServiceModel.FaultException> en el lado cliente, en lugar del <xref:System.ServiceModel.EndpointNotFoundException> que obtendría normalmente en ausencia del servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="1a616-206">If an error occurs when the routing service tries to relay a message, you may  get a <xref:System.ServiceModel.FaultException> on the client side, rather than a <xref:System.ServiceModel.EndpointNotFoundException> you would normally get in the absence of the routing service.</span></span> <span data-ttu-id="1a616-207">Un servicio de enrutamiento puede por tanto enmascarar las excepciones y no proporcionar una transparencia completa a menos que se examinen las excepciones anidadas.</span><span class="sxs-lookup"><span data-stu-id="1a616-207">A routing service may thus mask exceptions and not provide full transparency unless you examine nested exceptions.</span></span>

### <a name="tracing-exceptions"></a><span data-ttu-id="1a616-208">Traza de excepciones</span><span class="sxs-lookup"><span data-stu-id="1a616-208">Tracing Exceptions</span></span>

<span data-ttu-id="1a616-209">Cuando se produce un error al enviar un mensaje a un punto de conexión en una lista, el servicio de enrutamiento realiza un seguimiento de los datos de excepción resultantes y adjunta los detalles de la excepción como una propiedad de mensaje denominada **Exceptions**.</span><span class="sxs-lookup"><span data-stu-id="1a616-209">When sending a message to an endpoint in a list fails, the Routing Service traces the resulting exception data and attaches the exception details as a message property named **Exceptions**.</span></span> <span data-ttu-id="1a616-210">Esto conserva los datos de la excepción y permite al usuario tener acceso mediante programación a través de un inspector del mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-210">This preserves the exception data and allows a user programmatic access through a message inspector.</span></span>  <span data-ttu-id="1a616-211">Los datos de la excepción se almacenan por mensaje en un diccionario que asigna el nombre del punto de conexión a los detalles de la excepción producidos al intentar enviarle un mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-211">The exception data is stored per message in a dictionary that maps the endpoint name to the exception details encountered when trying to send a message to it.</span></span>

### <a name="backup-endpoints"></a><span data-ttu-id="1a616-212">puntos de conexión de reserva</span><span class="sxs-lookup"><span data-stu-id="1a616-212">Backup Endpoints</span></span>

<span data-ttu-id="1a616-213">Las entradas de la tabla de filtros pueden especificar también una lista de puntos de conexión de reserva que se utilizarán cuando se produzcan errores de transmisión al enviar mensajes al punto de conexión principal.</span><span class="sxs-lookup"><span data-stu-id="1a616-213">Each filter entry within the filter table can optionally specify a list of backup endpoints, which are used in the event of a transmission failure when sending to the primary endpoint.</span></span> <span data-ttu-id="1a616-214">Si se produce este tipo de error, el servicio de enrutamiento intenta transmitir el mensaje a la primera entrada de la lista de extremos de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-214">If such a failure occurs, the Routing Service attempts to transmit the message to the first entry in the backup endpoint list.</span></span> <span data-ttu-id="1a616-215">Si este intento resulta fallido también, se prueba con el punto de conexión de reserva siguiente de la lista.</span><span class="sxs-lookup"><span data-stu-id="1a616-215">If this send attempt also encounters a transmission failure, the next endpoint in the backup list is tried.</span></span> <span data-ttu-id="1a616-216">El servicio de enrutamiento sigue enviando el mensaje a cada uno de los extremos de la lista hasta que el mensaje se recibe correctamente, todos los extremos devuelven un error de transmisión o se produce un error distinto en el extremo.</span><span class="sxs-lookup"><span data-stu-id="1a616-216">The Routing Service continues sending the message to each endpoint in the list until the message is successfully received, all endpoints return a transmission failure, or a non-transmission failure is returned by an endpoint.</span></span>

<span data-ttu-id="1a616-217">En los siguientes ejemplos, se configura el servicio de enrutamiento para que utilice una lista de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-217">The following examples configure the Routing Service to use a backup list.</span></span>

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

### <a name="supported-error-patterns"></a><span data-ttu-id="1a616-218">Patrones de error admitidos</span><span class="sxs-lookup"><span data-stu-id="1a616-218">Supported Error Patterns</span></span>

<span data-ttu-id="1a616-219">En la siguiente tabla, se describen los patrones que son compatibles con el uso de listas de puntos de conexión de reserva, junto con notas en las que se describen los detalles del control de errores de patrones específicos.</span><span class="sxs-lookup"><span data-stu-id="1a616-219">The following table describes the patterns that are compatible with the use of backup endpoint lists, along with notes describing the details of error handling for specific patterns.</span></span>

|<span data-ttu-id="1a616-220">Patrón</span><span class="sxs-lookup"><span data-stu-id="1a616-220">Pattern</span></span>|<span data-ttu-id="1a616-221">Sesión</span><span class="sxs-lookup"><span data-stu-id="1a616-221">Session</span></span>|<span data-ttu-id="1a616-222">Transacción</span><span class="sxs-lookup"><span data-stu-id="1a616-222">Transaction</span></span>|<span data-ttu-id="1a616-223">Contexto de recepción</span><span class="sxs-lookup"><span data-stu-id="1a616-223">Receive Context</span></span>|<span data-ttu-id="1a616-224">Lista de reserva admitida</span><span class="sxs-lookup"><span data-stu-id="1a616-224">Backup List Supported</span></span>|<span data-ttu-id="1a616-225">Notas</span><span class="sxs-lookup"><span data-stu-id="1a616-225">Notes</span></span>|
|-------------|-------------|-----------------|---------------------|---------------------------|-----------|
|<span data-ttu-id="1a616-226">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-226">One-Way</span></span>||||<span data-ttu-id="1a616-227">Sí</span><span class="sxs-lookup"><span data-stu-id="1a616-227">Yes</span></span>|<span data-ttu-id="1a616-228">Intenta reenviar el mensaje a un punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-228">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="1a616-229">Si este mensaje se envía por multidifusión, solo el mensaje del canal fallido se mueve a su destino de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-229">If this message is being multicast, only the message on the failed channel is moved to its backup destination.</span></span>|
|<span data-ttu-id="1a616-230">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-230">One-Way</span></span>||<span data-ttu-id="1a616-231">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-231">✔️</span></span>||<span data-ttu-id="1a616-232">No</span><span class="sxs-lookup"><span data-stu-id="1a616-232">No</span></span>|<span data-ttu-id="1a616-233">Se lanza una excepción y se deshace la transacción.</span><span class="sxs-lookup"><span data-stu-id="1a616-233">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="1a616-234">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-234">One-Way</span></span>|||<span data-ttu-id="1a616-235">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-235">✔️</span></span>|<span data-ttu-id="1a616-236">Sí</span><span class="sxs-lookup"><span data-stu-id="1a616-236">Yes</span></span>|<span data-ttu-id="1a616-237">Intenta reenviar el mensaje a un punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-237">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="1a616-238">Una vez recibido correctamente el mensaje, rellene todos los contextos de recepción.</span><span class="sxs-lookup"><span data-stu-id="1a616-238">After the message is successfully received, complete all receive contexts.</span></span> <span data-ttu-id="1a616-239">Si ninguno de los extremos recibe correctamente el mensaje, no rellene el contexto de recepción.</span><span class="sxs-lookup"><span data-stu-id="1a616-239">If the message is not successfully received by any endpoint, do not complete the receive context.</span></span><br /><br /> <span data-ttu-id="1a616-240">Cuando este mensaje se envía por multidifusión, el contexto de recepción solo se rellena si al menos un punto de conexión (principal o de reserva) recibe correctamente el mensaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-240">When this message is being multicast, the receive context is only completed if the message is successfully received by at least one endpoint (primary or backup).</span></span> <span data-ttu-id="1a616-241">Si ninguno de los puntos de conexión de las rutas de acceso de multidifusión recibe el mensaje correctamente, no rellene el contexto de recepción.</span><span class="sxs-lookup"><span data-stu-id="1a616-241">If none of the endpoints in any of the multicast paths successfully receive the message, do not complete the receive context.</span></span>|
|<span data-ttu-id="1a616-242">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-242">One-Way</span></span>||<span data-ttu-id="1a616-243">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-243">✔️</span></span>|<span data-ttu-id="1a616-244">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-244">✔️</span></span>|<span data-ttu-id="1a616-245">Sí</span><span class="sxs-lookup"><span data-stu-id="1a616-245">Yes</span></span>|<span data-ttu-id="1a616-246">Anule la transacción anterior, cree una transacción nueva y reenvíe todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="1a616-246">Abort the previous transaction, create a new transaction, and resend all messages.</span></span> <span data-ttu-id="1a616-247">Los mensajes que detectaron un error se transmiten a un destino de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="1a616-247">Messages that encountered an error are transmitted to a backup destination.</span></span><br /><br /> <span data-ttu-id="1a616-248">Una vez creada una transacción que realiza correctamente todas las transmisiones, rellene los contextos de recepción y confirme la transacción.</span><span class="sxs-lookup"><span data-stu-id="1a616-248">After a transaction has been created in which all transmissions succeed, complete the receive contexts and commit the transaction.</span></span>|
|<span data-ttu-id="1a616-249">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-249">One-Way</span></span>|<span data-ttu-id="1a616-250">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-250">✔️</span></span>|||<span data-ttu-id="1a616-251">Sí</span><span class="sxs-lookup"><span data-stu-id="1a616-251">Yes</span></span>|<span data-ttu-id="1a616-252">Intenta reenviar el mensaje a un punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-252">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="1a616-253">En un escenario de multidifusión solo se reenvían a destinos de reserva los mensajes de sesiones en las que se produjo un error o que no pudieron cerrarse.</span><span class="sxs-lookup"><span data-stu-id="1a616-253">In a multicast scenario only the messages in a session that encountered an error or in a session whose session close failed are resent to backup destinations.</span></span>|
|<span data-ttu-id="1a616-254">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-254">One-Way</span></span>|<span data-ttu-id="1a616-255">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-255">✔️</span></span>|<span data-ttu-id="1a616-256">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-256">✔️</span></span>||<span data-ttu-id="1a616-257">No</span><span class="sxs-lookup"><span data-stu-id="1a616-257">No</span></span>|<span data-ttu-id="1a616-258">Se lanza una excepción y se deshace la transacción.</span><span class="sxs-lookup"><span data-stu-id="1a616-258">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="1a616-259">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-259">One-Way</span></span>|<span data-ttu-id="1a616-260">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-260">✔️</span></span>||<span data-ttu-id="1a616-261">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-261">✔️</span></span>|<span data-ttu-id="1a616-262">Sí</span><span class="sxs-lookup"><span data-stu-id="1a616-262">Yes</span></span>|<span data-ttu-id="1a616-263">Intenta reenviar el mensaje a un punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-263">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="1a616-264">Una vez que todos los envíos de mensaje se realizan correctamente, la sesión indica que no hay más mensajes y el servicio de enrutamiento cierra todos los canales de sesión salientes, se rellenan todos los contextos de recepción y se cierra el canal de sesión entrante.</span><span class="sxs-lookup"><span data-stu-id="1a616-264">After all message sends complete without error, the session indicates no more messages and the Routing Service successfully closes all outbound session channel(s), all receive contexts are completed, and the inbound session channel is closed.</span></span>|
|<span data-ttu-id="1a616-265">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-265">One-Way</span></span>|<span data-ttu-id="1a616-266">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-266">✔️</span></span>|<span data-ttu-id="1a616-267">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-267">✔️</span></span>|<span data-ttu-id="1a616-268">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-268">✔️</span></span>|<span data-ttu-id="1a616-269">Sí</span><span class="sxs-lookup"><span data-stu-id="1a616-269">Yes</span></span>|<span data-ttu-id="1a616-270">Anule la transacción actual y cree una nueva.</span><span class="sxs-lookup"><span data-stu-id="1a616-270">Abort the current transaction and create a new one.</span></span> <span data-ttu-id="1a616-271">Reenvíe todos los mensajes anteriores de la sesión.</span><span class="sxs-lookup"><span data-stu-id="1a616-271">Resend all previous messages in the session.</span></span> <span data-ttu-id="1a616-272">Una vez que se crea una transacción en la que todos los mensajes se envían correctamente y la sesión indica que no hay más mensajes, se cierran todos los canales de sesión salientes, se rellenan todos los contextos de recepción con la transacción, se cierra el canal de sesión entrante y se confirma la transacción.</span><span class="sxs-lookup"><span data-stu-id="1a616-272">After a transaction has been created in which all messages have been successfully sent and the session indicates no more messages, all the outbound session channels are closed, receive contexts are all completed with the transaction, the inbound session channel is closed, and the transaction is committed.</span></span><br /><br /> <span data-ttu-id="1a616-273">Cuando las sesiones son de multidifusión, los mensajes que no produjeron errores se reenvían al mismo destino y los mensajes que sí los produjeron se envían a los destinos de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-273">When the sessions are being multicast the messages that had no error are resent to the same destination as before, and messages that encountered an error are sent to backup destinations.</span></span>|
|<span data-ttu-id="1a616-274">Bidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-274">Two-Way</span></span>||||<span data-ttu-id="1a616-275">Sí</span><span class="sxs-lookup"><span data-stu-id="1a616-275">Yes</span></span>|<span data-ttu-id="1a616-276">Realice un envío a un destino de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-276">Send to a backup destination.</span></span>  <span data-ttu-id="1a616-277">Una vez que el canal devuelve un mensaje de respuesta, devuelva la respuesta al cliente original.</span><span class="sxs-lookup"><span data-stu-id="1a616-277">After a channel returns a response message, return the response to the original client.</span></span>|
|<span data-ttu-id="1a616-278">Bidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-278">Two-Way</span></span>|<span data-ttu-id="1a616-279">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-279">✔️</span></span>|||<span data-ttu-id="1a616-280">Sí</span><span class="sxs-lookup"><span data-stu-id="1a616-280">Yes</span></span>|<span data-ttu-id="1a616-281">Envíe todos los mensajes del canal a un destino de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-281">Send all messages on the channel to a backup destination.</span></span>  <span data-ttu-id="1a616-282">Una vez que el canal devuelve un mensaje de respuesta, devuelva la respuesta al cliente original.</span><span class="sxs-lookup"><span data-stu-id="1a616-282">After a channel returns a response message, return the response to the original client.</span></span>|
|<span data-ttu-id="1a616-283">Bidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-283">Two-Way</span></span>||<span data-ttu-id="1a616-284">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-284">✔️</span></span>||<span data-ttu-id="1a616-285">No</span><span class="sxs-lookup"><span data-stu-id="1a616-285">No</span></span>|<span data-ttu-id="1a616-286">Se lanza una excepción y se deshace la transacción.</span><span class="sxs-lookup"><span data-stu-id="1a616-286">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="1a616-287">Bidireccional</span><span class="sxs-lookup"><span data-stu-id="1a616-287">Two-Way</span></span>|<span data-ttu-id="1a616-288">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-288">✔️</span></span>|<span data-ttu-id="1a616-289">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-289">✔️</span></span>||<span data-ttu-id="1a616-290">No</span><span class="sxs-lookup"><span data-stu-id="1a616-290">No</span></span>|<span data-ttu-id="1a616-291">Se lanza una excepción y se deshace la transacción.</span><span class="sxs-lookup"><span data-stu-id="1a616-291">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="1a616-292">Dúplex</span><span class="sxs-lookup"><span data-stu-id="1a616-292">Duplex</span></span>||||<span data-ttu-id="1a616-293">No</span><span class="sxs-lookup"><span data-stu-id="1a616-293">No</span></span>|<span data-ttu-id="1a616-294">Actualmente, no se admite una comunicación dúplex que no sea de sesiones.</span><span class="sxs-lookup"><span data-stu-id="1a616-294">Non-session duplex communication is not currently supported.</span></span>|
|<span data-ttu-id="1a616-295">Dúplex</span><span class="sxs-lookup"><span data-stu-id="1a616-295">Duplex</span></span>|<span data-ttu-id="1a616-296">✔️</span><span class="sxs-lookup"><span data-stu-id="1a616-296">✔️</span></span>|||<span data-ttu-id="1a616-297">Sí</span><span class="sxs-lookup"><span data-stu-id="1a616-297">Yes</span></span>|<span data-ttu-id="1a616-298">Realice un envío a un destino de reserva.</span><span class="sxs-lookup"><span data-stu-id="1a616-298">Send to a backup destination.</span></span>|

## <a name="hosting"></a><span data-ttu-id="1a616-299">Hospedaje</span><span class="sxs-lookup"><span data-stu-id="1a616-299">Hosting</span></span>

<span data-ttu-id="1a616-300">Dado que el servicio de enrutamiento se implementa como un servicio WCF, debe auto-hospedarse en una aplicación o ser hospedado por un servidor IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="1a616-300">Because the Routing Service is implemented as a WCF service, it must be either self-hosted within an application or hosted by IIS or WAS.</span></span> <span data-ttu-id="1a616-301">Se recomienda que el servicio de enrutamiento se hospede bien en un IIS, en un WAS o en una aplicación de un servicio Windows para que pueda aprovecharse de las características de administración de ciclo de vida y de inicio automático que están disponibles en estos entornos de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="1a616-301">It is recommended that the Routing Service be hosted in either IIS, WAS, or a Windows Service application to take advantage of the automatic start and life-cycle management features available in these hosting environments.</span></span>

<span data-ttu-id="1a616-302">En el siguiente ejemplo, se muestra cómo hospedar el servicio de enrutamiento en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="1a616-302">The following example demonstrates hosting the Routing Service in an application.</span></span>

```csharp
using (ServiceHost serviceHost =
                new ServiceHost(typeof(RoutingService)))
```

<span data-ttu-id="1a616-303">Para hospedar el servicio de enrutamiento dentro de un IIS o WAS, debe crear un archivo de servicio (.svc) o utilizar la activación basada en configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="1a616-303">To host the Routing Service within IIS or WAS, you must either create a service file (.svc) or use configuration-based activation of the service.</span></span> <span data-ttu-id="1a616-304">Al utilizar un archivo de servicio, debe especificar la clase <xref:System.ServiceModel.Routing.RoutingService> que utiliza el parámetro del servicio.</span><span class="sxs-lookup"><span data-stu-id="1a616-304">When using a service file, you must specify the <xref:System.ServiceModel.Routing.RoutingService> using the Service parameter.</span></span> <span data-ttu-id="1a616-305">El siguiente ejemplo contiene un archivo de servicio de ejemplo que se puede utilizar para hospedar el servicio de enrutamiento con IIS o WAS.</span><span class="sxs-lookup"><span data-stu-id="1a616-305">The following example contains a sample service file that can be used to host the Routing Service with IIS or WAS.</span></span>

```aspx-csharp
<%@ ServiceHost Language="C#" Debug="true" Service="System.ServiceModel.Routing.RoutingService,
     System.ServiceModel.Routing, version=4.0.0.0, Culture=neutral,
     PublicKeyToken=31bf3856ad364e35" %>
```

## <a name="routing-service-and-impersonation"></a><span data-ttu-id="1a616-306">Servicio de enrutamiento y suplantación</span><span class="sxs-lookup"><span data-stu-id="1a616-306">Routing Service and Impersonation</span></span>

<span data-ttu-id="1a616-307">El Servicio de enrutamiento de WCF se puede usar con suplantación para enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="1a616-307">The WCF Routing Service can be used with impersonation for both sending and receiving messages.</span></span> <span data-ttu-id="1a616-308">Todas las restricciones habituales de Windows de suplantación se aplican.</span><span class="sxs-lookup"><span data-stu-id="1a616-308">All of the usual Windows constraints of impersonation apply.</span></span> <span data-ttu-id="1a616-309">Si hubiera necesitado configurar permisos de servicio o de cuenta para usar la suplantación al escribir su propio servicio, tendría que realizar los mismos pasos para usar la suplantación con el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="1a616-309">If you would have needed to set up service or account permissions to use impersonation when writing your own service, then you’ll have to do those same steps to use impersonation with the routing service.</span></span> <span data-ttu-id="1a616-310">Para obtener más información, consulte [delegación y suplantación](delegation-and-impersonation-with-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="1a616-310">For more information, see [Delegation and Impersonation](delegation-and-impersonation-with-wcf.md).</span></span>

<span data-ttu-id="1a616-311">La suplantación con el servicio de enrutamiento necesita tanto el uso de la suplantación de ASP.NET mientras está en modo de compatibilidad de ASP.NET como el uso de credenciales de Windows que se han configurado para permitir la suplantación.</span><span class="sxs-lookup"><span data-stu-id="1a616-311">Impersonation with the routing service requires either the use of ASP.NET impersonation while in ASP.NET compatibility mode or the use of Windows credentials that have been configured to allow impersonation.</span></span> <span data-ttu-id="1a616-312">Para obtener más información sobre el modo de compatibilidad de ASP.NET, consulte [servicios WCF y ASP.net](wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="1a616-312">For more information about ASP.NET compatibility mode, see [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span></span>

> [!WARNING]
> <span data-ttu-id="1a616-313">El Servicio de enrutamiento de WCF no admite la suplantación con la autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="1a616-313">The WCF Routing Service does not support impersonation with basic authentication.</span></span>

<span data-ttu-id="1a616-314">Para usar la suplantación de ASP.NET con el servicio de enrutamiento, habilite el modo de compatibilidad de ASP.NET en el entorno de hospedaje del servicio.</span><span class="sxs-lookup"><span data-stu-id="1a616-314">To use ASP.NET impersonation with the routing service, enable ASP.NET compatibility mode on the service hosting environment.</span></span> <span data-ttu-id="1a616-315">El servicio de enrutamiento se ha ya marcado como que permite el modo de compatibilidad de ASP.NET y la suplantación se habilitará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="1a616-315">The routing service has already been marked as allowing ASP.NET compatibility mode and impersonation will automatically be enabled.</span></span> <span data-ttu-id="1a616-316">La suplantación es el único uso admitido de la integración de ASP.NET con el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="1a616-316">Impersonation is the only supported use of ASP.NET integration with the routing service.</span></span>

<span data-ttu-id="1a616-317">Para usar la suplantación de la credencial de Windows con el servicio de enrutamiento, necesita configurar las credenciales y el servicio.</span><span class="sxs-lookup"><span data-stu-id="1a616-317">To use Windows credential impersonation with the routing service you need to configure both the credentials and the service.</span></span> <span data-ttu-id="1a616-318">El objeto de credenciales de cliente (<xref:System.ServiceModel.Security.WindowsClientCredential>, accesible desde <xref:System.ServiceModel.ChannelFactory>) define una propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> que se debe establecer para permitir la suplantación.</span><span class="sxs-lookup"><span data-stu-id="1a616-318">The client credentials object (<xref:System.ServiceModel.Security.WindowsClientCredential>, accessable from the <xref:System.ServiceModel.ChannelFactory>) defines an <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> property that must be set to permit impersonation.</span></span> <span data-ttu-id="1a616-319">Finalmente, en el servicio se debe configurar el comportamiento <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> para establecer `ImpersonateCallerForAllOperations` en `true`.</span><span class="sxs-lookup"><span data-stu-id="1a616-319">Finally, on the service you need to configure the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> behavior to set `ImpersonateCallerForAllOperations` to `true`.</span></span> <span data-ttu-id="1a616-320">El servicio de enrutamiento usa esta marca para decidir si crear los clientes para reenviar mensajes con la suplantación habilitada.</span><span class="sxs-lookup"><span data-stu-id="1a616-320">The routing service uses this flag to decide whether to create the clients for forwarding messages with impersonation enabled.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a616-321">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a616-321">See also</span></span>

- [<span data-ttu-id="1a616-322">Filtros de mensajes</span><span class="sxs-lookup"><span data-stu-id="1a616-322">Message Filters</span></span>](message-filters.md)
- [<span data-ttu-id="1a616-323">Enrutar contratos</span><span class="sxs-lookup"><span data-stu-id="1a616-323">Routing Contracts</span></span>](routing-contracts.md)
- [<span data-ttu-id="1a616-324">Elegir un filtro</span><span class="sxs-lookup"><span data-stu-id="1a616-324">Choosing a Filter</span></span>](choosing-a-filter.md)
