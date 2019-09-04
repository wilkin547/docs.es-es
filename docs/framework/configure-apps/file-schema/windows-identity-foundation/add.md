---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 932e8452542ace66824fba1262694c220ce88676
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252186"
---
# <a name="add"></a>\<add>
Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> identityConfiguration**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> securityTokenHandlers**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|type|Nombre del tipo de CLR del controlador de token que se va a agregar. Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|Proporciona la configuración para <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> la clase, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> la clase o una clase derivada de cualquiera de estas clases.|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|Proporciona la configuración para <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> la clase o las clases derivadas.|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|Proporciona la configuración para <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> la clase o las clases derivadas.|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|Proporciona una configuración opcional para <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> la clase o las clases derivadas.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.|  
  
## <a name="remarks"></a>Comentarios  
 El `<add>` elemento puede tomar un único elemento secundario que especifica la configuración del controlador de token. Esto depende de si la clase `type` `<add>` de controlador a la que se hace referencia mediante el atributo del elemento proporciona compatibilidad para esta característica. Las clases de controlador de token que proporcionan esta característica deben exponer un constructor <xref:System.Xml.XmlElement> que toma un objeto.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Algunas de las clases de controlador de tokens de seguridad integradas proporcionan esta funcionalidad. Estas clases son <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>,, ,<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>y .<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>  
  
> [!IMPORTANT]
> La colección de controladores de token solo puede contener un único controlador de cualquier tipo dado. Esto significa, por ejemplo, que si desea agregar un controlador que se deriva de la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase a la colección, primero debe <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>quitar, que está presente de forma predeterminada, de la colección. Puede usar el [ \<elemento Remove >](remove.md) para quitar un único controlador de la colección o utilizar el [ \<elemento Clear >](clear.md) para quitar todos los controladores de la colección.  
  
 La configuración especificada en un controlador invalida los valores equivalentes especificados en la colección de controladores de tokens en el [ \<elemento > securityTokenHandlerConfiguration](securitytokenhandlerconfiguration.md) y los especificados en el nivel de servicio en el [ \< elemento > identityConfiguration](identityconfiguration.md) .  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra el uso de los `<add>` elementos `<remove>` y para reemplazar el controlador de token de sesión predeterminado por un controlador de token de sesión personalizado. El XML se toma `ClaimsAwareWebFarm` del ejemplo.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
