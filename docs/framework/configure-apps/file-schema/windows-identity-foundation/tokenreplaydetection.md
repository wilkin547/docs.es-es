---
title: '&lt;tokenReplayDetection&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: f95d200f74621a40d2987acf68bc554df8d17ab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="lttokenreplaydetectiongt"></a>&lt;tokenReplayDetection&gt;
Habilita la detección de reproducción de tokens y especifica la hora de expiración de símbolos (tokens).  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<tokenReplayDetection >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>Tipo  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|enabled|Un valor que especifica si está habilitada la detección de reproducción de tokens; "true" para habilitar el token de la detección de reproducción.|  
|expirationPeriod|Un <xref:System.TimeSpan> que especifica la cantidad máxima de tiempo antes de que un elemento se considera caducado y eliminado de la memoria caché.  Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, consulte [valores de intervalo de tiempo](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica los valores de identidad de nivel de servicio.|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de seguridad controladores de tokens.|  
  
## <a name="remarks"></a>Comentarios  
 A `<tokenReplayDetection>` elemento puede especificarse en el nivel de servicio en la `<identityConfiguration>` elemento o en el nivel de colección de controlador de token de seguridad en el `<securityTokenHandlerConfiguration>` elemento. La configuración en una colección de controlador de token invalida las especificadas en el servicio.  
  
 El tipo de la memoria caché de la respuesta de token es especificado por el [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) elemento.
