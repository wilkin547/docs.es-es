---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 7c2b6bdc62da63905d7ff33a9984808e7b7d114f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544545"
---
# \<add>
Agrega el controlador de tokens de seguridad especificado a la colección de controladores de tokens.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
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
  
|Atributo|Descripción|  
|---------------|-----------------|  
|type|Nombre del tipo de CLR del controlador de token que se va a agregar. Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> clase, la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase o una clase derivada de cualquiera de estas clases.|  
|[\<sessionTokenRequirement>](sessiontokenrequirement.md)|Proporciona la configuración para la <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> clase o las clases derivadas.|  
|[\<userNameSecurityTokenHandlerRequirement>](usernamesecuritytokenhandlerrequirement.md)|Proporciona la configuración para la <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> clase o las clases derivadas.|  
|[\<x509SecurityTokenHandlerRequirement>](x509securitytokenhandlerrequirement.md)|Proporciona una configuración opcional para la <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> clase o las clases derivadas.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Especifica una colección de controladores de tokens de seguridad que se registran con el punto de conexión.|  
  
## <a name="remarks"></a>Comentarios  
 El `<add>` elemento puede tomar un único elemento secundario que especifica la configuración del controlador de token. Esto depende de si la clase de controlador a la que se hace referencia mediante el `type` atributo del `<add>` elemento proporciona compatibilidad para esta característica. Las clases de controlador de token que proporcionan esta característica deben exponer un constructor que toma un <xref:System.Xml.XmlElement> objeto.  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 Algunas de las clases de controlador de tokens de seguridad integradas proporcionan esta funcionalidad. Estas clases son <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> , <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> y <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> .  
  
> [!IMPORTANT]
> La colección de controladores de token solo puede contener un único controlador de cualquier tipo dado. Esto significa, por ejemplo, que si desea agregar un controlador que se deriva de la <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> clase a la colección, primero debe quitar <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , que está presente de forma predeterminada, de la colección. Puede usar el [\<remove>](remove.md) elemento para quitar un solo controlador de la colección o utilizar el [\<clear>](clear.md) elemento para quitar todos los controladores de la colección.  
  
 La configuración especificada en un controlador invalida los valores equivalentes especificados en la colección de controladores de tokens en el [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemento y los especificados en el nivel de servicio bajo el [\<identityConfiguration>](identityconfiguration.md) elemento.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra el uso de los `<add>` `<remove>` elementos y para reemplazar el controlador de token de sesión predeterminado por un controlador de token de sesión personalizado. El XML se toma del `ClaimsAwareWebFarm` ejemplo.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
