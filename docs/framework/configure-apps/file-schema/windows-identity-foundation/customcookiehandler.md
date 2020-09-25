---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: a8ee23ac6facaea18cd7f1820616cb9b16afa336
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189856"
---
# \<customCookieHandler>

Establece el tipo de controlador de cookies personalizado. Este elemento solo puede estar presente si el `mode` atributo del `<cookieHandler>` elemento es "Custom". El tipo personalizado se debe derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|type|Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Services.CookieHandler> clase. Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  

 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura el <xref:System.IdentityModel.Services.CookieHandler> que <xref:System.IdentityModel.Services.SessionAuthenticationModule> utiliza para leer y escribir cookies.|  
  
## <a name="remarks"></a>Observaciones  

 Cuando se especifica un controlador de cookies personalizado estableciendo el `mode` atributo del `<cookieHandler>` elemento en "Custom", se debe especificar el tipo del controlador de cookies personalizado incluyendo un `<customCookieHandler>` elemento secundario que haga referencia al tipo de controlador de cookies. No se puede especificar este elemento cuando el `mode` atributo está establecido en "fragmentado" o "predeterminado". Los controladores de cookies personalizados deben derivar de la <xref:System.IdentityModel.Services.CookieHandler> clase.  
  
 El `<customCookieHandler>` elemento se representa mediante la <xref:System.IdentityModel.Configuration.CustomTypeElement> clase.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se configura el SAM para usar un controlador de cookies personalizado de tipo `MyNamespace.MyCustomCookieHandler` .  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.IdentityModel.Services.CookieHandler>
