---
title: "&lt;backupList&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;backupList&gt;
Representa una sección de configuración para definir una lista de reserva que enumera un conjunto de extremos que desea que el servicio de enrutamiento use en caso de que no se pueda alcanzar el extremo primario. Si el primer extremo de la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista. De este modo, dispone de una forma rápida de agregar con fiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar patrones complejos o dónde se implementan todos sus servicios.  
  
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
|name|Cadena que especifica el nombre usado para identificar esta lista de extremos.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<filtro\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Lista de extremos auxiliares.|  
  
## Comentarios  
 Esta sección contiene una colección ordenada de extremos a los que se transmitirá un mensaje en caso de que se produzca una excepción de comunicaciones cuando se envíe al extremo primario.  
  
 Si se produce un error en el envío al extremo primario enumerado en el atributo `endpointName` de [\<agregar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al primer extremo de esta sección de configuración.  Si esto también genera un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al siguiente mensaje que contiene esta sección hasta que el intento de envío se realice correctamente, que devuelva un error distinto de una excepción de comunicaciones o que todos los extremos de la colección hayan devuelto un error.  
  
 En el siguiente ejemplo, si un envío al extremo primario denominado "Destino" devuelve una excepción de comunicación, el servicio intentará enviar el mensaje a "alternateServiceQueue".  Si este intento también devuelve una excepción de comunicación, el servicio de enrutamiento intentará enviar el mensaje al extremo siguiente de la colección.  
  
```  
  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
## Vea también  
 [System.ServiceModel.Routing.Configuration.BackupEndpointCollection](assetId:///System.ServiceModel.Routing.Configuration.BackupEndpointCollection?qualifyHint=False&amp;autoUpgrade=True)