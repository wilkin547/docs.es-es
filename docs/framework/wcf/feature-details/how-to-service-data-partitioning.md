---
title: Cómo Particionar datos de servicio
ms.date: 03/30/2017
ms.assetid: 1ccff72e-d76b-4e36-93a2-e51f7b32dc83
ms.openlocfilehash: 7bb5eb6bda8bb2be3dfaaa88eb4b5ad787f47aa7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268929"
---
# <a name="how-to-service-data-partitioning"></a>Cómo Particionar datos de servicio

Este tema describe los pasos básicos necesarios para realizar particiones de los mensajes en múltiples instancias de un mismo servicio de destino. La partición de datos de servicio se suele utilizar cuando hay que ajustar un servicio para proporcionar una mayor calidad del servicio, o cuando hay que administrar solicitudes de diversos clientes de una manera determinada. Por ejemplo, es posible que los mensajes de clientes de gran valor o "oro" deban procesarse con una prioridad más alta que los mensajes de un cliente estándar.  
  
 En este ejemplo, los mensajes se enrutan a una de las dos instancias del servicio de regularCalc. Ambas instancias del servicio son idénticas; sin embargo, el servicio representado por el extremo de calculator1 procesa mensajes recibidos de los clientes importantes, y el extremo de calculator2 procesa los mensajes de otros clientes.  
  
 El mensaje enviado del cliente no tiene ningún dato único que se pueda usar para identificar a qué instancia de servicio debería enrutarse el mensaje. Para permitir que cada cliente enrute datos a un destino concreto, implementaremos dos puntos de conexión de servicio que se usarán para recibir mensajes.  
  
> [!NOTE]
> Aunque este ejemplo utiliza puntos de conexión concretos para crear una partición de los datos, esto también se puede lograr mediante la información incluida en el propio mensaje, como el encabezado o la información del cuerpo del mensaje.  
  
### <a name="implement-service-data-partitioning"></a>Implementación de partición de datos de servicio  
  
1. Cree la configuración de servicio de enrutamiento básica especificando los extremos de servicio expuestos por el servicio. En el siguiente ejemplo, se definen dos puntos de conexión que se utilizarán para recibir mensajes. También se definen los puntos de conexión del cliente, que se utilizan para enviar mensajes a las instancias de servicio de regularCalc.  
  
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
  
2. Defina los filtros usados para enrutar mensajes a los extremos del destino.  En este ejemplo, se usa el filtro EndpointName para determinar qué punto de conexión de servicio recibe el mensaje. En el siguiente ejemplo, se definen los filtros y la sección de enrutamiento necesarios.  
  
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
  
3. Defina la tabla de filtro, que asocia cada filtro a un punto de conexión del cliente. En este ejemplo, el mensaje se enrutará según el punto de conexión concreto en el que se recibió. Como el mensaje solo puede coincidir con uno de los dos posibles filtros, no hay necesidad de utilizar la prioridad del filtro para controlar el orden en el que se evalúan los filtros.  
  
     El procedimiento siguiente define la tabla de filtros y agrega los filtros definidos anteriormente.  
  
    ```xml  
    <filterTables>  
       <filterTable name="filterTable1">  
         <!--add the filters to the message filter table-->  
         <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
         <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
       </filterTable>  
    </filterTables>  
    ```  
  
4. Para evaluar los mensajes entrantes con respecto a los filtros incluidos en la tabla, debe asociar la tabla de filtros a los puntos de conexión de servicio mediante el comportamiento de enrutamiento. En el ejemplo siguiente se muestra cómo asociar "filterTable1" a los puntos de conexión de servicio:  
  
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
  
## <a name="example"></a>Ejemplo  

 A continuación, se muestra una lista completa del archivo de configuración.  
  
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
  
## <a name="see-also"></a>Vea también

- [Servicios de enrutamiento](../samples/routing-services.md)
