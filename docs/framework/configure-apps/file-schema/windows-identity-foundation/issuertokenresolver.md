---
title: '&lt;issuerTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 646833f277c3ef4675a835ca0af3daf647e01224
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758586"
---
# <a name="ltissuertokenresolvergt"></a>&lt;issuerTokenResolver&gt;
Registra a la resolución del token de emisor que se usa por los controladores de la colección de controlador de token. La resolución del token de emisor se utiliza para resolver el token de firma en mensajes y los tokens entrantes.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers>  
\<securityTokenHandlerConfiguration >  
\<issuerTokenResolver >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
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
|type|Especifica el tipo de la resolución del token de emisor. Debe ser el <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase o un tipo que deriva de la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase. Requerido.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de seguridad controladores de tokens.|  
  
## <a name="remarks"></a>Comentarios  
 La resolución del token de emisor se utiliza para resolver el token de firma en mensajes y los tokens entrantes. Se utiliza para recuperar el material criptográfico que se utiliza para comprobar la firma. Debe especificar el `type` atributo. El tipo especificado puede ser <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizado que deriva de la <xref:System.IdentityModel.Tokens.IssuerTokenResolver> clase.  
  
 Algunos controladores de tokens permiten especificar la configuración de resolución del token del emisor en la configuración. La configuración en los controladores de tokens individuales invalida los especificados en la colección de controlador de token de seguridad.  
  
> [!NOTE]
>  Especificar el `<issuerTokenResolver>` elemento como un elemento secundario de la [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento está en desuso, pero todavía se admite por compatibilidad con versiones anteriores. Configuración de la `<securityTokenHandlerConfiguration>` elemento reemplazan a las que en el `<identityConfiguration>` elemento.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra la configuración para una resolución del token de emisor que se basa en una clase personalizada que deriva de <xref:System.IdentityModel.Tokens.IssuerTokenResolver>. La resolución del token mantiene un diccionario de pares de clave de audiencia que se inicializa a partir de un elemento de configuración personalizado (`<AddAudienceKeyPair>`) definido para la clase. Las invalidaciones de clase la <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> método para procesar este elemento. La invalidación se muestra en el ejemplo siguiente; Sin embargo, no se muestran los métodos llama por razones de brevedad. Para obtener un ejemplo completo, vea el `CustomToken` ejemplo.  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>Ejemplo  
  
```  
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
