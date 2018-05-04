---
title: '&lt;discoveryEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: 6a352fbfced08001f76dceaff283d6bca25f56f9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltdiscoveryendpointgt"></a>&lt;discoveryEndpoint&gt;

Este elemento de configuración define un punto de conexión estándar con un contrato de detección fijo. Cuando se agrega a la configuración de servicio, especifica dónde escuchar los mensajes de detección. Cuando se agrega a la configuración del cliente, especifica dónde enviar las consultas de detección.  
  
\<system.serviceModel>  
\<standardEndpoints >  
  
## <a name="syntax"></a>Sintaxis

```xml
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed" 
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxResponseDelay="Timespan" 
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos

| Atributo        | Descripción |  
| ---------------- | ----------- |  
| discoveryMode    | Cadena que especifica el modo del protocolo de detección. Los valores válidos son "Adhoc" y "Administrado". En modo administrado, el protocolo se basa en un proxy de detección, que actúa como un repositorio de servicios detectables. El modo Adhoc requiere que el protocolo utilice el mecanismo de multidifusión UDP para buscar servicios disponibles. Para obtener más información sobre la propiedad, vea <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>. |  
| discoveryVersion | Cadena que especifica una de las dos versiones del protocolo WS-Discovery. Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005. Este valor es del tipo <xref:System.ServiceModel.Discovery.DiscoveryVersion>. |  
| maxResponseDelay | Un valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar ciertos mensajes como Probe Match o Resolve Match.<br /><br /> Si se envían todos los ProbeMatches al mismo tiempo, puede producirse una tormenta de la red. Para evitar que esto se produzca, ProbeMatches se envía con un retraso aleatorio entre cada ProbeMatch. El retraso aleatorio se encuentra en el intervalo entre 0 y el valor establecido por este atributo. Si este atributo está establecido en 0, los mensajes ProbeMatches se envían en un bucle ajustado sin ningún retraso. En caso contrario, los mensajes ProbeMatches se envían con cierto retraso aleatorio de modo que el tiempo total empleado en enviar todos los mensajes ProbeMatches no supere maxResponseDelay. Este valor solo es pertinente para los servicios, clientes no lo utilizan. |  
| `name`           | Cadena que especifica el nombre de la configuración del extremo estándar. El nombre se utiliza en el atributo `endpointConfiguration` del extremo del servicio para vincular un extremo estándar a su configuración. |  
  
### <a name="child-elements"></a>Elementos secundarios

Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios

| Elemento | Descripción |  
| ------- | ----------- |  
| [\<standardEndpoints >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md) | Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas. |  
  
## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestra un servicio que escucha mensajes de detección a través de un transporte de multidifusión de red del mismo nivel. El ejemplo especifica explícitamente la versión WS-Discovery April 2005.  
  
La configuración del extremo estándar se define por servicio y no se puede compartir a través del servicio. Si otro servicio quisiera tener el mismo punto de conexión de detección, habría que agregar la misma configuración a la sección de dicho servicio.  
  
```xml
<services>  
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding" 
              address="calculator" 
              contract="ICalculatorService" />  
    <endpoint name="peerNetDiscovery"  
              binding="peerTcpBinding"  
              address="net.p2p://discoveryMesh/multicast"  
              kind="discoveryEndpoint"  
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"  
              bindingConfiguration="discoveryPeerTcpBindingConfig" />      
  </service>  
</services>  
<standardEndpoints>  
  <discoveryEndpoint>  
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"                         
                      version="WSDiscoveryApril2005" />  
  </discoveryEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a>Vea también

<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
