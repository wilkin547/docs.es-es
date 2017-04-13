---
title: "&lt;add&gt; de &lt;backupList&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;add&gt; de &lt;backupList&gt;
Representa un elemento de configuración que define un elemento de extremo de reserva.  
  
## Sintaxis  
  
```vb  
  
<routing>  
  <backupLists>  
    <backupList name="String">  
      <add endpointName="String" />  
    </backupList>    
  </backupLists>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Cadena que especifica el nombre del extremo de reserva.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Contiene una lista de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el extremo primario.|  
  
## Vea también  
 [System.ServiceModel.Routing.Configuration.BackupEndpointElement](assetId:///System.ServiceModel.Routing.Configuration.BackupEndpointElement?qualifyHint=False&amp;autoUpgrade=True)