---
title: '&lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: c11fd38e7c40f740d4c1c36ab87c44744ed0daab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627997"
---
# <a name="ltbackuplistgt"></a>&lt;backupList&gt;
Representa una sección de configuración para definir una lista de reserva que enumera un conjunto de puntos de conexión que desea que el servicio de enrutamiento use en caso de que no se puede alcanzar el punto de conexión principal. Si el primer punto de conexión en la lista está desconectado, el servicio de enrutamiento realizará automáticamente una conmutación por error al siguiente de la lista.  De este modo, dispone de una forma rápida de agregar confiabilidad a la aplicación sin tener que enseñar a la aplicación cliente cómo controlar modelos complejos o dónde implementar todos sus servicios.  
  
 \<system.serviceModel>  
\<routing>  
\<backupLists>  
\<backupList >  
  
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
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Lista de puntos de conexión auxiliares.|  
  
## <a name="remarks"></a>Comentarios  
 Esta sección contiene una colección ordenada de puntos de conexión a los que se transmitirá un mensaje en caso de que se produzca una excepción de comunicaciones cuando se envíe al punto de conexión primario.  
  
 Si un envío al punto de conexión principal aparece en el `endpointName` atributo de [ \<Agregar >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) produce un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al primer punto de conexión en este sección de configuración. Si esto también genera un error con una excepción de comunicaciones, el servicio de enrutamiento intentará enviar el mensaje al siguiente mensaje que contiene esta sección hasta que el intento de envío se realice correctamente, que devuelva un error distinto de una excepción de comunicaciones o que todos los puntos de conexión de la colección hayan devuelto un error.  
  
 En el siguiente ejemplo, si un envío al punto de conexión primario denominado "Destino" devuelve una excepción de comunicaciones, el servicio intentará enviar el mensaje a "alternateServiceQueue". Si este intento también devuelve una excepción de comunicación, el servicio de enrutamiento intentará enviar el mensaje al punto de conexión siguiente de la colección.  
  
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
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
