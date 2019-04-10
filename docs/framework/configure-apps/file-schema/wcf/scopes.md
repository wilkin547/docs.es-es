---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 8bc720238ca3039106345783381cd26134fc46b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213082"
---
# <a name="scopes"></a>\<scopes>
Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.  
  
\<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors>  
\<comportamiento >  
\<endpointDiscovery>  
\<scopes>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|Agrega la información sobre el ámbito del extremo que se puede usar en los criterios de coincidencia para buscar los servicios.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<endpointDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|Especifica las distintas configuraciones de detección para un punto de conexión, como su detectabilidad, ámbitos y cualquier extensión personalizada a sus metadatos.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
