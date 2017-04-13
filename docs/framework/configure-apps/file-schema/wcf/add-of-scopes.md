---
title: "&lt;add&gt; de &lt;scopes&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;add&gt; de &lt;scopes&gt;
Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los extremos de servicio durante la consulta.  
  
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
  
|Atributo|Descripción|  
|--------------|-----------------|  
|ámbito|URI que contiene información sobre el ámbito del extremo que se puede usar en los criterios de coincidencia para buscar los servicios.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<scopes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar extremos de servicio durante la consulta.|  
  
## Vea también  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>