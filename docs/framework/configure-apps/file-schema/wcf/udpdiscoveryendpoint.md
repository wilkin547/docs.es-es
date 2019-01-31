---
title: <udpDiscoveryEndpoint>
ms.date: 03/30/2017
ms.assetid: 1f485329-2771-43bc-88de-df8f2faa3bb7
ms.openlocfilehash: af925a0f16e59cb6fec3ec246bd64a8f109d4d57
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270343"
---
# <a name="udpdiscoveryendpoint"></a>\<udpDiscoveryEndpoint>
Este elemento de configuración define un punto de conexión estándar que está preconfigurado para las operaciones de detección sobre un enlace de multidifusión UDP. Este punto de conexión tiene un contrato fijo y admite dos versiones del protocolo WS-Discovery. Además, tiene un enlace de UDP fijo y una dirección predeterminada según se indica en las especificaciones de WS-Discovery (WS-Discovery April 2005 o WS-Discovery V1.1).  
  
 \<system.ServiceModel>  
\<standardEndpoints>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed"
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005"
                        maxResponseDelay="Timespan"
                        multicastAddress="Uri"
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|discoveryMode|Cadena que especifica el modo del protocolo de detección. Los valores válidos son "Adhoc" y "Administrado". En modo administrado, el protocolo se basa en un proxy de detección, que actúa como un repositorio de servicios detectables. El modo Adhoc requiere que el protocolo utilice el mecanismo de multidifusión UDP para buscar servicios disponibles. Este valor es del tipo <xref:System.ServiceModel.Discovery.ServiceDiscoveryMode>.|  
|discoveryVersion|Cadena que especifica una de las dos versiones del protocolo WS-Discovery. Los valores válidos son WSDiscovery11 y WSDiscoveryApril2005. Este valor es del tipo <xref:System.ServiceModel.Discovery.DiscoveryVersion>.|  
|maxResponseDelay|Un valor Timespan que especifica el valor máximo del tiempo que el protocolo Discovery esperará antes de enviar ciertos mensajes como Probe Match o Resolve Match.<br /><br /> Si se envían todos los ProbeMatches al mismo tiempo, puede producirse una tormenta de la red. Para evitar que esto se produzca, ProbeMatches se envía con un retraso aleatorio entre cada ProbeMatch. El retraso aleatorio se encuentra en el intervalo entre 0 y el valor establecido por este atributo. Si este atributo está establecido en 0, los mensajes ProbeMatches se envían en un bucle ajustado sin ningún retraso. En caso contrario, los mensajes ProbeMatches se envían con cierto retraso aleatorio de modo que el tiempo total empleado en enviar todos los mensajes ProbeMatches no supere maxResponseDelay. Este valor solo es pertinente para los servicios, clientes no lo utilizan.|  
|multicastAddress|Uri que especifica una dirección de multidifusión que se va a usar para enviar y recibir los mensajes de detección. El valor predeterminado es la dirección de multidifusión como compatible con la especificación de protocolo.|  
|`name`|Cadena que especifica el nombre de la configuración del extremo estándar. El nombre se utiliza en el atributo `endpointConfiguration` del punto de conexión del servicio para vincular un punto de conexión estándar a su configuración.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<udpTransportSettings>](../../../../../docs/framework/configure-apps/file-schema/wcf/udptransportsettings.md)|Colección de valores que le permite configurar el transporte UDP para el punto de conexión UDP.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<standardEndpoints>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Colección de puntos de conexión estándar que son puntos de conexión predefinidos con una o más de sus propiedades (dirección, enlace, contrato) fijas.|  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra un servicio que realiza escuchas de mensajes de detección sobre un transporte de multidifusión UDP.  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService" />
    <endpoint name="DiscoveryEndpoint"
              kind="udpDiscoveryEndpoint" />
  </service>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="DiscoveryEndpoint"
                        version="WSDiscoveryApril2005" />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</services>
```  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
