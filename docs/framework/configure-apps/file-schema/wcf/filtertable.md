---
title: "&lt;filterTable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;filterTable&gt;
Representa una tabla de enrutamiento que contiene una lista de filtros con respecto a la cual evaluar los mensajes y el extremo del cliente al que enrutar los mensajes a si el filtro se evalúa como verdadero.  
  
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
  
|Elemento|Descripción|  
|--------------|-----------------|  
|name|Cadena que contiene el nombre exclusivo de este elemento de configuración.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<filtros\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Asignaciones entre los filtros de enrutamiento y los extremos de destino a los que enviar mensajes cuando el filtro coincide.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Sección de configuración que contiene tablas de enrutamiento.|  
  
## Vea también  
 [System.ServiceModel.Routing.Configuration.RoutingSection](assetId:///System.ServiceModel.Routing.Configuration.RoutingSection?qualifyHint=False&amp;autoUpgrade=True)