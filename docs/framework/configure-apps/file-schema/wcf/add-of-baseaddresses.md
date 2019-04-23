---
title: <add> de <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: fbcb3a07bf40c96a4cd1b2ec87277b6fefdfb89d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164481"
---
# <a name="add-of-baseaddresses"></a>\<Agregar > de \<baseAddresses >
Representa un elemento de configuración que especifica las direcciones base usadas por el host de servicio.  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
\<host >  
\<baseAddresses>  
\<baseAddress>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`baseAddress`|Cadena que especifica una dirección base usada por el host del servicio.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<baseAddresses>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Una colección de elementos de `baseAddress`.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [Hospedar aplicaciones de WPF](../../../../../docs/framework/wcf/feature-details/hosting.md)
