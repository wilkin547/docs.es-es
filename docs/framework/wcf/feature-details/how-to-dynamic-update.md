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
# <a name="how-to-dynamic-update"></a>Cómo actualización dinámica

Este tema describe los pasos básicos necesarios para crear y actualizar dinámicamente la configuración de enrutamiento. En este ejemplo, la configuración de enrutamiento inicial se obtiene del archivo de configuración y enruta todos los mensajes al servicio de calculadora de regularCalc; sin embargo, se actualiza posteriormente mediante programación para cambiar el punto de conexión de destino del servicio de roundingCalc.  
  
> [!NOTE]
> En muchas implementaciones, la configuración será totalmente dinámica y no se basará en una configuración predeterminada; sin embargo, hay algunos casos, como el de este tema, en los que es deseable tener un estado de configuración predeterminada al iniciar el servicio.  
  
> [!NOTE]
> Las actualizaciones dinámicas solo se llevan a cabo en la memoria y no ocasionan la modificación de los archivos de configuración.  
  
 regularCalc y roundingCalc admiten las mismas operaciones de suma, resta, multiplicación y división; sin embargo, roundingCalc redondea todos los cálculos al valor entero más cercano antes de realizar la devolución. Se usa un archivo de configuración para configurar el servicio para enrutar todos los mensajes al servicio de regularCalc. Una vez iniciado el servicio de enrutamiento, <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> se utiliza para reconfigurar el servicio para enrutar los mensajes al servicio de roundingCalc.  
  
### <a name="implement-initial-configuration"></a>Implementación de la configuración inicial  
  
1. Cree la configuración de servicio de enrutamiento básica especificando los extremos de servicio expuestos por el servicio. En el siguiente ejemplo, se define un punto de conexión de servicio único que se utilizará para recibir mensajes. También se define un extremo de cliente que se usará para enviar mensajes a regularCalc.  
  
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
  
2. Defina el filtro usado para enrutar mensajes a los puntos de conexión del destino. En este ejemplo, se usa el filtro de MatchAll para enrutar todos los mensajes a regularCalcEndpoint definido previamente. En el siguiente ejemplo, se define el filtro y la tabla de filtros.  
  
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
  
3. Para evaluar los mensajes entrantes con respecto a los filtros incluidos en la tabla de filtros, debe asociar esta a los puntos de conexión de servicio mediante el comportamiento de enrutamiento. En el ejemplo siguiente se muestra cómo asociar "filterTable1" al punto de conexión de servicio.  
  
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
  
## <a name="implement-dynamic-configuration"></a>Implementación de la configuración dinámica  

 La configuración dinámica del servicio de enrutamiento solo se puede realizar en código creando un nuevo <xref:System.ServiceModel.Routing.RoutingConfiguration> y usando <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> para reemplazar la configuración actual.  En este ejemplo, el servicio de enrutamiento se auto-hospeda dentro de una aplicación de consola. Después de que la aplicación se haya iniciado, puede modificar la configuración de enrutamiento escribiendo 'regular' (normal) o 'rounding' (redondeo) en la ventana de la consola para configurar el extremo de destino al que se enrutan los mensajes: regularCalc al escribir 'regular'; de lo contrario, roundingCalc al introducir 'rounding'.  
  
1. Deben agregarse las siguientes instrucciones de uso para admitir el servicio de enrutamiento.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using System.ServiceModel.Description;  
    using System.ServiceModel.Dispatcher;  
    using System.ServiceModel.Routing;  
    ```  
  
2. El siguiente código se usa para probar internamente el servicio de enrutamiento como una aplicación de consola. Esto inicializa el servicio de enrutamiento mediante la configuración descrita en el paso anterior, que se incluye en el archivo de configuración de la aplicación. El bucle while contiene el código usado para cambiar la configuración de enrutamiento.  
  
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
  
3. Para actualizar la configuración de enrutamiento dinámicamente, debe crearse una nueva configuración de enrutamiento. Esto debe contener todos los puntos de conexión, filtros y tablas de filtros necesarios para la nueva configuración de enrutamiento, ya que reemplazará por completo la configuración de enrutamiento existente. Para usar la nueva configuración de enrutamiento, debe invocar <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> y pasar la nueva configuración.  
  
     Agregue el siguiente código al bucle while definido previamente para permitir que el servicio se reconfigure en función de los datos proporcionados por el usuario.  
  
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
    > Como el método para proporcionar un nuevo RoutingConfiguration se incluye en la extensión de servicio RoutingExtension, pueden proporcionarse nuevos objetos RoutingConfiguration en cualquier parte del modelo de extensibilidad de WCF que tiene o puede obtener una referencia a ServiceHost o ServiceExtensions (como en otros ServiceExtension).
  
## <a name="example"></a>Ejemplo  

A continuación se muestra una lista completa de la aplicación de consola usada en este ejemplo:
  
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
  
## <a name="example"></a>Ejemplo  

A continuación se muestra una lista completa del archivo de configuración que se usa en este ejemplo:
  
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
  
## <a name="see-also"></a>Vea también

- [Servicios de enrutamiento](../samples/routing-services.md)
