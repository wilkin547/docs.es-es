---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 3d1f7774f61060880a5c3b0327bdd6c2cc4dd74e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103004"
---
# <a name="host"></a>\<host >
Especifica los valores para un host de servicio.  
  
 \<system.ServiceModel>  
\<services>  
\<service>  
\<host >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
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
|[\<baseAddresses>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Una colección de elementos `baseAddress` que especifica las direcciones base utilizada por el host del servicio.|  
|[\<timeOuts>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|Un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<service>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Especifica la configuración para un servicio de Windows Communication Foundation (WCF).|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [Hospedaje](../../../../../docs/framework/wcf/feature-details/hosting.md)
