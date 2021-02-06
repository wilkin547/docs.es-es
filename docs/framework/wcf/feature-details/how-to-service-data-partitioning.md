---
description: 'Más información acerca de cómo: crear particiones de datos de servicio'
title: Cómo Particionar datos de servicio
ms.date: 03/30/2017
ms.assetid: 1ccff72e-d76b-4e36-93a2-e51f7b32dc83
ms.openlocfilehash: fd40ee37a80a8d5039231c6efe6369006022afad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643246"
---
# <a name="how-to-service-data-partitioning"></a><span data-ttu-id="edfd0-103">Cómo Particionar datos de servicio</span><span class="sxs-lookup"><span data-stu-id="edfd0-103">How To: Service Data Partitioning</span></span>

<span data-ttu-id="edfd0-104">Este tema describe los pasos básicos necesarios para realizar particiones de los mensajes en múltiples instancias de un mismo servicio de destino.</span><span class="sxs-lookup"><span data-stu-id="edfd0-104">This topic outlines the basic steps required to partition messages across multiple instances of the same destination service.</span></span> <span data-ttu-id="edfd0-105">La partición de datos de servicio se suele utilizar cuando hay que ajustar un servicio para proporcionar una mayor calidad del servicio, o cuando hay que administrar solicitudes de diversos clientes de una manera determinada.</span><span class="sxs-lookup"><span data-stu-id="edfd0-105">Service data partitioning is typically used when you need to scale a service in order to provide better quality of service, or when you need to handle requests from different customers in a specific way.</span></span> <span data-ttu-id="edfd0-106">Por ejemplo, es posible que los mensajes de clientes de gran valor o "oro" deban procesarse con una prioridad más alta que los mensajes de un cliente estándar.</span><span class="sxs-lookup"><span data-stu-id="edfd0-106">For example, messages from high value or "Gold" customers may need to be processed at a higher priority than messages from a standard customer.</span></span>  
  
 <span data-ttu-id="edfd0-107">En este ejemplo, los mensajes se enrutan a una de las dos instancias del servicio de regularCalc.</span><span class="sxs-lookup"><span data-stu-id="edfd0-107">In this example, messages are routed to one of two instances of the regularCalc service.</span></span> <span data-ttu-id="edfd0-108">Ambas instancias del servicio son idénticas; sin embargo, el servicio representado por el extremo de calculator1 procesa mensajes recibidos de los clientes importantes, y el extremo de calculator2 procesa los mensajes de otros clientes.</span><span class="sxs-lookup"><span data-stu-id="edfd0-108">Both instances of the service are identical; however the service represented by the calculator1 endpoint processes messages received from high value customers, the calculator 2 endpoint processes messages from other customers</span></span>  
  
 <span data-ttu-id="edfd0-109">El mensaje enviado del cliente no tiene ningún dato único que se pueda usar para identificar a qué instancia de servicio debería enrutarse el mensaje.</span><span class="sxs-lookup"><span data-stu-id="edfd0-109">The message sent from the client does not have any unique data that can be used to identify which service instance the message should be routed to.</span></span> <span data-ttu-id="edfd0-110">Para permitir que cada cliente enrute datos a un destino concreto, implementaremos dos puntos de conexión de servicio que se usarán para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="edfd0-110">To allow each client to route data to a specific destination service we will implement two service endpoints that will be used to receive messages.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="edfd0-111">Aunque este ejemplo utiliza puntos de conexión concretos para crear una partición de los datos, esto también se puede lograr mediante la información incluida en el propio mensaje, como el encabezado o la información del cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="edfd0-111">While this example uses specific endpoints to partition data, this could also be accomplished using information contained within the message itself such as header or body data.</span></span>  
  
### <a name="implement-service-data-partitioning"></a><span data-ttu-id="edfd0-112">Implementación de partición de datos de servicio</span><span class="sxs-lookup"><span data-stu-id="edfd0-112">Implement Service Data Partitioning</span></span>  
  
1. <span data-ttu-id="edfd0-113">Cree la configuración de servicio de enrutamiento básica especificando los extremos de servicio expuestos por el servicio.</span><span class="sxs-lookup"><span data-stu-id="edfd0-113">Create the basic Routing Service configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="edfd0-114">En el siguiente ejemplo, se definen dos puntos de conexión que se utilizarán para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="edfd0-114">The following example defines two endpoints, which will be used to receive messages.</span></span> <span data-ttu-id="edfd0-115">También se definen los puntos de conexión del cliente, que se utilizan para enviar mensajes a las instancias de servicio de regularCalc.</span><span class="sxs-lookup"><span data-stu-id="edfd0-115">It also defines the client endpoints, which are used to send messages to the regularCalc service instances.</span></span>  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoints for the Routing Service-->  
        <!--create the endpoints for the calculator service-->  
        <endpoint address="calculator1"  
                  binding="wsHttpBinding"  
                  name="calculator1Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <endpoint address="calculator2"  
                  binding="wsHttpBinding"  
                  name="calculator2Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
       </service>  
    </services>  
    <client>  
    <!--set up the destination endpoints-->  
        <endpoint name="CalcEndpoint1"  
                  address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                  binding="netTcpBinding"  
                  contract="*" />  
  
        <endpoint name="CalcEndpoint2"  
                  address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                  binding="netTcpBinding"  
                  contract="*" />  
     </client>  
    ```  
  
2. <span data-ttu-id="edfd0-116">Defina los filtros usados para enrutar mensajes a los extremos del destino.</span><span class="sxs-lookup"><span data-stu-id="edfd0-116">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="edfd0-117">En este ejemplo, se usa el filtro EndpointName para determinar qué punto de conexión de servicio recibe el mensaje.</span><span class="sxs-lookup"><span data-stu-id="edfd0-117">For this example, the EndpointName filter is used to determine which service endpoint received the message.</span></span> <span data-ttu-id="edfd0-118">En el siguiente ejemplo, se definen los filtros y la sección de enrutamiento necesarios.</span><span class="sxs-lookup"><span data-stu-id="edfd0-118">The following example defines the necessary routing section and filters.</span></span>  
  
    ```xml  
    <filters>  
      <!--define the different message filters-->  
      <!--define endpoint name filters looking for messages that show up on the virtual endpoints-->  
      <filter name="HighPriority" filterType="EndpointName"  
              filterData="calculator1Endpoint"/>  
      <filter name="NormalPriority" filterType="EndpointName"  
              filterData="calculator2Endpoint"/>  
    </filters>  
    ```  
  
3. <span data-ttu-id="edfd0-119">Defina la tabla de filtro, que asocia cada filtro a un punto de conexión del cliente.</span><span class="sxs-lookup"><span data-stu-id="edfd0-119">Define the filter table, which associates each filter with a client endpoint.</span></span> <span data-ttu-id="edfd0-120">En este ejemplo, el mensaje se enrutará según el punto de conexión concreto en el que se recibió.</span><span class="sxs-lookup"><span data-stu-id="edfd0-120">In this example, the message will be routed based on the specific endpoint it was received over.</span></span> <span data-ttu-id="edfd0-121">Como el mensaje solo puede coincidir con uno de los dos posibles filtros, no hay necesidad de utilizar la prioridad del filtro para controlar el orden en el que se evalúan los filtros.</span><span class="sxs-lookup"><span data-stu-id="edfd0-121">Since the message can only match one of the two possible filters, there is no need for using filter priority to control to the order in which filters are evaluated.</span></span>  
  
     <span data-ttu-id="edfd0-122">El procedimiento siguiente define la tabla de filtros y agrega los filtros definidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="edfd0-122">The following defines the filter table and adds the filters defined earlier.</span></span>  
  
    ```xml  
    <filterTables>  
       <filterTable name="filterTable1">  
         <!--add the filters to the message filter table-->  
         <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
         <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
       </filterTable>  
    </filterTables>  
    ```  
  
4. <span data-ttu-id="edfd0-123">Para evaluar los mensajes entrantes con respecto a los filtros incluidos en la tabla, debe asociar la tabla de filtros a los puntos de conexión de servicio mediante el comportamiento de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="edfd0-123">To evaluate incoming messages against the filters contained in the table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="edfd0-124">En el ejemplo siguiente se muestra cómo asociar "filterTable1" a los puntos de conexión de servicio:</span><span class="sxs-lookup"><span data-stu-id="edfd0-124">The following example demonstrates associating "filterTable1" with the service endpoints:</span></span>  
  
    ```xml  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a><span data-ttu-id="edfd0-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="edfd0-125">Example</span></span>  

 <span data-ttu-id="edfd0-126">A continuación, se muestra una lista completa del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="edfd0-126">The following is a complete listing of the configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation. All rights reserved -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoints for the Routing Service-->  
        <!--create the endpoints for the calculator service-->  
        <endpoint address="calculator1"  
                  binding="wsHttpBinding"  
                  name="calculator1Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <endpoint address="calculator2"  
                  binding="wsHttpBinding"  
                  name="calculator2Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
  
      </service>  
    </services>  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    <client>  
<!--set up the destination endpoints-->  
      <endpoint name="CalcEndpoint1"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="CalcEndpoint2"  
                address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
  
      <filters>  
        <!--define the different message filters-->  
        <!--define endpoint name filters looking for messages that show up on the virtual endpoints-->  
        <filter name="HighPriority" filterType="EndpointName"  
                filterData="calculator1Endpoint"/>  
        <filter name="NormalPriority" filterType="EndpointName"  
                filterData="calculator2Endpoint"/>  
      </filters>  
  
      <filterTables>  
        <filterTable name="filterTable1">  
          <!--add the filters to the message filter table-->  
          <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
          <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
        </filterTable>  
      </filterTables>  
  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="edfd0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="edfd0-127">See also</span></span>

- [<span data-ttu-id="edfd0-128">Servicios de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="edfd0-128">Routing Services</span></span>](../samples/routing-services.md)
