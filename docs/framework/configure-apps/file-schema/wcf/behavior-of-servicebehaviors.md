---
title: <behavior> de <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 115f94fc3f17dc5b4dd1ee3a090f2c9d121f810b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139734"
---
# <a name="behavior-of-servicebehaviors"></a>\<behavior> de \<serviceBehaviors>
El elemento `behavior` contiene una colección de valores para el comportamiento de un servicio. Su `name` indiza cada comportamiento. Los servicios se pueden vincular a cada comportamiento a través de este nombre mediante el `behaviorConfiguration` atributo del [\<endpoint>](endpoint-element.md) elemento. De esta forma, los extremos pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración. A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!NOTE]
> Los elementos de comportamiento específicos de las actividades de flujo de trabajo de Windows, como el [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) elemento, se documentan en la [ \<behavior> de \<serviceBehaviors> ](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) la página.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
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
|[\<dataContractSerializer>](datacontractserializer-element.md)|Contiene los datos de configuración para DataContractSerializer.|  
|[\<persistenceProvider>](persistenceprovider.md)|Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.|  
|[\<routing>](routing-of-servicebehavior.md)|Proporciona acceso en tiempo de ejecución al servicio de enrutamiento para permitir la modificación dinámica de la configuración del enrutamiento.|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, mensaje o autor en el nivel del servicio.|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|Especifica valores que autorizan que el acceso repare las operaciones.|  
|[\<serviceCredentials>](servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
|[\<serviceDebug>](servicedebug.md)|Especifica las características de depuración y de información de ayuda para un servicio Windows Communication Foundation (WCF).|  
|[\<serviceDiscovery>](servicediscovery.md)|Especifica la detectabilidad de extremos de servicio.|  
|[\<serviceMetadata>](servicemetadata.md)|Especifica la publicación de metadatos e información asociada del servicio.|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|Especifica valores que habilitan la auditoría de eventos de seguridad durante las operaciones del servicio.|  
|[\<serviceThrottling>](servicethrottling.md)|Especifica el mecanismo de limitación de un servicio WCF.|  
|[\<serviceTimeouts>](servicetimeouts.md)|Especifica el tiempo de espera para un servicio.|  
|[\<workflowRuntime>](workflowruntime.md)|Especifica la configuración de una instancia de WorkflowRuntime para hospedar servicios WCF basados en el flujo de trabajo.|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|Colección de elementos de comportamiento del servicio.|
