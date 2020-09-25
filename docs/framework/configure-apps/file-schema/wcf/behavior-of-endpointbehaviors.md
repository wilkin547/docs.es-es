---
title: <behavior> de <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: d191b968e1c3fd1db0837ba7e03f210a1b00062d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201504"
---
# <a name="behavior-of-endpointbehaviors"></a>\<behavior> de \<endpointBehaviors>

El elemento `behavior` contiene una colección de valores para el comportamiento de un punto de conexión. Su `name` indiza cada comportamiento. Los puntos de conexión se pueden vincular a cada comportamiento a través de este nombre. A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
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
  
|Atributo|Descripción|  
|---------------|-----------------|  
|name|Una cadena única que contiene el nombre de la configuración del comportamiento. Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento. A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|Especifica las credenciales usadas para autenticar el cliente en un servicio.|  
|[\<callbackDebug>](callbackdebug.md)|Especifica la depuración del servicio para un objeto de devolución de llamada de Windows Communication Foundation (WCF).|  
|[\<callbackTimeouts>](callbacktimeouts.md)|Especifica el tiempo de espera para la devolución de la llamada del cliente.|  
|[\<clientVia>](clientvia.md)|Especifica la ruta que un mensaje debe tomar.|  
|[\<dataContractSerializer>](datacontractserializer.md)|Contiene los datos de configuración para DataContractSerializer.|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|Especifica un comportamiento del extremo que permite que un servicio envíe respuestas de forma asincrónica.|  
|[\<enableWebScript>](enablewebscript.md)|Habilita el comportamiento del extremo que permite utilizar el servicio de las páginas web de AJAX de ASP.NET. El comportamiento solo se debe usar junto con el \<webHttpBinding> enlace estándar o el \<webMessageEncoding> elemento de enlace.|  
|[\<endpointDiscovery>](endpointdiscovery.md)|Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.|  
|[\<soapProcessing>](soapprocessing.md)|Define el comportamiento del punto de conexión de cliente usado para serializar entre distintos tipos de enlaces y versiones de mensajes.|  
|[\<synchronousReceive>](synchronousreceive-element.md)|Especifica el comportamiento de tiempo de ejecución para recibir los mensajes en una aplicación de servicio o de cliente. No tiene ningún atributo o elementos secundarios.|  
|[\<transactedBatching>](transactedbatching.md)|Especifica si el procesamiento por lotes de la transacción se admite para las operaciones de recepción.|  
|[\<webHttp>](webhttp.md)|Especifica WebHttpBehavior en un punto de conexión a través de la configuración. Este comportamiento, cuando se usa junto con el \<webHttpBinding> enlace estándar, habilita el modelo de programación web para un servicio WCF.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|Una colección de elementos de comportamiento del extremo.|
