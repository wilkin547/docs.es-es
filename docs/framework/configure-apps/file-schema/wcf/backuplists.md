---
title: "&lt;backupLists&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;backupLists&gt;
Representa una sección de configuración para definir un conjunto de servicios auxiliares usado en el control de errores.  Cada elemento secundario es una lista de reserva que enumera un conjunto de extremos que desea que el servicio de enrutamiento use en caso de que no se pueda alcanzar el extremo primario. Si el primer extremo de la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista. De este modo, dispone de una forma rápida de agregar conconfiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar patrones complejos o dónde se implementan todos sus servicios.  
  
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
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<filtro\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|Contiene una lista de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el extremo primario.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Representa una sección de configuración para definir un conjunto de filtros de enrutamiento, que determina el tipo de <xref:System.ServiceModel.Dispatcher.MessageFilter> de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] que se va a utilizar al evaluar los mensajes entrantes, así como las tablas de enrutamiento que definen los extremos de destino a los que se van a enviar mensajes cuando coincida un filtro.|  
  
## Vea también  
 [System.ServiceModel.Routing.Configuration.BackupListCollection](assetId:///System.ServiceModel.Routing.Configuration.BackupListCollection?qualifyHint=False&amp;autoUpgrade=True)