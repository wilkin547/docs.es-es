---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251769"
---
# \<tokenReplayDetection>
Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**  
  
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
|enabled|Valor que especifica si está habilitada la detección de reproducción de tokens; "true" para habilitar la detección de reproducción de tokens.|  
|expirationPeriod|<xref:System.TimeSpan>Que especifica la cantidad máxima de tiempo antes de que un elemento se considere expirado y se quite de la memoria caché.  Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Especifica la configuración de identidad de nivel de servicio.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Comentarios  
 Un `<tokenReplayDetection>` elemento se puede especificar en el nivel de servicio bajo el `<identityConfiguration>` elemento o en el nivel de colección de controladores de tokens de seguridad bajo el `<securityTokenHandlerConfiguration>` elemento. La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.  
  
 El elemento especifica el tipo de la memoria caché de reproducción de tokens [\<tokenReplayCache>](tokenreplaycache.md) .
