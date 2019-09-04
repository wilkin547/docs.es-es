---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: 80f435b52fd7657c5cd44538028d6080beffe0b5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252160"
---
# <a name="caches"></a>\<caches>
Registra las cachés utilizadas para los tokens de sesión y la detección de reproducción de tokens.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<almacena en caché >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 None  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<sessionSecurityTokenCache>](sessionsecuritytokencache.md)|Registra una memoria caché para los tokens de sesión con un servicio o una colección de controladores de tokens de seguridad.|  
|[\<tokenReplayCache>](tokenreplaycache.md)|Registra una memoria caché de reproducción de tokens con un servicio o una colección de controladores de tokens de seguridad.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Especifica la configuración de identidad de nivel de servicio.|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Comentarios  
 Un `<caches>` elemento se puede especificar en el nivel de servicio bajo `<identityConfiguration>` el elemento o en el nivel de colección de controladores de `<securityTokenHandlerConfiguration>` tokens de seguridad bajo el elemento. La configuración de una colección de controladores de tokens invalida las especificadas en el servicio.  
  
 El elemento se representa mediante la <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> clase. `<caches>` La <xref:System.IdentityModel.Configuration.IdentityModelCaches> clase representa las memorias caché configuradas.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra la configuración de una caché personalizada para contener los tokens de seguridad<xref:System.IdentityModel.Tokens.SessionSecurityToken>de la sesión (). La configuración se toma `ClaimsAwareWebFarm` del ejemplo.  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
