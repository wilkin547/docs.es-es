---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152676"
---
# <a name="issuertokenresolver"></a>\<issuerTokenResolver>
Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens. El solucionador de tokens de emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
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
|type|Especifica el tipo del solucionador de tokens de emisor. Debe ser <xref:System.IdentityModel.Tokens.IssuerTokenResolver> la clase o un tipo <xref:System.IdentityModel.Tokens.IssuerTokenResolver> que deriva de la clase. Necesario.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Proporciona configuración para una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Observaciones  
 El solucionador de tokens de emisor se usa para resolver el token de firma en los tokens y mensajes entrantes. Se utiliza para recuperar el material criptográfico que se utiliza para comprobar la firma. Debe especificar `type` el atributo. El tipo especificado puede <xref:System.IdentityModel.Tokens.IssuerTokenResolver> ser un tipo personalizado <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o uno que deriva de la clase.  
  
 Algunos controladores de tokens le permiten especificar la configuración del solucionador de tokens de emisor en la configuración. La configuración de los controladores de tokens individuales invalida los especificados en la colección de controladores de tokens de seguridad.  
  
> [!NOTE]
> Especificar el `<issuerTokenResolver>` elemento como un elemento secundario del elemento [ \<de>identityConfiguration](identityconfiguration.md) ha quedado en desuso, pero sigue siendo compatible con la compatibilidad con versiones anteriores. La configuración `<securityTokenHandlerConfiguration>` del elemento `<identityConfiguration>` los reemplaza en el elemento.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra la configuración de un solucionador de <xref:System.IdentityModel.Tokens.IssuerTokenResolver>tokens de emisor que se basa en una clase personalizada que deriva de . El solucionador de tokens mantiene un diccionario de pares de clave`<AddAudienceKeyPair>`de audiencia que se inicializa a partir de un elemento de configuración personalizado ( ) definido para la clase. La clase reemplaza <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> el método para procesar este elemento. La invalidación se muestra en el ejemplo siguiente; sin embargo, los métodos a los que llama no se muestran por brevedad. Para ver el ejemplo `CustomToken` completo, consulte el ejemplo.  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>Ejemplo
  
```csharp
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
