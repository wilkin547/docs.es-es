---
title: "&lt;filtro&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;filtro&gt;
Define un filtro del enrutamiento, que determina el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se va a utilizar al evaluar los mensajes entrantes, así como cualquier dato o parámetro de compatibilidad requerido por el filtro.  
  
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
  
|Atributo|Descripción|  
|--------------|-----------------|  
|customType|Cadena que contiene el nombre de tipo completo del tipo personalizado que se va a usar como filtro. Si `filterType`se establece en `custom`, este atributo contiene el nombre de tipo completo de la clase que se va a crear. `filterData` también puede contener valores que se van a usar durante la evaluación del filtro de tipo personalizado.|  
|filterData|Cadena que contiene los datos del filtro.  Para obtener más información sobre cómo especificar este atributo, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.|  
|filterType|Cadena que contiene el tipo de filtro.  Este atributo es del tipo <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Para obtener más información sobre su funcionamiento con el atributo `filterData`, vea <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.|  
|name|Cadena que contiene el nombre único de este elemento de filtro.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Sección de configuración para definir un conjunto de filtros de enrutamiento, que determinan el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se va a utilizar al evaluar los mensajes entrantes.|  
  
## Vea también  
 [System.ServiceModel.Routing.Configuration.FilterElement](assetId:///System.ServiceModel.Routing.Configuration.FilterElement?qualifyHint=False&amp;autoUpgrade=True)   
 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>   
 <xref:System.ServiceModel.Routing.Configuration.FilterType>