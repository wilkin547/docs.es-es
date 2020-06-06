---
title: <serviceDiscovery>
ms.date: 03/30/2017
ms.assetid: a3c68a4a-fc95-43c5-aacb-785936c0cf39
ms.openlocfilehash: 7ac067e84f2a4d2724e3d8f2d0af9b220fd15538
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399641"
---
# \<serviceDiscovery>
Especifica la detectabilidad de extremos de servicio.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceDiscovery>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </announcementEndpoints>
        <discoveryEndpoints>
          <endpoint name="String"
                    kind="Type" />
        </discoveryEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<announcementEndpoint>](announcementendpoint.md)|Colección de puntos de conexión de anuncio. Utilice esta sección para especificar los puntos de conexión que se van a usar para enviar mensajes de anuncio.|  
|[\<discoveryEndpoint>](discoveryendpoint.md)|Colección de extremos de detección. Utilice esta sección para especificar los puntos de conexión en los que se van a escuchar mensajes de detección.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Especifica un elemento de comportamiento.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración convierte todos los puntos de conexión de ese servicio en detectables. Puede seguir configurando las características de detección de estos puntos de conexión mediante los [\<discoveryEndpoint>](discoveryendpoint.md) [\<announcementEndpoint>](announcementendpoint.md) elementos secundarios o. Use la [\<announcementEndpoint>](announcementendpoint.md) sección para configurar los anuncios especificando la configuración del punto de conexión que se va a usar para enviar anuncios de servicio (en línea/Hola y sin conexión/adiós). Use la [\<discoveryEndpoint>](discoveryendpoint.md) sección para especificar manualmente el punto de conexión en el que se van a escuchar los mensajes de detección.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de configuración especifica que CalculatorService va a ser detectable y especifica opcionalmente el punto de conexión del anuncio que se va a utilizar.  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery>
        <announcementEndpoints>
          <endpoint name="udpEndpoint"
                    kind="udpAnnouncementEndpoint" />
        </announcementEndpoints>
      </serviceDiscovery>
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>
