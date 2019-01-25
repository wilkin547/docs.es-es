---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 1e89afc5764dbdb86e87d2307425299dff57c686
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525176"
---
# <a name="lttokenreplaycachegt"></a>&lt;tokenReplayCache&gt;
Registra una caché de reproducción de tokens con un servicio o una colección de controladores de token de seguridad.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<caches>  
\<tokenReplayCache>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|type|Un tipo que deriva la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase. Para obtener más información acerca de cómo especificar un personalizado `type`, consulte la sección [referencias de tipo personalizado].
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<caches>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra las memorias caché utilizadas por un servicio o una colección de controladores de token de seguridad.|  
  
## <a name="remarks"></a>Comentarios  
 La caché de reproducción de tokens se usa para detectar tokens reproducidos. Detección de reproducción de tokens está habilitada por la [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) elemento, que también especifica la hora de expiración máximo para los tokens.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra la configuración de una caché personalizada para detectar tokens reproducidos.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>Vea también
- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
