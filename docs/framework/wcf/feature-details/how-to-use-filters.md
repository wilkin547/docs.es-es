---
title: Cómo usar los filtros
ms.date: 03/30/2017
ms.assetid: f2c7255f-c376-460e-aa20-14071f1666e5
ms.openlocfilehash: 34ea961b0ef5db51efcae0b86f2c06171d6d756c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464104"
---
# <a name="how-to-use-filters"></a>Cómo usar los filtros
Este tema describe los pasos básicos necesarios para crear una configuración de enrutamiento que utiliza múltiples filtros. En este ejemplo, los mensajes se enrutan a dos implementaciones de un servicio de la calculadora, regularCalc y roundingCalc. Ambas implementaciones admiten las mismas operaciones; sin embargo, un servicio redondea todos los cálculos al valor entero más cercano antes de devolverlos. Una aplicación cliente debe poder indicar si se debe utilizar la versión del redondeo del servicio; si no se especifica ninguna preferencia de servicio, la carga del mensaje se equilibra entre los dos servicios. Las operaciones expuestas por ambos servicios son:  
  
- Sumar  
  
- Restar  
  
- Multiplicar  
  
- Divide  
  
 Dado que ambos servicios implementan las mismas operaciones, no puede utilizar el filtro Action porque la acción especificada en el mensaje no será única. En su lugar, debe realizar un trabajo adicional para asegurarse de que los mensajes se enrutan a los puntos de conexión adecuados.  
  
### <a name="determine-unique-data"></a>Determinación de datos únicos  
  
1. Como ambas implementaciones del servicio administran las mismas operaciones y son prácticamente idénticas exceptuando los datos que devuelven, los datos base incluidos en mensajes enviados de las aplicaciones cliente no son lo suficientemente exclusivos como para permitirle determinar cómo enrutar la solicitud. Sin embargo, si la aplicación cliente agrega un valor de encabezado único al mensaje, puede utilizar este valor para determinar cómo se debería enrutar el mensaje.  
  
     En este ejemplo, si la aplicación cliente necesita procesar el mensaje mediante la calculadora de redondeo, agrega un encabezado personalizado mediante el siguiente código:  
  
    ```csharp  
    messageHeadersElement.Add(MessageHeader.CreateHeader("RoundingCalculator",
                                   "http://my.custom.namespace/", "rounding"));  
    ```  
  
     Ahora, puede utilizar el filtro XPath para inspeccionar los mensajes de este encabezado y enrutar mensajes que contengan el encabezado al servicio roundCalc.  
  
2. Además el servicio de enrutamiento expone dos extremos de servicio virtuales que se pueden utilizar con los filtros EndpointName, EndpointAddress o PrefixEndpointAddress para enrutar de forma exclusiva los mensajes entrantes a una implementación de la calculadora concreta en función del extremo al que la aplicación cliente envía la solicitud.  
  
### <a name="define-endpoints"></a>Definición de los puntos de conexión  
  
1. Al definir los extremos utilizados por el servicio de enrutamiento, debería determinar primero la forma del canal empleado por sus clientes y servicios. En este escenario, ambos servicios de destino utilizan un patrón de solicitud-respuesta, de modo que se utiliza <xref:System.ServiceModel.Routing.IRequestReplyRouter>. En el siguiente ejemplo, se definen los puntos de conexión de servicio expuestos por el servicio de enrutamiento.  
  
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
            <!--first create the general router endpoint-->  
            <endpoint address="general"  
                      binding="wsHttpBinding"  
                      name="routerEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
            <!--create a virtual endpoint for the regular calculator service-->  
            <endpoint address="regular/calculator"  
                      binding="wsHttpBinding"  
                      name="calculatorEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
            <!--now create a virtual endpoint for the rounding calculator-->  
            <endpoint address="rounding/calculator"  
                      binding="wsHttpBinding"  
                      name="roundingEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
  
          </service>  
    </services>  
    ```  
  
     Con esta configuración, el servicio de enrutamiento expone tres puntos de conexión independientes. Según las opciones de tiempo de ejecución, la aplicación cliente envía mensajes a una de estas direcciones. Los mensajes que llegan a uno de los puntos de conexión de servicio "virtuales" ("redondeo/calculador" o "regular/calculador") se reenvían a la implementación de calculadora correspondiente. Si la aplicación cliente no envía la solicitud a un punto de conexión determinado, el mensaje se dirige al punto de conexión general. Independientemente del extremo elegido, la aplicación cliente también puede decidir incluir el encabezado personalizado para indicar que el mensaje se debería reenviar a la implementación de calculadora de redondeo.  
  
2. El siguiente ejemplo define los extremos del cliente (destino) a los que el servicio de enrutamiento enruta los mensajes.  
  
    ```xml  
    <client>  
          <endpoint name="regularCalcEndpoint"  
                    address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
  
          <endpoint name="roundingCalcEndpoint"  
                    address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
    </client>  
    ```  
  
     Estos puntos de conexión se utilizan en la tabla de filtros para indicar el punto de conexión de destino al que se envía el mensaje cuando coincide con un filtro concreto.  
  
### <a name="define-filters"></a>Definir filtros  
  
1. Para enrutar los mensajes en función del encabezado personalizado "RoundingCalculator" que la aplicación cliente agrega al mensaje, defina un filtro que use una consulta XPath para comprobar la presencia de este encabezado. Dado que este encabezado se define mediante un espacio de nombres personalizado, agregue también una entrada de espacio de nombres que defina un prefijo de espacio de nombres personalizado de "personalizado" que se usa en la consulta XPath. En el siguiente ejemplo, se define la sección de enrutamiento necesaria, la tabla de espacio de nombres y el filtro XPath.  
  
    ```xml  
    <routing>  
          <!-- use the namespace table element to define a prefix for our custom namespace-->  
          <namespaceTable>  
            <add prefix="custom" namespace="http://my.custom.namespace/"/>  
          </namespaceTable>  
          <filters>  
            <!--define the different message filters-->  
            <!--define an xpath message filter to look for the custom header coming from the client-->  
            <filter name="XPathFilter" filterType="XPath"
                    filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 'rounding'"/>  
          </filters>  
    </routing>  
    ```  
  
     Este **MessageFilter** busca un encabezado RoundingCalculator en el mensaje que contiene un valor de "redondeo". El cliente establece este encabezado para indicar que el mensaje se debería enrutar al servicio de roundingCalc.  
  
    > [!NOTE]
    > El prefijo de espacio de nombres s12 se define `http://www.w3.org/2003/05/soap-envelope`de forma predeterminada en la tabla de espacio de nombres y representa el espacio de nombres.
  
2. También debe definir los filtros que buscan mensajes recibidos en los dos puntos de conexión virtuales. El primer punto de conexión virtual es el punto de conexión "regular/calculador". El cliente puede enviar solicitudes a este extremo para indicar que el mensaje se debería enrutar al servicio de regularCalc. La siguiente configuración define un filtro que utiliza <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> para determinar si el mensaje llegó a través de un punto de conexión con el nombre especificado en filterData.  
  
    ```xml  
    <!--define an endpoint name filter looking for messages that show up on the virtual regular calculator endpoint-->  
    <filter name="EndpointNameFilter" filterType="EndpointName" filterData="calculatorEndpoint"/>  
    ```  
  
     Si el punto de conexión de servicio denominado "calculatorEndpoint" `true`recibe un mensaje, este filtro se evalúa como .  
  
3. A continuación, defina un filtro que busque los mensajes enviados a la dirección de roundingEndpoint. El cliente puede enviar solicitudes a este punto de conexión para indicar que el mensaje se debería enrutar al servicio de roundingCalc. La siguiente configuración define un <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> filtro que utiliza el para determinar si el mensaje llegó al punto de conexión "redondeo/calculador".  
  
    ```xml  
    <!--define a filter looking for messages that show up with the address prefix.  The corresponds to the rounding calc virtual endpoint-->  
    <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress"  
            filterData="http://localhost/routingservice/router/rounding/"/>  
    ```  
  
     Si se recibe un mensaje en `http://localhost/routingservice/router/rounding/` una dirección que comienza con, este filtro se evalúa como **true**. Dado que la dirección base `http://localhost/routingservice/router` utilizada por esta configuración es y la dirección especificada para el roundingEndpoint es `http://localhost/routingservice/router/rounding/calculator`"redondeo/calculador", la dirección completa utilizada para comunicarse con este punto de conexión es , que coincide con este filtro.  
  
    > [!NOTE]
    > El filtro PrefixEndpointAddress no evalúa el nombre de host al realizar una coincidencia, porque se puede hacer referencia a un host único utilizando diversos nombres de host que pueden ser todos ellos métodos válidos para hacer referencia al host de la aplicación cliente. Por ejemplo, todos los nombres siguientes pueden hacer referencia al mismo host:  
    >
    > - localhost  
    > - 127.0.0.1  
    > - `www.contoso.com`  
    > - ContosoWeb01  
  
4. El filtro final debe admitir el enrutamiento de mensajes que llegan al punto de conexión general sin el encabezado personalizado. En este escenario, los mensajes deberían alternar entre los servicios de regularCalc y roundingCalc. Para admitir el enrutamiento "round robin" de estos mensajes, utilice un filtro personalizado que permita que una instancia de filtro coincida con cada mensaje procesado.  A continuación, se definen dos instancias de RoundRobinMessageFilter, que se agrupan para indicar que deberían alternar entre sí.  
  
    ```xml  
    <!-- Set up the custom message filters.  In this example,   
         we'll use the example round robin message filter,   
         which alternates between the references-->  
    <filter name="RoundRobinFilter1" filterType="Custom"  
                    customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly"  
                    filterData="group1"/>  
    <filter name="RoundRobinFilter2" filterType="Custom"  
                    customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly"  
                    filterData="group1"/>  
    ```  
  
     Durante el tiempo de ejecución, este tipo de filtro alterna entre todas las instancias de filtro definidas de este tipo que están configuradas como el mismo grupo en una recopilación. Esto hace que los mensajes procesados `true` por `RoundRobinFilter1` `RoundRobinFilter2`este filtro personalizado se alternen entre devolver for y .  
  
### <a name="define-filter-tables"></a>Definición de tablas de filtros  
  
1. Para asociar los filtros a extremos de cliente concretos, debe colocarlos dentro de una tabla de filtros. Este ejemplo de escenario también utiliza una configuración de prioridad de filtros, que es una configuración opcional que le permite indicar el orden en el que se procesan los filtros. Si no se especifica ninguna prioridad de filtro, todos los filtros se evalúan simultáneamente.  
  
    > [!NOTE]
    > Aunque una prioridad de filtro le permite controlar el orden en el que se procesan los filtros, puede afectar negativamente al rendimiento del servicio de enrutamiento. Cuando sea posible, cree una lógica de filtro para que no se requiera el uso de prioridades de filtro.  
  
     A continuación se define la tabla de filtros y se agrega el "XPathFilter" definido anteriormente a la tabla con una prioridad de 2. Esta entrada también especifica `XPathFilter` que si el mensaje coincide, `roundingCalcEndpoint`el mensaje se enrutará al archivo .  
  
    ```xml  
    <routing>  
    ...      <filters>  
    ...      </filters>  
          <filterTables>  
            <table name="filterTable1">  
              <entries>  
                <!--add the filters to the message filter table-->  
                <!--first look for the custom header, and if we find it,  
                    send the message to the rounding calc endpoint-->  
                <add filterName="XPathFilter" endpointName="roundingCalcEndpoint" priority="2"/>  
              </entries>  
            </table>  
          </filterTables>  
    </routing>  
    ```  
  
     Al especificar una prioridad de filtro, los filtros con prioridad máxima se evalúan primero. Si coinciden uno o más filtros en un nivel de prioridad concreto, no se evaluará ningún filtro en los niveles de menor prioridad. Para este escenario, 2 es la prioridad máxima especificada y ésta es la única entrada de filtro en este nivel.  
  
2. Las entradas de filtro se han definido para comprobar si se recibe un mensaje se recibe en un extremo concreto inspeccionando el nombre de extremo o el prefijo de dirección. Las siguientes entradas suman ambas entradas de filtro a la tabla de filtros y las asocian a los puntos de conexión de destino a los que se enrutará el mensaje. Estos filtros están establecidos con una prioridad 1 para indicar que solo se deberían ejecutar si el filtro XPath anterior no coincidiera con el mensaje.  
  
    ```xml  
    <!--if the header wasn't there, send the message based on which virtual endpoint it arrived at-->  
    <!--we determine this through the endpoint name, or through the address prefix-->  
    <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint" priority="1"/>  
    <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint" priority="1"/>  
    ```  
  
     Dado que estos filtros tienen una prioridad de filtro de 1, solo se evaluarán si el filtro de nivel de prioridad 2 no coincide con el mensaje. Asimismo, como ambos filtros tienen el mismo nivel de prioridad, se evaluarán simultáneamente. Dado que ambos filtros son mutuamente excluyentes, es posible que solo uno u otro coincida con un mensaje.  
  
3. Si un mensaje no coincide con ninguno de los filtros anteriores, dicho mensaje se recibió a través del punto de conexión de servicio genérico y no contenía ninguna información de encabezado que indicara dónde enrutarlo. El filtro personalizado administrará estos mensajes para equilibrar su carga entre los dos servicios de la calculadora. En el siguiente ejemplo, se muestra cómo agregar las entradas de filtro a la tabla de filtros; cada filtro se asocia a uno de los dos puntos de conexión de destino.  
  
    ```xml  
    <!--if none of the other filters have matched,   
        this message showed up on the default router endpoint,   
        with no custom header-->  
    <!--round robin these requests between the two services-->  
    <add filterName="RoundRobinFilter1" endpointName="regularCalcEndpoint" priority="0"/>  
    <add filterName="RoundRobinFilter2" endpointName="roundingCalcEndpoint" priority="0"/>  
    ```  
  
     Dado que estas entradas especifican una prioridad de 0, solo se evaluarán si ningún filtro con una prioridad más alta coincide con el mensaje. Asimismo, como ambos tienen la misma prioridad, se evaluarán simultáneamente.  
  
     Tal y como se ha indicado previamente, el filtro personalizado utilizado por estas definiciones de filtro solo evalúa uno u otro como `true` por cada mensaje recibido. Dado que solo se han definido dos filtros utilizando este filtro, con la misma configuración de grupo especificada, el efecto es que el servicio de enrutamiento alterna entre el envío a regularCalcEndpoint y a RoundingCalcEndpoint.  
  
4. Para evaluar los mensajes con respecto a los filtros, la tabla de filtros debe estar asociada primero a los puntos de conexión de servicio que se utilizarán para recibir mensajes.  En el siguiente ejemplo, se muestra cómo asociar la tabla de enrutamiento a los extremos de servicio utilizando el comportamiento de enrutamiento:  
  
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
        <!--first create the general router endpoint-->  
        <endpoint address="general"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <!--create a virtual endpoint for the regular calculator service-->  
        <endpoint address="regular/calculator"  
                  binding="wsHttpBinding"  
                  name="calculatorEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <!--now create a virtual endpoint for the rounding calculator-->  
        <endpoint address="rounding/calculator"  
                  binding="wsHttpBinding"  
                  name="roundingEndpoint"  
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
                address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
      <namespaceTable>  
        <add prefix="custom" namespace="http://my.custom.namespace/"/>  
      </namespaceTable>  
      <filters>  
        <!--define the different message filters-->  
        <!--define an xpath message filter to look for the custom header coming from the client-->  
        <filter name="XPathFilter" filterType="XPath" filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 'rounding'"/>  
  
        <!--define an endpoint name filter looking for messages that show up on the virtual regular calculator endpoint-->  
        <filter name="EndpointNameFilter" filterType="EndpointName" filterData="calculatorEndpoint"/>  
  
        <!--define a filter looking for messages that show up with the address prefix.  The corresponds to the rounding calc virtual endpoint-->  
        <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress" filterData="http://localhost/routingservice/router/rounding/"/>  
  
        <!--Set up the custom message filters.  In this example, we'll use the example round robin message filter, which alternates between the references-->  
        <filter name="RoundRobinFilter1" filterType="Custom" customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly" filterData="group1"/>  
        <filter name="RoundRobinFilter2" filterType="Custom" customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly" filterData="group1"/>  
      </filters>  
      <filterTables>  
        <table name="filterTable1">  
          <entries>  
            <!--add the filters to the message filter table-->  
            <!--first look for the custom header, and if we find it, send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilter" endpointName="roundingCalcEndpoint" priority="2"/>  
  
            <!--if the header wasn't there, send the message based on which virtual endpoint it arrived at-->  
            <!--we determine this through the endpoint name, or through the address prefix-->  
            <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint" priority="1"/>  
            <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint" priority="1"/>  
  
            <!--if none of the other filters have matched, this message showed up on the default router endpoint, with no custom header-->  
            <!--round robin these requests between the two services-->  
            <add filterName="RoundRobinFilter1" endpointName="regularCalcEndpoint" priority="0"/>  
            <add filterName="RoundRobinFilter2" endpointName="roundingCalcEndpoint" priority="0"/>  
          </entries>  
        </table>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Servicios de enrutamiento](../../../../docs/framework/wcf/samples/routing-services.md)
