---
title: '&lt;entradas&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9b6d8d1c3797d60b26443e07cc527ea8b86f526e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltentriesgt"></a>&lt;entradas&gt;
Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.  
  
 \<system.serviceModel >  
\<enrutamiento >  
\<routingTables >  
\<tabla >  
\<las entradas >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<filtros >](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Asigna un filtro a un punto de conexión de cliente que se definió previamente. Los mensajes que coincidan con este filtro se enviarán a este destino.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Sección de configuración que contiene una tabla de enrutamiento.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
