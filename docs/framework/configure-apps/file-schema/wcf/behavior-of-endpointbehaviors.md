---
title: <behavior> de <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 81c9ec7bd82fa0b947e438632b293ab9110067f5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398237"
---
# <a name="behavior-of-endpointbehaviors"></a>\<comportamiento > de \<endpointBehaviors >
El elemento `behavior` contiene una colección de valores para el comportamiento de un punto de conexión. Su `name` indiza cada comportamiento. Los puntos de conexión se pueden vincular a cada comportamiento a través de este nombre. A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> endpointBehaviors**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<comportamiento >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|Nombre|Una cadena única que contiene el nombre de la configuración del comportamiento. Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento. A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Especifica las credenciales usadas para autenticar el cliente en un servicio.|  
|[\<callbackDebug>](callbackdebug.md)|Especifica la depuración del servicio para un objeto de devolución de llamada de Windows Communication Foundation (WCF).|  
|[\<callbackTimeouts>](callbacktimeouts.md)|Especifica el tiempo de espera para la devolución de la llamada del cliente.|  
|[\<clientVia>](clientvia.md)|Especifica la ruta que un mensaje debe tomar.|  
|[\<dataContractSerializer>](datacontractserializer.md)|Contiene los datos de configuración para DataContractSerializer.|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|Especifica un comportamiento del extremo que permite que un servicio envíe respuestas de forma asincrónica.|  
|[\<enableWebScript>](enablewebscript.md)|Habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET. El comportamiento solo se debe usar junto con la \<> de enlace de webHttpBinding o el elemento de enlace de > de \<webMessageEncoding.|  
|[\<endpointDiscovery>](endpointdiscovery.md)|Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.|  
|[\<soapProcessing>](soapprocessing.md)|Define el comportamiento del punto de conexión de cliente usado para serializar entre distintos tipos de enlaces y versiones de mensajes.|  
|[\<synchronousReceive>](synchronousreceive-element.md)|Especifica el comportamiento de tiempo de ejecución para recibir los mensajes en una aplicación de servicio o de cliente. No tiene ningún atributo o elementos secundarios.|  
|[\<transactedBatching>](transactedbatching.md)|Especifica si el procesamiento por lotes de la transacción se admite para las operaciones de recepción.|  
|[\<webHttp>](webhttp.md)|Especifica WebHttpBehavior en un punto de conexión a través de la configuración. Este comportamiento, cuando se usa junto con \<webHttpBinding > enlace estándar, habilita el modelo de programación web para un servicio WCF.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|Una colección de elementos de comportamiento del extremo.|
