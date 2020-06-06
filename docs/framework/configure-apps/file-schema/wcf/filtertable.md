---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855195"
---
# \<filterTable>
Representa una tabla de enrutamiento que contiene una lista de filtros con respecto a la cual evaluar los mensajes y el extremo del cliente al que enrutar los mensajes a si el filtro se evalúa como verdadero.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<routing>
  <filterTables>
     name="String">
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
  
|Elemento|Descripción|  
|-------------|-----------------|  
|name|Cadena que contiene el nombre exclusivo de este elemento de configuración.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|Asignaciones entre los filtros de enrutamiento y los puntos de conexión de destino a los que enviar mensajes cuando el filtro coincide.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<routing>](routing.md)|Sección de configuración que contiene tablas de enrutamiento.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
