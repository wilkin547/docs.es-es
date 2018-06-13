---
title: '&lt;Entradas&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: b9cc7f7736ffefaca68a0f197bd064a99c4dca9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746714"
---
# <a name="ltentriesgt"></a>&lt;Entradas&gt;
Una entrada del enrutamiento que contiene las asignaciones entre los filtros del enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando coincida el filtro.  
  
 \<system.serviceModel>  
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
