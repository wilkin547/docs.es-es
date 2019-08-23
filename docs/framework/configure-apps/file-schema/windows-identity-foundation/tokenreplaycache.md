---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944074"
---
# <a name="tokenreplaycache"></a>\<tokenReplayCache>
Registra una memoria caché de reproducción de tokens con un servicio o una colección de controladores de tokens de seguridad.  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|type|Tipo que se deriva de la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase. Para obtener más información sobre cómo especificar un personalizado `type`, vea [referencias de tipo personalizado].
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<caches>](caches.md)|Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Comentarios  
 La memoria caché de reproducción de tokens se usa para detectar tokens reproducidos. La detección de la reproducción de tokens [ \<](tokenreplaydetection.md) está habilitada por el elemento > de tokenReplayDetection, que también especifica el tiempo de expiración máximo para los tokens.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra la configuración de una memoria caché personalizada para detectar tokens reproducidos.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [\<tokenReplayDetection>](tokenreplaydetection.md)
