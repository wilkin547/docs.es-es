---
description: 'Más información acerca de cómo: controlar errores'
title: Cómo Control de errores
ms.date: 03/30/2017
ms.assetid: de566e39-9358-44ff-8244-780f6b799966
ms.openlocfilehash: 1d385070e4cc0d55bc3327114baf4e4ff543171f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704659"
---
# <a name="how-to-error-handling"></a>Cómo Control de errores

Este tema describe los pasos básicos necesarios para crear una configuración de enrutamiento que utiliza el control de errores. En este ejemplo, los mensajes se enrutan a un punto de conexión de destino. Si un mensaje no se puede entregar debido a un error de la red o relacionado con las comunicaciones (<xref:System.ServiceModel.CommunicationException>), el mensaje se reenvía a un punto de conexión alternativo.

> [!NOTE]
> Para simular un error de la red, el punto de conexión de destino utilizado en este ejemplo contiene una dirección incorrecta. Se produce un error en los mensajes enrutados a este extremo, ya que ningún servicio está realizando escuchas en la dirección especificada.

> [!NOTE]
> Aunque el ejemplo incluido en este tema no describe la configuración de tiempo de espera explícitamente, debe tenerla en cuenta al utilizar el control de errores. Cuando se detectan errores, se detectará un retraso adicional antes de que el cliente reciba una respuesta. Esto se debe a que el error se recibe en el servicio de enrutamiento, que, a continuación, intenta enviar el mensaje a un punto de conexión de reserva. Si los valores de tiempo de espera asociados a los puntos de conexión de destino de reserva y primarios son grandes, el cliente podría experimentar un retraso largo mientras el mensaje conmuta por error en varios puntos de conexión de la lista de reserva antes de enviarse correctamente.
>
> Como el servicio de enrutamiento podría encontrarse con un retraso máximo igual a la suma del valor de tiempo de espera de todos los extremos asociados a un filtro, recomendamos aumentar el tiempo de espera esperado en el cliente de forma correspondiente.

### <a name="implement-error-handling"></a>Implementación del control de errores

1. Cree la configuración de servicio de enrutamiento básica especificando el extremo de servicio expuesto por el servicio. En el siguiente ejemplo, se define un punto de conexión de servicio único que se utilizará para recibir mensajes. También se definen los extremos de cliente que se utilizan para enviar mensajes; deadDestination y realDestination. El punto de conexión deadDestination contiene una dirección que no hace referencia a un servicio en ejecución y que se utiliza para simular un error de la red al enviar mensajes a este punto de conexión.

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

2. Defina los filtros usados para enrutar mensajes a los extremos del destino.  Para este ejemplo, se emplea un filtro MatchAll para coincidir con todos los mensajes recibidos por el servicio de enrutamiento.

    ```xml
    <filters>
      <!-- Create a MatchAll filter which will catch all messages -->
      <filter name="MatchAllFilter1" filterType="MatchAll" />
    </filters>
    ```

3. Defina la lista de puntos de conexión de reserva, que contiene los puntos de conexión a los que se envía un mensaje en caso de que se produzca un error de la red o de comunicaciones durante un envío al punto de conexión de destino primario. En el siguiente ejemplo, se define una lista de reserva que contiene un extremo; sin embargo, se pueden especificar varios extremos en una lista de reserva.

     Si la lista de reserva contiene varios puntos de conexión, cuando se produce un error de la red o de comunicaciones, el servicio de enrutamiento intenta enviar el mensaje al primer punto de conexión de la lista. Si se produce un error de la red o de comunicaciones al realizar el envío a este extremo, el servicio de enrutamiento intenta enviar el mensaje al extremo siguiente incluido en la lista. El servicio sigue enviando el mensaje a cada punto de conexión de la lista de puntos de conexión de reserva hasta que el mensaje se envía correctamente, todos los puntos de conexión de reserva devuelven un error de la red o de comunicaciones, o se envía el mensaje y el punto de conexión devuelve un error de ausencia de red no relacionado con las comunicaciones.

    ```xml
    <backupLists>
      <backupList name="backupEndpointList">
          <add endpointName="realDestination" />
      </backupList>
    </backupLists>
    ```

4. Defina la tabla de filtros, que asocia el filtro al punto de conexión deadDestination y a la lista de puntos de conexión de reserva.  El servicio de enrutamiento intenta enviar primero el mensaje al punto de conexión de destino asociado al filtro. Como deadDestination contiene una dirección que no hace referencia a un servicio en ejecución, esto produce un error de la red. A continuación, el servicio de enrutamiento intenta enviar el mensaje al punto de conexión especificado en backupEndpointList.

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

5. Para evaluar los mensajes entrantes con respecto al filtro incluido en la tabla de filtros, debe asociar la tabla de filtros a los puntos de conexión de servicio mediante el comportamiento de enrutamiento.  En el ejemplo siguiente se muestra cómo asociar "filterTable1" a los puntos de conexión de servicio.

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

## <a name="example"></a>Ejemplo

A continuación se muestra una lista completa del archivo de configuración:

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
            <!-- Add an entry that maps the MatchAllMessageFilter to the dead destination -->
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
