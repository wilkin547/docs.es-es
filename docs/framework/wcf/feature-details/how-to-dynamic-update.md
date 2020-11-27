---
title: Cómo actualización dinámica
ms.date: 03/30/2017
ms.assetid: 9b8f6e0d-edab-4a7e-86e3-8c66bebc64bb
ms.openlocfilehash: a12d480163bb579f34d006ae1837ed4392bf47ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265549"
---
# <a name="how-to-dynamic-update"></a><span data-ttu-id="490e2-102">Cómo actualización dinámica</span><span class="sxs-lookup"><span data-stu-id="490e2-102">How To: Dynamic Update</span></span>

<span data-ttu-id="490e2-103">Este tema describe los pasos básicos necesarios para crear y actualizar dinámicamente la configuración de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="490e2-103">This topic outlines the basic steps required to create and dynamically update the routing configuration.</span></span> <span data-ttu-id="490e2-104">En este ejemplo, la configuración de enrutamiento inicial se obtiene del archivo de configuración y enruta todos los mensajes al servicio de calculadora de regularCalc; sin embargo, se actualiza posteriormente mediante programación para cambiar el punto de conexión de destino del servicio de roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="490e2-104">In this example, the initial routing configuration is obtained from the configuration file and routes all messages to the regularCalc calculator service; however, it is subsequently updated programmatically in order to change the destination endpoint the roundingCalc service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="490e2-105">En muchas implementaciones, la configuración será totalmente dinámica y no se basará en una configuración predeterminada; sin embargo, hay algunos casos, como el de este tema, en los que es deseable tener un estado de configuración predeterminada al iniciar el servicio.</span><span class="sxs-lookup"><span data-stu-id="490e2-105">In many implementations, configuration will be fully dynamic and will not rely on a default configuration; however, there are some scenarios, such as the one in this topic, where it is desirable to have a default configuration state when the service starts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="490e2-106">Las actualizaciones dinámicas solo se llevan a cabo en la memoria y no ocasionan la modificación de los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="490e2-106">Dynamic updates occur only in memory, and do not result in the modification of configuration files.</span></span>  
  
 <span data-ttu-id="490e2-107">regularCalc y roundingCalc admiten las mismas operaciones de suma, resta, multiplicación y división; sin embargo, roundingCalc redondea todos los cálculos al valor entero más cercano antes de realizar la devolución.</span><span class="sxs-lookup"><span data-stu-id="490e2-107">Both regularCalc and roundingCalc support the same operations of add, subtract, multiply and divide; however, roundingCalc rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="490e2-108">Se usa un archivo de configuración para configurar el servicio para enrutar todos los mensajes al servicio de regularCalc.</span><span class="sxs-lookup"><span data-stu-id="490e2-108">A configuration file is used to configure the service to route all messages to the regularCalc service.</span></span> <span data-ttu-id="490e2-109">Una vez iniciado el servicio de enrutamiento, <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> se utiliza para reconfigurar el servicio para enrutar los mensajes al servicio de roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="490e2-109">After the Routing Service has been started, <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> is used to reconfigure the service to route messages to the roundingCalc service.</span></span>  
  
### <a name="implement-initial-configuration"></a><span data-ttu-id="490e2-110">Implementación de la configuración inicial</span><span class="sxs-lookup"><span data-stu-id="490e2-110">Implement Initial Configuration</span></span>  
  
1. <span data-ttu-id="490e2-111">Cree la configuración de servicio de enrutamiento básica especificando los extremos de servicio expuestos por el servicio.</span><span class="sxs-lookup"><span data-stu-id="490e2-111">Create the basic Routing Service Configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="490e2-112">En el siguiente ejemplo, se define un punto de conexión de servicio único que se utilizará para recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="490e2-112">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="490e2-113">También se define un extremo de cliente que se usará para enviar mensajes a regularCalc.</span><span class="sxs-lookup"><span data-stu-id="490e2-113">It also defines a client endpoint that will be used to send messages to the regularCalc.</span></span>  
  
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
    <!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    ```  
  
2. <span data-ttu-id="490e2-114">Defina el filtro usado para enrutar mensajes a los puntos de conexión del destino.</span><span class="sxs-lookup"><span data-stu-id="490e2-114">Define the filter used to route messages to the destination endpoints.</span></span> <span data-ttu-id="490e2-115">En este ejemplo, se usa el filtro de MatchAll para enrutar todos los mensajes a regularCalcEndpoint definido previamente.</span><span class="sxs-lookup"><span data-stu-id="490e2-115">For this example, the MatchAll filter is used to route all messages to the regularCalcEndpoint defined previously.</span></span> <span data-ttu-id="490e2-116">En el siguiente ejemplo, se define el filtro y la tabla de filtros.</span><span class="sxs-lookup"><span data-stu-id="490e2-116">The following example defines the filter and filter table.</span></span>  
  
    ```xml  
    <filters>  
      <!--define the message filter-->  
      <filter name="MatchAllFilter" filterType="MatchAll"/>  
    </filters>  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filter to the message filter table-->  
          <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
3. <span data-ttu-id="490e2-117">Para evaluar los mensajes entrantes con respecto a los filtros incluidos en la tabla de filtros, debe asociar esta a los puntos de conexión de servicio mediante el comportamiento de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="490e2-117">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="490e2-118">En el ejemplo siguiente se muestra cómo asociar "filterTable1" al punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="490e2-118">The following example demonstrates associating "filterTable1" with the service endpoint.</span></span>  
  
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
  
## <a name="implement-dynamic-configuration"></a><span data-ttu-id="490e2-119">Implementación de la configuración dinámica</span><span class="sxs-lookup"><span data-stu-id="490e2-119">Implement Dynamic Configuration</span></span>  

 <span data-ttu-id="490e2-120">La configuración dinámica del servicio de enrutamiento solo se puede realizar en código creando un nuevo <xref:System.ServiceModel.Routing.RoutingConfiguration> y usando <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> para reemplazar la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="490e2-120">Dynamic configuration of the Routing Service can only be performed in code by creating a new <xref:System.ServiceModel.Routing.RoutingConfiguration> and using <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> to replace the current configuration.</span></span>  <span data-ttu-id="490e2-121">En este ejemplo, el servicio de enrutamiento se auto-hospeda dentro de una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="490e2-121">For this example, the Routing Service is self-hosted within a console application.</span></span> <span data-ttu-id="490e2-122">Después de que la aplicación se haya iniciado, puede modificar la configuración de enrutamiento escribiendo 'regular' (normal) o 'rounding' (redondeo) en la ventana de la consola para configurar el extremo de destino al que se enrutan los mensajes: regularCalc al escribir 'regular'; de lo contrario, roundingCalc al introducir 'rounding'.</span><span class="sxs-lookup"><span data-stu-id="490e2-122">After the application has started, you can modify the routing configuration by entering ‘regular’ or ‘rounding’ at the console window to configure the destination endpoint that messages are routed to; regularCalc when ‘regular’ is entered, otherwise roundingCalc when ‘rounding’ is entered.</span></span>  
  
1. <span data-ttu-id="490e2-123">Deben agregarse las siguientes instrucciones de uso para admitir el servicio de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="490e2-123">The following using statements must be added in order to support the Routing Service.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using System.ServiceModel.Description;  
    using System.ServiceModel.Dispatcher;  
    using System.ServiceModel.Routing;  
    ```  
  
2. <span data-ttu-id="490e2-124">El siguiente código se usa para probar internamente el servicio de enrutamiento como una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="490e2-124">The following code is used to self-host the Routing Service as a console application.</span></span> <span data-ttu-id="490e2-125">Esto inicializa el servicio de enrutamiento mediante la configuración descrita en el paso anterior, que se incluye en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="490e2-125">This initializes the Routing Service using the configuration described in the previous step, which is contained within the application configuration file.</span></span> <span data-ttu-id="490e2-126">El bucle while contiene el código usado para cambiar la configuración de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="490e2-126">The while loop contains the code used to change the routing configuration.</span></span>  
  
    ```csharp  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost =  
            new ServiceHost(typeof(RoutingService)))  
        {  
            // Open the ServiceHost to create listeners
            // and start listening for messages.  
            Console.WriteLine("The Routing Service configured, opening....");  
            serviceHost.Open();  
            Console.WriteLine("The Routing Service is now running.");  
             Console.WriteLine("Type 'quit' to terminate router.");  
             Console.WriteLine("<ENTER> to change routing configuration.");  
             while (Console.ReadLine() != "quit")  
             {  
            ....  
            }  
        }  
    }  
    ```  
  
3. <span data-ttu-id="490e2-127">Para actualizar la configuración de enrutamiento dinámicamente, debe crearse una nueva configuración de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="490e2-127">To dynamically update the routing configuration, a new routing configuration must be created.</span></span> <span data-ttu-id="490e2-128">Esto debe contener todos los puntos de conexión, filtros y tablas de filtros necesarios para la nueva configuración de enrutamiento, ya que reemplazará por completo la configuración de enrutamiento existente.</span><span class="sxs-lookup"><span data-stu-id="490e2-128">This must contain all endpoints, filters and filter tables that are required for the new routing configuration, as it will completely replace the existing routing configuration.</span></span> <span data-ttu-id="490e2-129">Para usar la nueva configuración de enrutamiento, debe invocar <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> y pasar la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="490e2-129">In order to use the new routing configuration, you must invoke <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> and pass the new configuration.</span></span>  
  
     <span data-ttu-id="490e2-130">Agregue el siguiente código al bucle while definido previamente para permitir que el servicio se reconfigure en función de los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="490e2-130">Add the following code to the while loop defined previously to allow the service to be reconfigured based on user input.</span></span>  
  
    ```csharp  
    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
    string destEndpoint = Console.ReadLine();  
    // Create a new RoutingConfiguration  
    RoutingConfiguration rc = new RoutingConfiguration();  
    // Determine the endpoint to configure for  
    switch (destEndpoint)  
    {  
        case "regular":  
            // Define the destination endpoint  
            ServiceEndpoint regularCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        case "rounding":  
            // Define the destination endpoint  
            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        default:  
            Console.WriteLine("Incorrect value entered, no change.");  
            break;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="490e2-131">Como el método para proporcionar un nuevo RoutingConfiguration se incluye en la extensión de servicio RoutingExtension, pueden proporcionarse nuevos objetos RoutingConfiguration en cualquier parte del modelo de extensibilidad de WCF que tiene o puede obtener una referencia a ServiceHost o ServiceExtensions (como en otros ServiceExtension).</span><span class="sxs-lookup"><span data-stu-id="490e2-131">Since the method for providing a new RoutingConfiguration is contained in the RoutingExtension service extension, new RoutingConfiguration objects can be provided anywhere in the WCF extensibility model that has or can obtain a reference to the ServiceHost or ServiceExtensions (such as in another ServiceExtension).</span></span>
  
## <a name="example"></a><span data-ttu-id="490e2-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="490e2-132">Example</span></span>  

<span data-ttu-id="490e2-133">A continuación se muestra una lista completa de la aplicación de consola usada en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="490e2-133">The following is a complete listing of the console application used in this example:</span></span>
  
```csharp
//-----------------------------------------------------------------  
//  Copyright (c) Microsoft Corporation.  All Rights Reserved.  
//-----------------------------------------------------------------  
  
using System;  
using System.Collections.Generic;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.ServiceModel.Description;  
using System.ServiceModel.Dispatcher;  
using System.ServiceModel.Routing;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    public class Router  
    {  
        // Host the service within this EXE console application.  
        public static void Main()  
        {
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost =  
                new ServiceHost(typeof(RoutingService)))  
            {  
                // Open the ServiceHost to create listeners
                // and start listening for messages.  
                Console.WriteLine("The Routing Service configured, opening....");  
                serviceHost.Open();  
                Console.WriteLine("The Routing Service is now running.");  
                Console.WriteLine("Type 'quit' to terminate router.");  
                Console.WriteLine("<ENTER> to change routing configuration.");  
                while (Console.ReadLine() != "quit")  
                {  
                    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
                    string destEndpoint = Console.ReadLine();  
                    // Create a new RoutingConfiguration  
                    RoutingConfiguration rc = new RoutingConfiguration();  
                    // Determine the endpoint to configure for  
                    switch (destEndpoint)  
                    {  
                        case "regular":  
                            // Define the destination endpoint  
                            ServiceEndpoint regularCalc = new ServiceEndpoint(  
                            ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                            new NetTcpBinding(),  
                            new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        case "rounding":  
                            // Define the destination endpoint  
                            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
                                ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                                new NetTcpBinding(),  
                                new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        default:  
                            Console.WriteLine("Incorrect value entered, no change.");  
                            break;  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="490e2-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="490e2-134">Example</span></span>  

<span data-ttu-id="490e2-135">A continuación se muestra una lista completa del archivo de configuración que se usa en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="490e2-135">The following is a complete listing of the configuration file used in this example:</span></span>
  
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
<!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
  
      <filters>  
        <!--define the message filter-->  
        <filter name="MatchAllFilter" filterType="MatchAll"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filter to the message filter table-->  
            <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="490e2-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="490e2-136">See also</span></span>

- [<span data-ttu-id="490e2-137">Servicios de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="490e2-137">Routing Services</span></span>](../samples/routing-services.md)
