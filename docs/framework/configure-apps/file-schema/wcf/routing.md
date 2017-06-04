---
title: "&lt;enrutar&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;enrutar&gt;
Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se va a utilizar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que se van a enviar mensajes cuando coincida un filtro.  
  
## Sintaxis  
  
```vb  
  
<routing>  
      <filters>  
        <filter customType=”String”  
                filterData=”String”  
                filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"   
                name="String" />  
      </filters>  
      <routingTables>  
        <table name="String">  
          <entries>  
            <add endpoint="String"   
                 filterName="String"   
                 priority="Integer" />  
          </entries>  
        </table>  
      </routingTables>  
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
|[\<filtros\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Contiene un conjunto de filtros de enrutamiento que determinan el tipo de MessageFilter de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se usará al evaluar los mensajes entrantes.|  
|[\<filterTables\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md)|Contiene asignaciones entre los filtros de enrutamiento y los extremos de destino para especificar qué extremo usar cuando coincide el filtro.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|system.ServiceModel|Elemento raíz de todos los elementos de configuración de WCF.|  
  
## Vea también  
 [System.ServiceModel.Routing.Configuration.RoutingSection](assetId:///System.ServiceModel.Routing.Configuration.RoutingSection?qualifyHint=False&amp;autoUpgrade=True)