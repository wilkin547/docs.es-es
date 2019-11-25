---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 451750a1facd9a886b53427a8d54580d1a939fa5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968507"
---
# <a name="issuertokenresolver"></a>\<issuerTokenResolver >
Registra el solucionador de tokens de emisor que usan los controladores en la colección de controladores de tokens. La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers**](securitytokenhandlers.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration**](securitytokenhandlerconfiguration.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerTokenResolver >**  
  
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
|tipo|Especifica el tipo de solucionador de tokens del emisor. Debe ser la clase <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo que se derive de la clase <xref:System.IdentityModel.Tokens.IssuerTokenResolver>. Requerido.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](securitytokenhandlerconfiguration.md)|Proporciona la configuración para una colección de controladores de tokens de seguridad.|  
  
## <a name="remarks"></a>Comentarios  
 La resolución de tokens del emisor se usa para resolver el token de firma en los tokens y mensajes entrantes. Se utiliza para recuperar el material criptográfico que se usa para comprobar la firma. Debe especificar el atributo `type`. El tipo especificado puede ser <xref:System.IdentityModel.Tokens.IssuerTokenResolver> o un tipo personalizado que deriva de la clase <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.  
  
 Algunos controladores de token permiten especificar la configuración de la resolución de tokens del emisor en la configuración. La configuración de los controladores de token individuales invalida los especificados en la colección de controladores de tokens de seguridad.  
  
> [!NOTE]
> La especificación del elemento `<issuerTokenResolver>` como un elemento secundario del elemento de [\<identityConfiguration](identityconfiguration.md) está en desuso, pero todavía se admite por compatibilidad con versiones anteriores. Los valores del elemento `<securityTokenHandlerConfiguration>` reemplazan a los del elemento `<identityConfiguration>`.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra la configuración de un solucionador de tokens de emisor que se basa en una clase personalizada que deriva de <xref:System.IdentityModel.Tokens.IssuerTokenResolver>. La resolución de tokens mantiene un diccionario de pares de clave de audiencia que se inicializa a partir de un elemento de configuración personalizado (`<AddAudienceKeyPair>`) definido para la clase. La clase invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> para procesar este elemento. La invalidación se muestra en el ejemplo siguiente: sin embargo, los métodos a los que llama no se muestran por motivos de brevedad. Para obtener el ejemplo completo, vea el ejemplo `CustomToken`.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
