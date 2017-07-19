---
title: "&lt;cliente&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#client"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# &lt;cliente&gt;
El elemento `client` define una lista de extremos a los que un cliente puede conectarse.  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
    <client>  
        <endpoint>  
        </endpoint>  
                <metadata>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguna  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<extremo\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|Contiene una colección de elementos de extremo, que especifica los extremos a los que este cliente puede conectarse.|  
|[\<metadatos\>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|Contiene los valores para procesar los metadatos.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|El elemento raíz de todos los elementos de configuración de la Windows Communication Foundation \(WCF\).|  
  
## Comentarios  
 La sección `client` define una lista de extremos a los que un cliente puede conectarse.  Cada extremo enumerado en la sección de cliente define su propio enlace, comportamiento y contrato.  La combinación de los atributos `contract` y `name` identifica singularmente.  El código de cliente especifica el `name` para conectar el servicio que el cliente implementa a un extremo.  Si se omite el atributo de `name`, el extremo actúa como el extremo predeterminado para el contrato que implementa.  
  
 Además, esta sección también especifica los valores para procesar los metadatos.  
  
## Ejemplo  
  
```  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.ClientSection>   
 <xref:System.ServiceModel.Configuration.MetadataElement>   
 [Configuración del cliente de WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [Clientes](../../../../../docs/framework/wcf/feature-details/clients.md)