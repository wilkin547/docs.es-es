---
title: <add> de <entries>
ms.date: 03/30/2017
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
ms.openlocfilehash: 690fd07159e07b7e037f7330b31fdcba423e80f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920126"
---
# <a name="add-of-entries"></a>\<Agregar > de \<entradas >
Representa una entrada de enrutamiento que asigna un filtro a un extremo de cliente que se definió previamente. Los mensajes que coincidan con este filtro se enviarán a este destino.  
  
 \<system.serviceModel>  
\<> de enrutamiento  
\<filterTables>  
\<filterTable>  
\<entradas >  
\<add>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|backupList|Cadena que especifica una referencia a una lista auxiliar de puntos de conexión.|  
|endpoint|Cadena que especifica una referencia a un extremo de cliente que recibirá mensajes que coincidan con el filtro especificado por el atributo `filterName`.|  
|filterName|Cadena que especifica una referencia a un elemento de filtro.|  
|prioridad|Entero que especifica la prioridad de esta entrada.<br /><br /> Las entradas en la tabla de enrutamiento se evaluarán según la prioridad, siendo 0 la prioridad más baja. Todas las entradas para una prioridad concreta se evalúan simultáneamente; si no se encuentra ninguna entrada coincidente para la prioridad actual, se evaluará el nivel de prioridad siguiente.<br /><br /> Este valor es opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<> de enrutamiento](routing.md)|Sección de configuración que contiene entradas de asignación de enrutamiento.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
