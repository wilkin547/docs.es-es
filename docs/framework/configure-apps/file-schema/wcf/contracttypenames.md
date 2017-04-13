---
title: "&lt;contractTypeNames&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;contractTypeNames&gt;
Una sección de configuración que especifica una lista de nombres de tipos de contrato, que son los nombres del contrato de los servicios que se están buscando, y los criterios que suelen usarse al buscar un servicio.  Si se especifica más de un nombre del contrato, solo responderán los extremos del servicio que coincidan con TODOS los contratos.  Observe que en [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] un extremo sólo puede admitir un contrato.  
  
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
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|Un nombre de tipo de contrato es una propiedad que hace referencia al conjunto de criterios que suele usarse al buscar un servicio.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<findCriteria\>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|Elemento de configuración que proporciona un conjunto de criterios utilizado por una aplicación cliente para buscar un servicio de detección.  Los criterios pueden agruparse en criterios de búsqueda \(que especifican qué servicios está buscando\) y en criterios de finalización de búsqueda \(cuánto tiempo debería durar la búsqueda\).|  
  
## Vea también  
 <xref:System.ServiceModel.Discovery.FindCriteria>   
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>   
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>