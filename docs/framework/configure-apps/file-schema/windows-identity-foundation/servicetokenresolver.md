---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152585"
---
# <a name="servicetokenresolver"></a>\<serviceTokenResolver>
Registra el solucionador de tokens de servicio que usan los controladores de la colección de controladores de tokens. El solucionador de tokens de servicio se usa para resolver el token de cifrado en los tokens y mensajes entrantes.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|type|Especifica el tipo del solucionador de tokens de servicio. El <xref:System.IdentityModel.Selectors.SecurityTokenResolver> tipo o un tipo que <xref:System.IdentityModel.Selectors.SecurityTokenResolver> deriva de la clase. Para obtener más información `type` acerca de cómo especificar el atributo, vea [Referencias de tipo personalizado]. Necesario.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Proporciona configuración para una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Observaciones  
 El solucionador de tokens de servicio se puede usar para resolver el token de cifrado en los tokens y mensajes entrantes. Se utiliza para recuperar la clave que se debe usar para descifrar los tokens entrantes. Debe especificar `type` el atributo. El tipo especificado puede <xref:System.IdentityModel.Selectors.SecurityTokenResolver> ser un tipo personalizado <xref:System.IdentityModel.Selectors.SecurityTokenResolver> o uno que deriva de la clase.  
  
 Algunos controladores de tokens le permiten especificar la configuración del solucionador de tokens de servicio en la configuración. La configuración de los controladores de tokens individuales invalida los especificados en la colección de controladores de tokens de seguridad.  
  
> [!NOTE]
> Especificar el `<serviceTokenResolver>` elemento como un elemento secundario del elemento [ \<de>identityConfiguration](identityconfiguration.md) ha quedado en desuso, pero sigue siendo compatible con la compatibilidad con versiones anteriores. La configuración `<securityTokenHandlerConfiguration>` del elemento `<identityConfiguration>` los reemplaza en el elemento.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
