---
title: <add> de <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 53af01a519c244376b262db1f6515a438dcc554f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663370"
---
# <a name="add-of-backuplist"></a>\<Agregar > de \<backupList >
Representa un elemento de configuración que define un elemento de extremo de reserva.  
  
 \<system.serviceModel>  
\<> de enrutamiento  
\<> backupLists  
\<> backupList  
\<add>  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|name|Cadena que especifica el nombre del extremo de reserva.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<> de enrutamiento](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Contiene una lista de extremos que le gustaría que usara el servicio de enrutamiento en caso de que no se pudiera alcanzar el punto de conexión principal.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
