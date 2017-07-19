---
title: "&lt;scopes&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;scopes&gt;
Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar extremos de servicio durante la consulta.  
  
## Sintaxis  
  
```  
  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="String">  
      <endpointDiscovery enable="Boolean">  
        <scopes>  
          <add scope="URI"/>  
        </scopes>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|[\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|Agrega la información sobre el ámbito del extremo que se puede usar en los criterios de coincidencia para buscar los servicios.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<endpointDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|Especifica las distintas configuraciones de detección para un extremo, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.|  
  
## Vea también  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>