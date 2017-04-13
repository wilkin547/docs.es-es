---
title: "&lt;dynamicEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;dynamicEndpoint&gt;
Este elemento de configuración define un extremo estándar que contiene información para permitir que una aplicación funcione como un programa cliente que pueda buscar la dirección del extremo dinámicamente en tiempo de ejecución.  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <dynamicEndpoint>   
          <standardEndpoint>  
             <discoveryClientSettings discoveryEndpoint=”String” >  
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
             </discoveryClientSettings>  
          <standardEndpoint>  
       </dynamicEndpoint>          
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<discoveryClientSettings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|Contiene la configuración que necesita una aplicación para participar en el proceso de detección del servicio como un cliente.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Colección de extremos estándar que son extremos predefinidos con una o más de sus propiedades \(dirección, enlace, contrato\) fijas.|  
  
## Vea también  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>   
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>