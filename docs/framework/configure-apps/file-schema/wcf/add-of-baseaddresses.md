---
title: '&lt;add&gt; de &lt;baseAddresses&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 516c615248c95ef3107664b996f457fb80b46373
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a>&lt;add&gt; de &lt;baseAddresses&gt;
Representa un elemento de configuración que especifica las direcciones base usadas por el host de servicio.  
  
 \<sistema. ServiceModel >  
\<cliente >  
\<punto de conexión >  
\<host >  
\<baseAddresses >  
\<baseAddress >  
  
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
|[\<baseAddresses >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Una colección de elementos de `baseAddress`.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [Hospedar aplicaciones de WPF](../../../../../docs/framework/wcf/feature-details/hosting.md)
