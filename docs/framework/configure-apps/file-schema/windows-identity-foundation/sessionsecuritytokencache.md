---
title: <sessionSecurityTokenCache>
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: 347d1a1cba95bbd4992de95d6617e8828f4fc374
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156906"
---
# \<sessionSecurityTokenCache>

Registra una memoria caché para los tokens de sesión con un servicio o una colección de controladores de tokens de seguridad.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionSecurityTokenCache>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <sessionSecurityTokenCache type=xs:string>  
      </sessionSecurityTokenCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|type|Tipo que se deriva de la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<caches>](caches.md)|Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.|  
  
## <a name="example"></a>Ejemplo  

 El siguiente XML muestra la configuración de una caché personalizada para contener los tokens de seguridad de la sesión ( <xref:System.IdentityModel.Tokens.SessionSecurityToken> ). La configuración se toma del `ClaimsAwareWebFarm` ejemplo. Para obtener más información sobre este ejemplo, consulte [Índice de ejemplo de código WIF](/previous-versions/dotnet/framework/security/wif-code-sample-index).  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
