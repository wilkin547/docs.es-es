---
title: '&lt;tiempos de espera&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 1f0638f85177d2acb6f61e3246a1a5ee9a4e2f5c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753006"
---
# <a name="lttimeoutsgt"></a>&lt;tiempos de espera&gt;
Representa un elemento de configuración que especifica el intervalo de tiempo permitido para que el host del servicio abra o cierre.  
  
 \<system.ServiceModel>  
\<cliente >  
\<punto de conexión >  
\<host >  
\<los tiempos de espera >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`closeTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se cierre.|  
|`openTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo permitido para que el host del servicio se abra.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<host >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Un elemento de configuración que especifica valores para un host de servicio.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [Hospedar aplicaciones de WPF](../../../../../docs/framework/wcf/feature-details/hosting.md)
