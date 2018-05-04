---
title: '&lt;add&gt; de &lt;entries&gt;'
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: a6960c16c84c13d905f0993ee3cfc1cf67df07fc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltentriesgt"></a>&lt;add&gt; de &lt;entries&gt;
Representa una entrada de enrutamiento que asigna un filtro a un punto de conexión de cliente que se definió previamente. Los mensajes que coincidan con este filtro se enviarán a este destino.  
  
 \<system.serviceModel>  
\<enrutamiento >  
\<routingTables >  
\<tabla >  
\<las entradas >  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|backupList|Cadena que especifica una referencia a una lista auxiliar de extremos.|  
|extremo|Cadena que especifica una referencia a un extremo de cliente que recibirá mensajes que coincidan con el filtro especificado por el atributo `filterName`.|  
|filterName|Cadena que especifica una referencia a un elemento de filtro.|  
|priority|Entero que especifica la prioridad de esta entrada.<br /><br /> Las entradas en la tabla de enrutamiento se evaluarán según la prioridad, siendo 0 la prioridad más baja. Todas las entradas para una prioridad concreta se evalúan simultáneamente; si no se encuentra ninguna entrada coincidente para la prioridad actual, se evaluará el nivel de prioridad siguiente.<br /><br /> Este valor es opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<enrutamiento >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Sección de configuración que contiene entradas de asignación de enrutamiento.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
