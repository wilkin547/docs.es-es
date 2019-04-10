---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 7d0afd638e9a311b69ff47b6789d5fde093945ba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212107"
---
# <a name="baseaddresses"></a>\<baseAddresses>
Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado. Si una dirección base está presente, los extremos se pueden configurar con direcciones relativas a la dirección base.  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
\<host >  
\<baseAddresses>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|Un elemento de configuración que especifica las direcciones base usadas por el host del servicio.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<host >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Un elemento de configuración que especifica valores para un host de servicio.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [Hospedaje](../../../../../docs/framework/wcf/feature-details/hosting.md)
