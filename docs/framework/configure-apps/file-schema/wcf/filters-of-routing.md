---
title: "&lt;filters&gt; de &lt;routing&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;filters&gt; de &lt;routing&gt;
Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se va a utilizar al evaluar los mensajes entrantes.  
  
## Sintaxis  
  
```vb  
  
<routing>  
      <filters>  
        <filter customType=”String”  
                filterData=”String”  
                filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"   
                name="String" />  
      </filters>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<filtro\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|Contiene un filtro del enrutamiento que determina el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se usará al evaluar los mensajes entrantes.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se va a utilizar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que se van a enviar mensajes cuando coincida un filtro.|  
  
## Vea también  
 [System.ServiceModel.Routing.Configuration.FilterElement](assetId:///System.ServiceModel.Routing.Configuration.FilterElement?qualifyHint=False&amp;autoUpgrade=True)