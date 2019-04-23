---
title: Cómo Control de errores
ms.date: 03/30/2017
ms.assetid: de566e39-9358-44ff-8244-780f6b799966
ms.openlocfilehash: 3752e358230b76d8984fa8e6a2ded43ad0eb2c6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979399"
---
# <a name="how-to-error-handling"></a><span data-ttu-id="ddbf9-102">Cómo Control de errores</span><span class="sxs-lookup"><span data-stu-id="ddbf9-102">How To: Error Handling</span></span>
<span data-ttu-id="ddbf9-103">Este tema describe los pasos básicos necesarios para crear una configuración de enrutamiento que utiliza el control de errores.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-103">This topic outlines the basic steps required to create a routing configuration that uses error handling.</span></span> <span data-ttu-id="ddbf9-104">En este ejemplo, los mensajes se enrutan a un punto de conexión de destino.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-104">In this example, messages are routed to a destination endpoint.</span></span> <span data-ttu-id="ddbf9-105">Si un mensaje no se puede entregar debido a un error de la red o relacionado con las comunicaciones (<xref:System.ServiceModel.CommunicationException>), el mensaje se reenvía a un punto de conexión alternativo.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-105">If a message cannot be delivered due to a network or communications-related failure (<xref:System.ServiceModel.CommunicationException>), the message is resent to an alternate endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddbf9-106">Para simular un error de la red, el punto de conexión de destino utilizado en este ejemplo contiene una dirección incorrecta.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-106">To simulate a network failure, the destination endpoint used in this example contains an incorrect address.</span></span> <span data-ttu-id="ddbf9-107">Se produce un error en los mensajes enrutados a este extremo, ya que ningún servicio está realizando escuchas en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-107">Messages routed to this endpoint fail as no service is listening on the specified address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddbf9-108">Aunque el ejemplo incluido en este tema no describe la configuración de tiempo de espera explícitamente, debe tenerla en cuenta al utilizar el control de errores.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-108">While the example contained in this topic does not explicitly discuss time-out settings, you must take these into consideration when using error handling.</span></span> <span data-ttu-id="ddbf9-109">Cuando se detectan errores, se detectará un retraso adicional antes de que el cliente reciba una respuesta.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-109">When errors are encountered, there will be an additional delay encountered before the client receives a response.</span></span> <span data-ttu-id="ddbf9-110">Esto se debe a que el error se recibe en el servicio de enrutamiento, que, a continuación, intenta enviar el mensaje a un punto de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-110">This is because the error is received at the Routing Service, which then attempts to send the message to a backup endpoint.</span></span> <span data-ttu-id="ddbf9-111">Si los valores de tiempo de espera asociados a los puntos de conexión de destino de reserva y primarios son grandes, el cliente podría experimentar un retraso largo mientras el mensaje conmuta por error en varios puntos de conexión de la lista de reserva antes de enviarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-111">If the time-out values associated with the primary and backup destination endpoints are large, the client could experience a long delay as the message fails over multiple endpoints in the backup list before being successfully sent.</span></span>  
>   
>  <span data-ttu-id="ddbf9-112">Como el servicio de enrutamiento podría encontrarse con un retraso máximo igual a la suma del valor de tiempo de espera de todos los extremos asociados a un filtro, recomendamos aumentar el tiempo de espera esperado en el cliente de forma correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-112">Since the Routing Service could encounter a maximum delay equal to the sum of the time-out value for all endpoints associated with a filter, we recommend that you increase the expected time-out at the client accordingly.</span></span>  
  
### <a name="implement-error-handling"></a><span data-ttu-id="ddbf9-113">Implementación del control de errores</span><span class="sxs-lookup"><span data-stu-id="ddbf9-113">Implement Error Handling</span></span>  
  
1. <span data-ttu-id="ddbf9-114">Cree la configuración de servicio de enrutamiento básica especificando el extremo de servicio expuesto por el servicio.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-114">Create the basic Routing Service configuration by specifying the service endpoint exposed by the service.</span></span> <span data-ttu-id="ddbf9-115">En el siguiente ejemplo, se define un punto de conexión de servicio único que se utilizará para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-115">The following example defines a single service endpoint, which is used to receive messages.</span></span> <span data-ttu-id="ddbf9-116">También se definen los extremos de cliente que se utilizan para enviar mensajes; deadDestination y realDestination.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-116">It also defines the client endpoints that are used to send messages; deadDestination and realDestination.</span></span> <span data-ttu-id="ddbf9-117">El punto de conexión deadDestination contiene una dirección que no hace referencia a un servicio en ejecución y que se utiliza para simular un error de la red al enviar mensajes a este punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-117">The deadDestination endpoint contains an address that does not reference a running service and is used to simulate a network failure when sending messages to this endpoint.</span></span>  
  
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
  
2. <span data-ttu-id="ddbf9-118">Defina los filtros usados para enrutar mensajes a los extremos del destino.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-118">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="ddbf9-119">Para este ejemplo, se emplea un filtro MatchAll para coincidir con todos los mensajes recibidos por el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-119">For this example, a MatchAll filter is used to match all messages received by the Routing Service.</span></span>  
  
    ```xml  
    <filters>  
      <!-- Create a MatchAll filter which will catch all messages -->  
      <filter name="MatchAllFilter1" filterType="MatchAll" />  
    </filters>  
    ```  
  
3. <span data-ttu-id="ddbf9-120">Defina la lista de puntos de conexión de reserva, que contiene los puntos de conexión a los que se envía un mensaje en caso de que se produzca un error de la red o de comunicaciones durante un envío al punto de conexión de destino primario.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-120">Define the backup endpoint list, which contains the endpoints that a message is sent to in the event of a network or communications failure when sending to the primary destination endpoint.</span></span> <span data-ttu-id="ddbf9-121">En el siguiente ejemplo, se define una lista de reserva que contiene un extremo; sin embargo, se pueden especificar varios extremos en una lista de reserva.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-121">The following example defines a backup list that contains one endpoint; however, multiple endpoints can be specified in a backup list.</span></span>  
  
     <span data-ttu-id="ddbf9-122">Si la lista de reserva contiene varios puntos de conexión, cuando se produce un error de la red o de comunicaciones, el servicio de enrutamiento intenta enviar el mensaje al primer punto de conexión de la lista.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-122">If the backup list contains multiple endpoints, when a network or communications failure occurs the Routing Service attempts to send the message to the first endpoint in the list.</span></span> <span data-ttu-id="ddbf9-123">Si se produce un error de la red o de comunicaciones al realizar el envío a este extremo, el servicio de enrutamiento intenta enviar el mensaje al extremo siguiente incluido en la lista.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-123">If a network or communications failure occurs when sending to this endpoint, the Routing Service attempts to send the message to the next endpoint contained in the list.</span></span> <span data-ttu-id="ddbf9-124">El servicio sigue enviando el mensaje a cada punto de conexión de la lista de puntos de conexión de reserva hasta que el mensaje se envía correctamente, todos los puntos de conexión de reserva devuelven un error de la red o de comunicaciones, o se envía el mensaje y el punto de conexión devuelve un error de ausencia de red no relacionado con las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-124">The service continues sending the message to each endpoint in the backup endpoint list until the message is successfully sent, all backup endpoints return a network or communications-related error, or the message is sent and the endpoint returns a non-network, non-communications-related error.</span></span>  
  
    ```xml  
    <backupLists>          
      <backupList name="backupEndpointList">  
          <add endpointName="realDestination" />  
      </backupList>  
    </backupLists>  
    ```  
  
4. <span data-ttu-id="ddbf9-125">Defina la tabla de filtros, que asocia el filtro al punto de conexión deadDestination y a la lista de puntos de conexión de reserva.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-125">Define the filter table, which associates the filter with the deadDestination endpoint and the backup endpoint list.</span></span>  <span data-ttu-id="ddbf9-126">El servicio de enrutamiento intenta enviar primero el mensaje al punto de conexión de destino asociado al filtro.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-126">The Routing Service first attempts to send the message to the destination endpoint associated with the filter.</span></span> <span data-ttu-id="ddbf9-127">Como deadDestination contiene una dirección que no hace referencia a un servicio en ejecución, esto produce un error de la red.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-127">Since the deadDestination contains an address that does not refer to a running service, this results in a network error.</span></span> <span data-ttu-id="ddbf9-128">A continuación, el servicio de enrutamiento intenta enviar el mensaje al punto de conexión especificado en backupEndpointlist.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-128">The Routing Service then attempts to send the message to the endpoint specified in the backupEndpointlist.</span></span>  
  
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
  
5. <span data-ttu-id="ddbf9-129">Para evaluar los mensajes entrantes con respecto al filtro incluido en la tabla de filtros, debe asociar la tabla de filtros a los puntos de conexión de servicio mediante el comportamiento de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-129">To evaluate incoming messages against the filter contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span>  <span data-ttu-id="ddbf9-130">El ejemplo siguiente se muestra cómo asociar "filterTable1" a los puntos de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-130">The following example demonstrates associating "filterTable1" with the service endpoints.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="ddbf9-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ddbf9-131">Example</span></span>  
 <span data-ttu-id="ddbf9-132">A continuación, se muestra una lista completa del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ddbf9-132">Following is a complete listing of the configuration file.</span></span>  
  
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
