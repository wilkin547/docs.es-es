---
title: <add> de <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: c29e47f688118e34fbdb4deb396c930d478f0582
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187089"
---
# <a name="add-of-scopes"></a>\<Agregar > de \<ámbitos >
Agrega un Uri de ámbito personalizado que se puede utilizar para filtrar los extremos de servicio durante la consulta.  
  
\<system.ServiceModel>  
\<comportamientos >  
\<endpointBehaviors>  
\<comportamiento >  
\<endpointDiscovery>  
\<scopes>  
\<add>  
  
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
  
|Atributo|Descripción|  
|---------------|-----------------|  
|ámbito|URI que contiene información sobre el ámbito del punto de conexión que se puede usar en los criterios de coincidencia para buscar los servicios.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Contiene una colección de elementos de configuración que especifican URI del ámbito personalizado que se pueden usar para filtrar puntos de conexión de servicio durante la consulta.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
