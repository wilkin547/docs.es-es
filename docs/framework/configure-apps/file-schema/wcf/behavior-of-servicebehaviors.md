---
title: "Elemento &lt;behavior&gt; de &lt;serviceBehaviors&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Elemento &lt;behavior&gt; de &lt;serviceBehaviors&gt;
El elemento `behavior` contiene una colección de valores para el comportamiento de un servicio.  Su `name` indiza cada comportamiento.  Los servicios pueden vincularse a cada comportamiento a través de este nombre mediante el atributo `behaviorConfiguration` del elemento [\<extremo\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md).  De esta forma, los extremos pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración.  A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.  Para obtener más información sobre la configuración predeterminada, así como sobre enlaces y comportamientos sin nombre, vea [Configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!NOTE]
>  Los elementos de comportamiento específicos de las actividades de Windows Workflow, como el elemento [\<sendMessageChannelCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md), se documentan en la página [\<comportamiento\> de \<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md).  
  
## Sintaxis  
  
```  
  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
       <behavior name="String" />  
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Una cadena única que contiene el nombre de la configuración del comportamiento.  Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.  A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre.  Para obtener más información sobre la configuración predeterminada, así como sobre enlaces y comportamientos sin nombre, vea [Configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [Configuración simplificada de los servicios de WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)|Contiene los datos de configuración para DataContractSerializer.|  
|[\<persistenceProvider\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistenceprovider.md)|Especifica el tipo de la implementación de proveedor de persistencia que se va a usar, así como el tiempo de espera que se va a utilizar en las operaciones de persistencia.|  
|[\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|Proporciona acceso en tiempo de ejecución al servicio de enrutamiento para permitir la modificación dinámica de la configuración del enrutamiento.|  
|[\<serviceAuthenticationManager\>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthenticationmanager.md)|Proporciona un elemento de configuración del flujo de trabajo que establece la validez de una transmisión, mensaje o autor en el nivel del servicio.|  
|[\<serviceAuthorization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)|Especifica valores que autorizan que el acceso repare las operaciones.|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Especifica la credencial que se va a utilizar para autenticar el servicio y los valores relacionados con la validación de la credencial del cliente.|  
|[\<serviceDebug\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)|Especifica las características de depuración y de información de ayuda para un servicio [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].|  
|[\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)|Especifica la detectabilidad de extremos de servicio.|  
|[\<serviceMetadata\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)|Especifica la publicación de metadatos e información asociada del servicio.|  
|[\<serviceSecurityAudit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)|Especifica valores que habilitan la auditoría de eventos de seguridad durante las operaciones del servicio.|  
|[\<serviceThrottling\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md)|Especifica el mecanismo de la limitación de peticiones de un servicio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].|  
|[\<serviceTimeouts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicetimeouts.md)|Especifica el tiempo de espera para un servicio.|  
|[\<workflowRuntime\>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|Especifica la configuración de una instancia de WorkflowRuntime para hospedar los servicios [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] basados en flujo de trabajo.|  
|[\<useRequestHeadersForMetadataAddress\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|Habilita la recuperación de información de direcciones de metadatos de los encabezados de mensajes de solicitud.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|Colección de elementos de comportamiento del servicio.|