---
title: Elemento &lt;behavior&gt; de &lt;serviceBehaviors&gt;
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 9cb5676897255d11b502080f4f7f3fb897027917
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362115"
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt"></a>Elemento &lt;behavior&gt; de &lt;serviceBehaviors&gt;
El elemento `behavior` contiene una colección de valores para el comportamiento de un servicio. Su `name` indiza cada comportamiento. Servicios pueden vincularse a cada comportamiento a través de este nombre mediante la `behaviorConfiguration` atributo de la [ \<extremo >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento. De esta forma, los puntos de conexión pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración. A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre. Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!NOTE]
>  Elementos de comportamiento específicos a las actividades de flujo de trabajo de Windows, como el [ \<sendMessageChannelCache >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md) elemento, se documentan en el [ \<comportamiento > de \< serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) página.  
  
 \<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
  
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
|name|Una cadena única que contiene el nombre de la configuración del comportamiento. Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento. A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre. Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)|Contiene los datos de configuración para DataContractSerializer.|  
|[\<persistenceProvider >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistenceprovider.md)|Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.|  
|[\<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|Proporciona acceso en tiempo de ejecución al servicio de enrutamiento para permitir la modificación dinámica de la configuración del enrutamiento.|  
|[\<serviceAuthenticationManager >](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthenticationmanager.md)|Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, mensaje o autor en el nivel del servicio.|  
|[\<serviceAuthorization >](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)|Especifica valores que autorizan que el acceso repare las operaciones.|  
|[\<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
|[\<serviceDebug >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)|Especifica las características de información de depuración y ayuda para un servicio de Windows Communication Foundation (WCF).|  
|[\<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)|Especifica la detectabilidad de puntos de conexión de servicio.|  
|[\<serviceMetadata >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)|Especifica la publicación de metadatos e información asociada del servicio.|  
|[\<serviceSecurityAudit >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)|Especifica valores que habilitan la auditoría de eventos de seguridad durante las operaciones del servicio.|  
|[\<serviceThrottling >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md)|Especifica el mecanismo de limitación de un servicio WCF.|  
|[\<serviceTimeouts >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicetimeouts.md)|Especifica el tiempo de espera para un servicio.|  
|[\<workflowRuntime >](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|Especifica la configuración para una instancia de WorkflowRuntime para hospedar servicios WCF basados en flujo de trabajo.|  
|[\<useRequestHeadersForMetadataAddress >](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|Colección de elementos de comportamiento del servicio.|
