---
title: "&lt;filterTables&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;filterTables&gt;
Representa una sección de configuración para definir tablas de enrutamiento que contienen las asignaciones entre los filtros de enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.  
  
## Sintaxis  
  
```vb  
  
<routing>  
      <filterTables>  
        <filterTable name="String">  
          <entries>  
            <add backupList=”String”  
                 endpointName="String"   
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
|[\<filtros\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Tabla de enrutamiento que contiene las asignaciones entre los filtros de enrutamiento y los extremos de destino a los que enviar mensajes cuando coincida el filtro.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Sección de configuración que contiene filtros y tablas de enrutamiento.|  
  
## Vea también  
 [System.ServiceModel.Routing.Configuration.RoutingSection](assetId:///System.ServiceModel.Routing.Configuration.RoutingSection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.ServiceModel.Routing.Configuration.FilterTableCollection](assetId:///System.ServiceModel.Routing.Configuration.FilterTableCollection?qualifyHint=False&amp;autoUpgrade=True)