---
title: "&lt;discoveryClient&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;discoveryClient&gt;
Elemento de configuración para crear un enlace personalizado que habilita una aplicación cliente para buscar automáticamente un servicio detectable y encontrar su dirección en tiempo de ejecución.  
  
## Sintaxis  
  
```  
  
<discoveryClient discoveryEndpoint=”String” >  
   <findCriteria duration=”TimeSpan”  
       maxResults=”Integer”   
       scopeMatchBy=”Uri” >  
       <contractTypeNames>  
          <add name="String" namespace="String" />  
       <contractTypeNames>  
       <extensions />  
       <scopes>  
          <add scope="URI"/>  
       </scopes>  
   </findCriteria>  
</discoveryClient>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|discoveryEndpoint|Cadena que contiene el nombre del extremo de la detección que habilita una aplicación cliente para buscar un servicio detectable automáticamente y encontrar su dirección en tiempo de ejecución.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.  Los criterios pueden agruparse en criterios de búsqueda \(que especifican qué servicios está buscando\) y en criterios de finalización de búsqueda \(cuánto tiempo debería durar la búsqueda\).|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Vea también  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>   
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>