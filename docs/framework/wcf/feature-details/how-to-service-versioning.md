---
title: Cómo Control de versiones del servicio
ms.date: 03/30/2017
ms.assetid: 4287b6b3-b207-41cf-aebe-3b1d4363b098
ms.openlocfilehash: f1178a0bedfe8665d7b3ec463e99183809538c28
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464111"
---
# <a name="how-to-service-versioning"></a><span data-ttu-id="80597-102">Cómo Control de versiones del servicio</span><span class="sxs-lookup"><span data-stu-id="80597-102">How To: Service Versioning</span></span>
<span data-ttu-id="80597-103">Este tema describe los pasos básicos necesarios para crear una configuración de enrutamiento que enrute mensajes a las diferentes versiones del mismo servicio.</span><span class="sxs-lookup"><span data-stu-id="80597-103">This topic outlines the basic steps required to create a routing configuration that routes messages to different versions of the same service.</span></span> <span data-ttu-id="80597-104">En este ejemplo, los mensajes se enrutan a dos versiones diferentes de un servicio de la calculadora, `roundingCalc` (v1) y `regularCalc` (v2).</span><span class="sxs-lookup"><span data-stu-id="80597-104">In this example, messages are routed to two different versions of a calculator service, `roundingCalc` (v1) and `regularCalc` (v2).</span></span> <span data-ttu-id="80597-105">Ambas implementaciones admiten las mismas operaciones; sin embargo, el servicio más antiguo, `roundingCalc`, redondea todos los cálculos al valor entero más cercano antes de devolverlos.</span><span class="sxs-lookup"><span data-stu-id="80597-105">Both implementations support the same operations; however the older service, `roundingCalc`, rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="80597-106">Una aplicación cliente debe poder indicar cuándo se debe usar el servicio `regularCalc` más reciente.</span><span class="sxs-lookup"><span data-stu-id="80597-106">A client application must be able to indicate whether to use the newer `regularCalc` service.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="80597-107">Para enrutar un mensaje a una versión de servicio concreta, el servicio de enrutamiento debe poder determinar el destino del mensaje en función del contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="80597-107">In order to route a message to a specific service version, the Routing Service must be able to determine the message destination based on the message content.</span></span> <span data-ttu-id="80597-108">En el método mostrado a continuación, el cliente especificará la versión insertando información en un encabezado del mensaje.</span><span class="sxs-lookup"><span data-stu-id="80597-108">In the method demonstrated below, the client will specify the version by inserting information into a message header.</span></span> <span data-ttu-id="80597-109">Existen métodos de control de versiones del servicio que no requieren que los clientes pasen datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="80597-109">There are methods of service versioning that do not require clients to pass additional data.</span></span> <span data-ttu-id="80597-110">Por ejemplo, un mensaje se podría enrutar a la versión más reciente o más compatible de un servicio, o el enrutador podría usar una parte del sobre SOAP estándar.</span><span class="sxs-lookup"><span data-stu-id="80597-110">For example, a message could be routed to the most recent or most compatible version of a service or the router could use a part of the standard SOAP envelope.</span></span>  
  
 <span data-ttu-id="80597-111">Las operaciones expuestas por ambos servicios son:</span><span class="sxs-lookup"><span data-stu-id="80597-111">The operations exposed by both services are:</span></span>  
  
- <span data-ttu-id="80597-112">Sumar</span><span class="sxs-lookup"><span data-stu-id="80597-112">Add</span></span>  
  
- <span data-ttu-id="80597-113">Restar</span><span class="sxs-lookup"><span data-stu-id="80597-113">Subtract</span></span>  
  
- <span data-ttu-id="80597-114">Multiplicar</span><span class="sxs-lookup"><span data-stu-id="80597-114">Multiply</span></span>  
  
- <span data-ttu-id="80597-115">Divide</span><span class="sxs-lookup"><span data-stu-id="80597-115">Divide</span></span>  
  
 <span data-ttu-id="80597-116">Como ambas implementaciones del servicio administran las mismas operaciones y son prácticamente idénticas exceptuando los datos que devuelven, los datos base incluidos en mensajes enviados de las aplicaciones cliente no son lo suficientemente exclusivos como para permitirle determinar cómo enrutar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="80597-116">Because both service implementations handle the same operations, and are essentially identical other than the data that they return, the base data contained in messages sent from client applications is not unique enough to allow you to determine how to route the request.</span></span> <span data-ttu-id="80597-117">Por ejemplo, no se pueden utilizar los filtros de acción porque las acciones predeterminadas para ambos servicios son las mismas.</span><span class="sxs-lookup"><span data-stu-id="80597-117">For example, Action filters cannot be used because the default actions for both services are the same.</span></span>  
  
 <span data-ttu-id="80597-118">Esto se puede resolver de varias maneras: exponiendo un extremo concreto en el enrutador para cada versión del servicio o agregando un elemento de encabezado personalizado al mensaje para indicar la versión del servicio.</span><span class="sxs-lookup"><span data-stu-id="80597-118">This can be resolved in several ways, such as exposing a specific endpoint on the router for each version of the service or adding a custom header element to the message to indicate service version.</span></span>  <span data-ttu-id="80597-119">Cada uno de estos sistemas le permite enrutar los mensajes entrantes de forma única a una versión concreta del servicio. Sin embargo, el empleo de contenidos de mensaje únicos es el método preferido para diferenciar entre las solicitudes de versiones del servicio diferentes.</span><span class="sxs-lookup"><span data-stu-id="80597-119">Each of these approaches allows you to uniquely route incoming messages to a specific version of the service, but utilizing unique message content is the preferred method of differentiating between requests for different service versions.</span></span>  
  
 <span data-ttu-id="80597-120">En este ejemplo, la aplicación cliente agrega el encabezado personalizado 'CalcVer' al mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="80597-120">In this example, the client application adds the ‘CalcVer’ custom header to the request message.</span></span> <span data-ttu-id="80597-121">Este encabezado contendrá un valor que indica la versión del servicio al que se debería enrutar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="80597-121">This header will contain a value that indicates the version of the service that the message should be routed to.</span></span> <span data-ttu-id="80597-122">Un valor de '1' indica que el servicio roundingCalc debe procesar el mensaje, mientras que un valor de '2' indica el servicio de regularCalc.</span><span class="sxs-lookup"><span data-stu-id="80597-122">A value of ‘1’ indicates that the message must be processed by the roundingCalc service, while a value of ‘2’ indicates the regularCalc service.</span></span> <span data-ttu-id="80597-123">Esto permite que la aplicación cliente controle directamente que versión del servicio procesará el mensaje.</span><span class="sxs-lookup"><span data-stu-id="80597-123">This allows the client application to directly control which version of the service will process the message.</span></span>  <span data-ttu-id="80597-124">Como el encabezado personalizado es un valor contenido dentro del mensaje, puede utilizar un punto de conexión para recibir mensajes destinados a ambas versiones del servicio.</span><span class="sxs-lookup"><span data-stu-id="80597-124">Since the custom header is a value contained within the message, you can use one endpoint to receive messages destined for both versions of the service.</span></span> <span data-ttu-id="80597-125">Se puede utilizar el siguiente código en la aplicación cliente para agregar este encabezado personalizado al mensaje:</span><span class="sxs-lookup"><span data-stu-id="80597-125">The following code can be used in the client application to add this custom header to the message:</span></span>  
  
```csharp  
messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", "2"));  
```  
  
### <a name="implement-service-versioning"></a><span data-ttu-id="80597-126">Implementación de versiones del servicio</span><span class="sxs-lookup"><span data-stu-id="80597-126">Implement Service Versioning</span></span>  
  
1. <span data-ttu-id="80597-127">Cree la configuración de servicio de enrutamiento básica especificando el extremo de servicio expuesto por el servicio.</span><span class="sxs-lookup"><span data-stu-id="80597-127">Create the basic Routing Service configuration by specifying the service endpoint exposed by the service.</span></span> <span data-ttu-id="80597-128">En el siguiente ejemplo, se define un punto de conexión de servicio único que se utilizará para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="80597-128">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="80597-129">También se definen los puntos de conexión del cliente que se utilizarán para enviar mensajes a los servicios `roundingCalc` (v1) y `regularCalc` (v2).</span><span class="sxs-lookup"><span data-stu-id="80597-129">It also defines the client endpoints which will be used to send messages to the `roundingCalc` (v1) and the `regularCalc` (v2) services.</span></span>  
  
    ```xml  
    <services>  
        <service behaviorConfiguration="routingConfiguration"  
                 name="System.ServiceModel.Routing.RoutingService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost/routingservice/router" />  
            </baseAddresses>  
          </host>  
          <!--Set up the inbound endpoint for the Routing Service-->  
          <endpoint address="calculator"  
                    binding="wsHttpBinding"  
                    name="routerEndpoint"  
                    contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        </service>  
    </services>  
    <client>  
    <!--set up the destination endpoints-->  
          <endpoint name="regularCalcEndpoint"  
                    address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
  
          <endpoint name="roundingCalcEndpoint"  
                    address="http://localhost:8080/servicemodelsamples/service/"  
                    binding="wsHttpBinding"  
                    contract="*" />  
        </client>  
    ```  
  
2. <span data-ttu-id="80597-130">Defina los filtros usados para enrutar mensajes a los extremos del destino.</span><span class="sxs-lookup"><span data-stu-id="80597-130">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="80597-131">En este ejemplo, el filtro XPath se utiliza para detectar el valor del encabezado personalizado "CalcVer" para determinar a qué versión se debe enrutar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="80597-131">For this example, the XPath filter is used to detect the value of the "CalcVer" custom header to determine which version the message should be routed to.</span></span> <span data-ttu-id="80597-132">Un filtro XPath también se utiliza para detectar mensajes que no contienen el encabezado "CalcVer".</span><span class="sxs-lookup"><span data-stu-id="80597-132">An XPath filter is also used to detect messages that do not contain the "CalcVer" header.</span></span> <span data-ttu-id="80597-133">En el siguiente ejemplo, se definen los filtros necesarios y la tabla de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="80597-133">The following example defines the required filters and namespace table.</span></span>  
  
    ```xml  
    <!-- use the namespace table element to define a prefix for our custom namespace-->  
    <namespaceTable>  
      <add prefix="custom" namespace="http://my.custom.namespace/"/>  
    </namespaceTable>  
    <filters>  
      <!--define the different message filters-->  
      <!--define an xpath message filter to look for the  
          custom header containing a value of 2-->  
      <filter name="XPathFilterRegular" filterType="XPath"  
              filterData="sm:header()/custom:CalcVer = '2'"/>  
      <!--define an xpath message filter to look for the  
          custom header containing a value of 1-->  
      <filter name="XPathFilterRounding" filterType="XPath"  
              filterData="sm:header()/custom:CalcVer = '1'"/>  
       <!--define an xpath message filter to look for  
           messages that do not contain the custom header-->  
       <filter name="XPathFilterNoHeader" filterType="XPath"  
               filterData="count(sm:header()/custom:CalcVer)=0"/>  
    </filters>
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="80597-134">El prefijo de espacio de nombres s12 se define `http://www.w3.org/2003/05/soap-envelope`de forma predeterminada en la tabla de espacio de nombres y representa el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="80597-134">The s12 namespace prefix is defined by default in the namespace table, and represents the namespace `http://www.w3.org/2003/05/soap-envelope`.</span></span>
  
3. <span data-ttu-id="80597-135">Defina la tabla de filtro, que asocia cada filtro a un punto de conexión del cliente.</span><span class="sxs-lookup"><span data-stu-id="80597-135">Define the filter table, which associates each filter with a client endpoint.</span></span> <span data-ttu-id="80597-136">Si el mensaje contiene el encabezado "CalcVer" con un valor de 1, se enviará al servicio regularCalc.</span><span class="sxs-lookup"><span data-stu-id="80597-136">If the message contains the "CalcVer" header with a value of 1, it will be sent to the regularCalc service.</span></span> <span data-ttu-id="80597-137">Si el encabezado contiene un valor de 2, se enviará al servicio de roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="80597-137">If the header contains a value of 2, it will be sent to the roundingCalc service.</span></span> <span data-ttu-id="80597-138">Si no hay ningún encabezado, el mensaje se enrutará a regularCalc.</span><span class="sxs-lookup"><span data-stu-id="80597-138">If no header is present, the message will be routed to the regularCalc.</span></span>  
  
     <span data-ttu-id="80597-139">El procedimiento siguiente define la tabla de filtros y agrega los filtros definidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="80597-139">The following defines the filter table and adds the filters defined earlier.</span></span>  
  
    ```xml  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filters to the message filter table-->  
          <!--look for the custom header = 1, and if we find it,  
              send the message to the rounding calc endpoint-->  
          <add filterName="XPathFilterRounding" endpointName="roundingCalcEndpoint"/>  
          <!--look for the custom header = 2, and if we find it,  
              send the message to the rounding calc endpoint-->  
          <add filterName="XPathFilterRegular" endpointName="regularCalcEndpoint"/>  
          <!--look for the absence of the custom header, and if  
              it is not present, assume the v1 endpoint-->  
          <add filterName="XPathFilterNoHeader" endpointName="roundingCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
4. <span data-ttu-id="80597-140">Para evaluar los mensajes entrantes con respecto a los filtros incluidos en la tabla de filtros, debe asociar esta a los puntos de conexión de servicio mediante el comportamiento de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="80597-140">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="80597-141">En el ejemplo siguiente `filterTable1` se muestra cómo asociarse con los puntos de conexión de servicio:</span><span class="sxs-lookup"><span data-stu-id="80597-141">The following example demonstrates associating `filterTable1` with the service endpoints:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="80597-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80597-142">Example</span></span>  
 <span data-ttu-id="80597-143">A continuación, se muestra una lista completa del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="80597-143">The following is a complete listing of the configuration file.</span></span>  
  
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
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
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
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="roundingCalcEndpoint"  
                address="http://localhost:8080/servicemodelsamples/service/"  
                binding="wsHttpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
      <namespaceTable>  
        <add prefix="custom" namespace="http://my.custom.namespace/"/>  
      </namespaceTable>  
      <filters>  
        <!--define the different message filters-->  
        <!--define an xpath message filter to look for the  
            custom header containing a value of 2-->  
        <filter name="XPathFilterRegular" filterType="XPath"  
                filterData="sm:header()/custom:CalcVer = '2'"/>  
        <!--define an xpath message filter to look for the  
            custom header containing a value of 1-->  
        <filter name="XPathFilterRounding" filterType="XPath"  
                filterData="sm:header()/custom:CalcVer = '1'"/>  
        <!--define an xpath message filter to look for  
            messages that do not contain the custom header-->  
        <filter name="XPathFilterNoHeader" filterType="XPath"  
                filterData="count(sm:header()/custom:CalcVer)=0"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filters to the message filter table-->  
            <!--look for the custom header = 1, and if we find it,  
                send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilterRounding" endpointName="roundingCalcEndpoint"/>  
            <!--look for the custom header = 2, and if we find it,  
                send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilterRegular" endpointName="regularCalcEndpoint"/>  
            <!--look for the absence of the custom header, and if  
                it is not present, assume the v1 endpoint-->  
            <add filterName="XPathFilterNoHeader" endpointName="roundingCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="80597-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="80597-144">Example</span></span>  
 <span data-ttu-id="80597-145">A continuación, se muestra una lista completa de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="80597-145">The following is a complete listing of the client application.</span></span>  
  
```csharp  
using System;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    //The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.  
  
    //Client implementation code.  
    class Client  
    {  
        static void Main()  
        {  
            //Print out the welcome text  
            Console.WriteLine("This sample routes the Calculator Sample through the new WCF RoutingService");  
            Console.WriteLine("Wait for all the services to indicate that they've started, then press");  
            Console.WriteLine("<ENTER> to start the client.");  
  
            while (Console.ReadLine() != "quit")  
            {  
                //Offer the Address configuration for the client  
                Console.WriteLine("");  
                Console.WriteLine("Welcome to the Calculator Client!");  
  
                EndpointAddress epa;  
                //set the default address as the general router endpoint  
                epa = new EndpointAddress("http://localhost/routingservice/router/calculator");  
  
                //set up the CalculatorClient with the EndpointAddress, the WSHttpBinding, and the ICalculator contract  
                //We use the WSHttpBinding so that the outgoing has a message envelope, which we'll manipulate in a minute  
                CalculatorClient client = new CalculatorClient(new WSHttpBinding(), epa);  
                //client.Endpoint.Contract = ContractDescription.GetContract(typeof(ICalculator));  
  
                //Ask the customer if they want to add a custom header to the outgoing message.  
                //The Router will look for this header, and if so ignore the endpoint the message was  
                //received on, and instead direct the message to the RoundingCalcService.  
                Console.WriteLine("");  
                Console.WriteLine("Which calculator service should be used?");  
                Console.WriteLine("Enter 1 for the rounding calculator, 2 for the regular calculator.");  
                Console.WriteLine("[1] or [2]?");  
  
                string header = Console.ReadLine();  
  
                //get the current operationContextScope from the client's inner channel  
                using (OperationContextScope ocs = new OperationContextScope((client.InnerChannel)))  
                {  
                    //get the outgoing message headers element (collection) from the context  
                    MessageHeaders messageHeadersElement = OperationContext.Current.OutgoingMessageHeaders;  
  
                    //if they wanted to create the header, go ahead and add it to the outgoing message  
                    if (header != null && (header=="1" || header=="2"))  
                    {  
                        //create a new header "RoundingCalculator", no specific namespace, and set the value to
                        //the value of header.  
                        //the Routing Service will look for this header in order to determine if the message  
                        //should be routed to the RoundingCalculator  
                        messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", header));  
                    }  
                    else //incorrect choice, no header added  
                    {  
                        Console.WriteLine("Incorrect value entered, not adding a header");  
                    }  
  
                        //call the client operations  
                        CallClient(client);  
                }  
  
                //close the client to clean it up  
                client.Close();  
                Console.WriteLine();  
                Console.WriteLine("Press <ENTER> to run the client again or type 'quit' to quit.");  
            }  
        }  
  
        private static void CallClient(CalculatorClient client)  
        {  
            Console.WriteLine("");  
            Console.WriteLine("Sending!");  
            // Call the Add service operation.  
            double value1 = 100.00D;  
            double value2 = 15.99D;  
            double result = client.Add(value1, value2);  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Subtract service operation.  
            value1 = 145.00D;  
            value2 = 76.54D;  
            result = client.Subtract(value1, value2);  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Multiply service operation.  
            value1 = 9.00D;  
            value2 = 81.25D;  
            result = client.Multiply(value1, value2);  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Divide service operation.  
            value1 = 22.00D;  
            value2 = 7.00D;  
            result = client.Divide(value1, value2);  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="80597-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80597-146">See also</span></span>

- [<span data-ttu-id="80597-147">Servicios de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="80597-147">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)
