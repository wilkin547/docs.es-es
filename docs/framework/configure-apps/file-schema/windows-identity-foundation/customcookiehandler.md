---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b974767aa86801bff234e200e1fce021bfc422c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
Establece el tipo de controlador de cookie personalizado. Este elemento sólo puede estar presente si el `mode` atributo de la `<cookieHandler>` elemento es "Custom". El tipo personalizado debe derivarse de la <xref:System.IdentityModel.Services.CookieHandler> clase.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
\<customCookieHandler >  
  
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
|type|Especifica un tipo personalizado que deriva de la <xref:System.IdentityModel.Services.CookieHandler> clase. Para obtener más información sobre cómo especificar el `type` de atributo, vea [las referencias de tipos personalizado](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Configura el <xref:System.IdentityModel.Services.CookieHandler> que la <xref:System.IdentityModel.Services.SessionAuthenticationModule> utiliza para leer y escribir las cookies.|  
  
## <a name="remarks"></a>Comentarios  
 Al especificar un controlador de cookies personalizado estableciendo la `mode` atributo de la `<cookieHandler>` elemento a "Custom", debe especificar el tipo del controlador de cookie personalizado mediante la inclusión de un `<customCookieHandler>` elemento secundario que hace referencia al tipo de controlador de cookie. Este elemento no puede ser especificado cuando el `mode` atributo está establecido en "Chunked" o "Default". Controladores de cookie personalizado deben derivarse de la <xref:System.IdentityModel.Services.CookieHandler> clase.  
  
 El `<customCookieHandler>` elemento representado por la <xref:System.IdentityModel.Configuration.CustomTypeElement> clase.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se configura el SAM para usar un controlador de cookies personalizados del tipo `MyNamespace.MyCustomCookieHandler`.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Services.CookieHandler>
