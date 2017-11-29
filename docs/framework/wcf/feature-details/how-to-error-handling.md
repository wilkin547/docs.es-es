---
title: "Cómo: Control de errores"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de566e39-9358-44ff-8244-780f6b799966
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 5bcab65eb98684820a84968f15ba80de3c5b60de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-error-handling"></a><span data-ttu-id="0a806-102">Cómo: Control de errores</span><span class="sxs-lookup"><span data-stu-id="0a806-102">How To: Error Handling</span></span>
<span data-ttu-id="0a806-103">Este tema describe los pasos básicos necesarios para crear una configuración de enrutamiento que utiliza el control de errores.</span><span class="sxs-lookup"><span data-stu-id="0a806-103">This topic outlines the basic steps required to create a routing configuration that uses error handling.</span></span> <span data-ttu-id="0a806-104">En este ejemplo, los mensajes se enrutan a un extremo de destino.</span><span class="sxs-lookup"><span data-stu-id="0a806-104">In this example, messages are routed to a destination endpoint.</span></span> <span data-ttu-id="0a806-105">Si un mensaje no se puede entregar debido a un error de la red o relacionado con las comunicaciones (<xref:System.ServiceModel.CommunicationException>), el mensaje se reenvía a un extremo alternativo.</span><span class="sxs-lookup"><span data-stu-id="0a806-105">If a message cannot be delivered due to a network or communications-related failure (<xref:System.ServiceModel.CommunicationException>), the message is resent to an alternate endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a806-106">Para simular un error de la red, el extremo de destino utilizado en este ejemplo contiene una dirección incorrecta.</span><span class="sxs-lookup"><span data-stu-id="0a806-106">To simulate a network failure, the destination endpoint used in this example contains an incorrect address.</span></span> <span data-ttu-id="0a806-107">Se produce un error en los mensajes enrutados a este extremo, ya que ningún servicio está realizando escuchas en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="0a806-107">Messages routed to this endpoint fail as no service is listening on the specified address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a806-108">Aunque el ejemplo incluido en este tema no describe la configuración de tiempo de espera explícitamente, debe tenerla en cuenta al utilizar el control de errores.</span><span class="sxs-lookup"><span data-stu-id="0a806-108">While the example contained in this topic does not explicitly discuss time-out settings, you must take these into consideration when using error handling.</span></span> <span data-ttu-id="0a806-109">Cuando se detectan errores, se detectará un retraso adicional antes de que el cliente reciba una respuesta.</span><span class="sxs-lookup"><span data-stu-id="0a806-109">When errors are encountered, there will be an additional delay encountered before the client receives a response.</span></span> <span data-ttu-id="0a806-110">Esto se debe a que el error se recibe en el servicio de enrutamiento, que, a continuación, intenta enviar el mensaje a un extremo de reserva.</span><span class="sxs-lookup"><span data-stu-id="0a806-110">This is because the error is received at the Routing Service, which then attempts to send the message to a backup endpoint.</span></span> <span data-ttu-id="0a806-111">Si los valores de tiempo de espera asociados a los extremos de destino de reserva y primarios son grandes, el cliente podría experimentar un retraso largo mientras el mensaje conmuta por error en varios extremos de la lista de reserva antes de enviarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="0a806-111">If the time-out values associated with the primary and backup destination endpoints are large, the client could experience a long delay as the message fails over multiple endpoints in the backup list before being successfully sent.</span></span>  
>   
>  <span data-ttu-id="0a806-112">Como el servicio de enrutamiento podría encontrarse con un retraso máximo igual a la suma del valor de tiempo de espera de todos los extremos asociados a un filtro, recomendamos aumentar el tiempo de espera esperado en el cliente de forma correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0a806-112">Since the Routing Service could encounter a maximum delay equal to the sum of the time-out value for all endpoints associated with a filter, we recommend that you increase the expected time-out at the client accordingly.</span></span>  
  
### <a name="implement-error-handling"></a><span data-ttu-id="0a806-113">Implementación del control de errores</span><span class="sxs-lookup"><span data-stu-id="0a806-113">Implement Error Handling</span></span>  
  
1.  <span data-ttu-id="0a806-114">Cree la configuración de servicio de enrutamiento básica especificando el extremo de servicio expuesto por el servicio.</span><span class="sxs-lookup"><span data-stu-id="0a806-114">Create the basic Routing Service configuration by specifying the service endpoint exposed by the service.</span></span> <span data-ttu-id="0a806-115">En el siguiente ejemplo, se define un extremo de servicio único que se utilizará para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="0a806-115">The following example defines a single service endpoint, which is used to receive messages.</span></span> <span data-ttu-id="0a806-116">También se definen los extremos de cliente que se utilizan para enviar mensajes; deadDestination y realDestination.</span><span class="sxs-lookup"><span data-stu-id="0a806-116">It also defines the client endpoints that are used to send messages; deadDestination and realDestination.</span></span> <span data-ttu-id="0a806-117">El extremo deadDestination contiene una dirección que no hace referencia a un servicio en ejecución y que se utiliza para simular un error de la red al enviar mensajes a este extremo.</span><span class="sxs-lookup"><span data-stu-id="0a806-117">The deadDestination endpoint contains an address that does not reference a running service and is used to simulate a network failure when sending messages to this endpoint.</span></span>  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/" />  
          </baseAddresses>  
        </host>  
        <!-- Create the Routing Service endpoint -->  
        <endpoint address="router"  
                  binding="basicHttpBinding"  
                  name="RoutingServiceEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
  
    <!-- Create the destination endpoints that we want to send to -->  
    <client>  
      <!-- Create a dummy endpoint that we know will be down -->  
      <endpoint name="deadDestination"   
                address="net.tcp://localhost:9090/servicemodelsamples/fakeDestination"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <!-- Now create the real service endpoint -->  
      <endpoint name="realDestination"   
                address="net.tcp://localhost:8080/servicemodelsamples/service"  
                binding="netTcpBinding"   
                contract="*" />  
    </client>  
    ```  
  
2.  <span data-ttu-id="0a806-118">Defina los filtros usados para enrutar mensajes a los extremos del destino.</span><span class="sxs-lookup"><span data-stu-id="0a806-118">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="0a806-119">Para este ejemplo, se emplea un filtro MatchAll para coincidir con todos los mensajes recibidos por el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0a806-119">For this example, a MatchAll filter is used to match all messages received by the Routing Service.</span></span>  
  
    ```xml  
    <filters>  
      <!-- Create a MatchAll filter which will catch all messages -->  
      <filter name="MatchAllFilter1" filterType="MatchAll" />  
    </filters>  
    ```  
  
3.  <span data-ttu-id="0a806-120">Defina la lista de extremos de reserva, que contiene los extremos a los que se envía un mensaje en caso de que se produzca un error de la red o de comunicaciones durante un envío al extremo de destino primario.</span><span class="sxs-lookup"><span data-stu-id="0a806-120">Define the backup endpoint list, which contains the endpoints that a message is sent to in the event of a network or communications failure when sending to the primary destination endpoint.</span></span> <span data-ttu-id="0a806-121">En el siguiente ejemplo, se define una lista de reserva que contiene un extremo; sin embargo, se pueden especificar varios extremos en una lista de reserva.</span><span class="sxs-lookup"><span data-stu-id="0a806-121">The following example defines a backup list that contains one endpoint; however, multiple endpoints can be specified in a backup list.</span></span>  
  
     <span data-ttu-id="0a806-122">Si la lista de reserva contiene varios extremos, cuando se produce un error de la red o de comunicaciones, el servicio de enrutamiento intenta enviar el mensaje al primer extremo de la lista.</span><span class="sxs-lookup"><span data-stu-id="0a806-122">If the backup list contains multiple endpoints, when a network or communications failure occurs the Routing Service attempts to send the message to the first endpoint in the list.</span></span> <span data-ttu-id="0a806-123">Si se produce un error de la red o de comunicaciones al realizar el envío a este extremo, el servicio de enrutamiento intenta enviar el mensaje al extremo siguiente incluido en la lista.</span><span class="sxs-lookup"><span data-stu-id="0a806-123">If a network or communications failure occurs when sending to this endpoint, the Routing Service attempts to send the message to the next endpoint contained in the list.</span></span> <span data-ttu-id="0a806-124">El servicio sigue enviando el mensaje a cada extremo de la lista de extremos de reserva hasta que el mensaje se envía correctamente, todos los extremos de reserva devuelven un error de la red o de comunicaciones, o se envía el mensaje y el extremo devuelve un error de ausencia de red no relacionado con las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="0a806-124">The service continues sending the message to each endpoint in the backup endpoint list until the message is successfully sent, all backup endpoints return a network or communications-related error, or the message is sent and the endpoint returns a non-network, non-communications-related error.</span></span>  
  
    ```xml  
    <backupLists>          
      <backupList name="backupEndpointList">  
          <add endpointName="realDestination" />  
      </backupList>  
    </backupLists>  
    ```  
  
4.  <span data-ttu-id="0a806-125">Defina la tabla de filtros, que asocia el filtro al extremo deadDestination y a la lista de extremos de reserva.</span><span class="sxs-lookup"><span data-stu-id="0a806-125">Define the filter table, which associates the filter with the deadDestination endpoint and the backup endpoint list.</span></span>  <span data-ttu-id="0a806-126">El servicio de enrutamiento intenta enviar primero el mensaje al extremo de destino asociado al filtro.</span><span class="sxs-lookup"><span data-stu-id="0a806-126">The Routing Service first attempts to send the message to the destination endpoint associated with the filter.</span></span> <span data-ttu-id="0a806-127">Como deadDestination contiene una dirección que no hace referencia a un servicio en ejecución, esto produce un error de la red.</span><span class="sxs-lookup"><span data-stu-id="0a806-127">Since the deadDestination contains an address that does not refer to a running service, this results in a network error.</span></span> <span data-ttu-id="0a806-128">A continuación, el servicio de enrutamiento intenta enviar el mensaje al extremo especificado en backupEndpointlist.</span><span class="sxs-lookup"><span data-stu-id="0a806-128">The Routing Service then attempts to send the message to the endpoint specified in the backupEndpointlist.</span></span>  
  
    ```xml  
    <filterTables>  
            <!-- Set up the Routing Service's Message Filter Table -->  
            <filterTable name="filterTable1">  
                <!-- Add an entity that maps the MatchAllMessageFilter to the dead destination -->  
                <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
                <!-- Listed in the backupEndpointList -->  
                <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
            </filterTable>  
          </filterTables>  
    ```  
  
5.  <span data-ttu-id="0a806-129">Para evaluar los mensajes entrantes con respecto al filtro incluido en la tabla de filtros, debe asociar la tabla de filtros a los puntos de conexión de servicio mediante el comportamiento de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="0a806-129">To evaluate incoming messages against the filter contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span>  <span data-ttu-id="0a806-130">En el ejemplo siguiente se muestra cómo asociar "filterTable1" a los extremos de servicio.</span><span class="sxs-lookup"><span data-stu-id="0a806-130">The following example demonstrates associating "filterTable1" with the service endpoints.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <!-- Set up the Routing Behavior -->  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a><span data-ttu-id="0a806-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0a806-131">Example</span></span>  
 <span data-ttu-id="0a806-132">A continuación, se muestra una lista completa del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0a806-132">Following is a complete listing of the configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/" />  
          </baseAddresses>  
        </host>  
        <!-- Create the Routing Service endpoint -->  
        <endpoint address="router"  
                  binding="basicHttpBinding"  
                  name="RoutingServiceEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <!-- Set up the Routing Behavior -->  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <!-- Create the destination endpoints that we want to send to -->  
    <client>  
      <!-- Create a dummy endpoint that we know will be down -->  
      <endpoint name="deadDestination"   
                address="net.tcp://localhost:9090/servicemodelsamples/fakeDestination"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <!-- Now create the real service endpoint -->  
      <endpoint name="realDestination"   
                address="net.tcp://localhost:8080/servicemodelsamples/service"  
                binding="netTcpBinding"   
                contract="*" />  
    </client>  
    <routing>  
      <filters>  
        <!-- Create a MatchAll filter which will catch all messages -->  
        <filter name="MatchAllFilter1" filterType="MatchAll" />  
      </filters>  
      <filterTables>  
        <!-- Set up the Routing Service's Message Filter Table -->  
        <filterTable name="filterTable1">  
            <!-- Add an entrty that maps the MatchAllMessageFilter to the dead destination -->  
            <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
            <!-- Listed in the backupEndpointList -->  
            <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
        </filterTable>  
      </filterTables>  
      <!-- Create the backup endpoint list -->  
      <backupLists>          
        <backupList name="backupEndpointList">  
            <add endpointName="realDestination" />  
        </backupList>  
      </backupLists>  
      </routing>  
  </system.serviceModel>  
</configuration>  
```
