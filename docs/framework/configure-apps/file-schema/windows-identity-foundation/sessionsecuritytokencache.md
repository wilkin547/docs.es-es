---
title: '&lt;sessionSecurityTokenCache&gt;'
ms.date: 03/30/2017
ms.assetid: d43e676c-0153-485c-ab31-0257a2db7507
author: BrucePerlerMS
ms.openlocfilehash: b812673ac1c015adde357d3c0707d85643aad3e9
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47401383"
---
# <a name="ltsessionsecuritytokencachegt"></a>&lt;sessionSecurityTokenCache&gt;
Registra una memoria caché de tokens de sesión con un servicio o una colección de controladores de token de seguridad.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<las memorias caché >  
\<sessionSecurityTokenCache >  
  
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
|type|Un tipo que deriva la <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> clase.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<las memorias caché >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra las memorias caché utilizadas por un servicio o una colección de controladores de token de seguridad.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra la configuración de una caché personalizada para almacenar los tokens de seguridad de sesión (<xref:System.IdentityModel.Tokens.SessionSecurityToken>). La configuración se toma de la `ClaimsAwareWebFarm` ejemplo. Para obtener más información acerca de este ejemplo, vea [índice de ejemplo de código WIF](../../../../../docs/framework/security/wif-code-sample-index.md).  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
