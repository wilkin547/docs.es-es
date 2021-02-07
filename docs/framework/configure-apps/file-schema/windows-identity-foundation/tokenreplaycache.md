---
description: 'Más información acerca de: <tokenReplayCache>'
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 793b1f88a9eeb0ebce4cd440e248e81377f17e9b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749004"
---
# \<tokenReplayCache>

Registra una memoria caché de reproducción de tokens con un servicio o una colección de controladores de tokens de seguridad.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**  
  
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
|type|Tipo que se deriva de la <xref:System.IdentityModel.Tokens.TokenReplayCache> clase. Para obtener más información sobre cómo especificar un personalizado `type` , vea [referencias de tipo personalizado].
  
### <a name="child-elements"></a>Elementos secundarios  

 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<caches>](caches.md)|Registra las memorias caché utilizadas por un servicio o una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Observaciones  

 La memoria caché de reproducción de tokens se usa para detectar tokens reproducidos. La detección de la reproducción de tokens está habilitada por el [\<tokenReplayDetection>](tokenreplaydetection.md) elemento, que también especifica el tiempo de expiración máximo para los tokens.  
  
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
