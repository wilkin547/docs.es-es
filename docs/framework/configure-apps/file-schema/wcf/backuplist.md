---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 478211755b9131c03b72777ee95ff7223b9092c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850274"
---
# \<backupList>
Representa una sección de configuración para definir una lista auxiliar que enumera un conjunto de puntos de conexión que le gustaría que usara el servicio de enrutamiento en caso de que no se pueda alcanzar el punto de conexión primario. Si el primer extremo en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.  De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|name|Cadena que especifica el nombre usado para identificar esta lista de puntos de conexión.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<filter>](filter.md)||  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<routing>](routing.md)|Lista de extremos auxiliares.|  
  
## <a name="remarks"></a>Comentarios  
 Esta sección contiene una colección ordenada de extremos a los que se transmitirá un mensaje en caso de que se produzca una excepción de comunicaciones cuando se envíe al extremo primario.  
  
 Si un envío al punto de conexión principal que aparece en el `endpointName` atributo de [\<add>](add-of-entries.md) produce un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al primer punto de conexión en esta sección de configuración. Si esto también genera un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al siguiente mensaje que contiene esta sección hasta que el intento de envío se realice correctamente, que devuelva un error distinto de una excepción de comunicaciones o que todos los puntos de conexión de la colección hayan devuelto un error.  
  
 En el ejemplo siguiente, si un envío al punto de conexión principal denominado "Destination" devuelve una excepción de comunicación, el servicio intentará enviar el mensaje a "alternateServiceQueue". Si este intento también devuelve una excepción de comunicación, el servicio de enrutamiento intentará enviar el mensaje al punto de conexión siguiente de la colección.  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
