---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 2e2159a73ca79fc362a8138eea95dbd173dafb11
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944295"
---
# <a name="tokenreplaydetection"></a>\<tokenReplayDetection>
Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<tokenReplayDetection>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a>Type  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|enabled|Valor que especifica si está habilitada la detección de reproducción de tokens; "true" para habilitar la detección de reproducción de tokens.|  
|expirationPeriod|<xref:System.TimeSpan> Que especifica la cantidad máxima de tiempo antes de que un elemento se considere expirado y se quite de la memoria caché.  Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Especifica la configuración de identidad de nivel de servicio.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Comentarios  
 Un `<tokenReplayDetection>` elemento se puede especificar en el nivel de servicio bajo `<identityConfiguration>` el elemento o en el nivel de colección de controladores de `<securityTokenHandlerConfiguration>` tokens de seguridad bajo el elemento. La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.  
  
 El tipo de la memoria caché de reproducción de tokens se [ \<](tokenreplaycache.md) especifica mediante el elemento > de tokenReplayCache.
