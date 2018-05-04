---
title: '&lt;direcciones base&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 8de962cc70e1399dd1e9459473055651f9aca5fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltbaseaddressesgt"></a>&lt;direcciones base&gt;
Representa una colección de elementos `baseAddress`, que son las direcciones base para un host del servicio en un entorno autohospedado. Si una dirección base está presente, los puntos de conexión se pueden configurar con direcciones relativas a la dirección base.  
  
 \<system.ServiceModel>  
\<cliente >  
\<punto de conexión >  
\<host >  
\<baseAddresses >  
  
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
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [Hospedar aplicaciones de WPF](../../../../../docs/framework/wcf/feature-details/hosting.md)
