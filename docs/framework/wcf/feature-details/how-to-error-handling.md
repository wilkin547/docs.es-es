---
title: "C&#243;mo: Control de errores | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: de566e39-9358-44ff-8244-780f6b799966
caps.latest.revision: 5
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Control de errores
Este tema describe los pasos básicos necesarios para crear una configuración de enrutamiento que utiliza el control de errores.  En este ejemplo, los mensajes se enrutan a un extremo de destino.  Si un mensaje no se puede entregar debido a un error de la red o relacionado con las comunicaciones \(<xref:System.ServiceModel.CommunicationException>\), el mensaje se reenvía a un extremo alternativo.  
  
> [!NOTE]
>  Para simular un error de la red, el extremo de destino utilizado en este ejemplo contiene una dirección incorrecta.  Se produce un error en los mensajes enrutados a este extremo, ya que ningún servicio está realizando escuchas en la dirección especificada.  
  
> [!NOTE]
>  Aunque el ejemplo incluido en este tema no describe la configuración de tiempo de espera explícitamente, debe tenerla en cuenta al utilizar el control de errores.  Cuando se detectan errores, se detectará un retraso adicional antes de que el cliente reciba una respuesta.  Esto se debe a que el error se recibe en el servicio de enrutamiento, que, a continuación, intenta enviar el mensaje a un extremo de reserva.  Si los valores de tiempo de espera asociados a los extremos de destino de reserva y primarios son grandes, el cliente podría experimentar un retraso largo mientras el mensaje conmuta por error en varios extremos de la lista de reserva antes de enviarse correctamente.  
>   
>  Como el servicio de enrutamiento podría encontrarse con un retraso máximo igual a la suma del valor de tiempo de espera de todos los extremos asociados a un filtro, recomendamos aumentar el tiempo de espera esperado en el cliente de forma correspondiente.  
  
### Implementación del control de errores  
  
1.  Cree la configuración de servicio de enrutamiento básica especificando el extremo de servicio expuesto por el servicio.  En el siguiente ejemplo, se define un extremo de servicio único que se utilizará para recibir mensajes.  También se definen los extremos de cliente que se utilizan para enviar mensajes; deadDestination y realDestination.  El extremo deadDestination contiene una dirección que no hace referencia a un servicio en ejecución y que se utiliza para simular un error de la red al enviar mensajes a este extremo.  
  
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
  
2.  Defina los filtros usados para enrutar mensajes a los extremos del destino.  Para este ejemplo, se emplea un filtro MatchAll para coincidir con todos los mensajes recibidos por el servicio de enrutamiento.  
  
    ```xml  
    <filters>  
      <!-- Create a MatchAll filter which will catch all messages -->  
      <filter name="MatchAllFilter1" filterType="MatchAll" />  
    </filters>  
  
    ```  
  
3.  Defina la lista de extremos de reserva, que contiene los extremos a los que se envía un mensaje en caso de que se produzca un error de la red o de comunicaciones durante un envío al extremo de destino primario.  En el siguiente ejemplo, se define una lista de reserva que contiene un extremo; sin embargo, se pueden especificar varios extremos en una lista de reserva.  
  
     Si la lista de reserva contiene varios extremos, cuando se produce un error de la red o de comunicaciones, el servicio de enrutamiento intenta enviar el mensaje al primer extremo de la lista.  Si se produce un error de la red o de comunicaciones al realizar el envío a este extremo, el servicio de enrutamiento intenta enviar el mensaje al extremo siguiente incluido en la lista.  El servicio sigue enviando el mensaje a cada extremo de la lista de extremos de reserva hasta que el mensaje se envía correctamente, todos los extremos de reserva devuelven un error de la red o de comunicaciones, o se envía el mensaje y el extremo devuelve un error de ausencia de red no relacionado con las comunicaciones.  
  
    ```  
    <backupLists>          
      <backupList name="backupEndpointList">  
          <add endpointName="realDestination" />  
      </backupList>  
    </backupLists>  
    ```  
  
4.  Defina la tabla de filtros, que asocia el filtro al extremo deadDestination y a la lista de extremos de reserva.  El servicio de enrutamiento intenta enviar primero el mensaje al extremo de destino asociado al filtro.  Como deadDestination contiene una dirección que no hace referencia a un servicio en ejecución, esto produce un error de la red.  A continuación, el servicio de enrutamiento intenta enviar el mensaje al extremo especificado en backupEndpointlist.  
  
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
  
5.  Para evaluar los mensajes entrantes con respecto al filtro incluido en la tabla de filtros, debe asociar la tabla de filtros a los extremos de servicio mediante el comportamiento de enrutamiento.  En el siguiente ejemplo, se muestra cómo asociar "filterTable1" a los extremos de servicio.  
  
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
  
## Ejemplo  
 A continuación, se muestra una lista completa del archivo de configuración.  
  
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