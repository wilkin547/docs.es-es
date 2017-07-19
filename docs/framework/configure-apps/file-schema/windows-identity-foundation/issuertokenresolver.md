---
title: "&lt;issuerTokenResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;issuerTokenResolver&gt;
Registra a la resolución de símbolo \(token\) de emisor que utiliza controladores en la colección de controladores de símbolo \(token\).  Se utiliza la resolución de símbolo \(token\) de emisor para resolver el token de firma de tokens y los mensajes entrantes.  
  
## Sintaxis  
  
```  
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
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|type|En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  Atributo  Descripción  Obligatorio.|  
  
### Elementos secundarios  
 None  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|type|  
  
## Comentarios  
 Se utiliza la resolución de símbolo \(token\) de emisor para resolver el token de firma de tokens y los mensajes entrantes.  Se utiliza para recuperar el material criptográfico que se utiliza para comprobar la firma.  Debe especificar el `type` atributo.  Obligatorio.  
  
 None  Elemento  
  
> [!NOTE]
>  Descripción  Configuración de la `<securityTokenHandlerConfiguration>` elemento anulan a aquellos en los `<identityConfiguration>` elemento.  
  
## Ejemplo  
 El XML siguiente muestra la configuración para una resolución de símbolo \(token\) de emisor que se basa en una clase personalizada que se deriva de <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.  La resolución de símbolo \(token\) mantiene un diccionario de pares de clave de la audiencia que se inicializa desde un elemento de configuración personalizado \(`<AddAudienceKeyPair>`\) definidos para la clase.  La clase reemplaza el <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> método para procesar este elemento.  El reemplazo se muestra en el siguiente ejemplo; Sin embargo, los métodos que llama no se muestran para mayor brevedad.  Para obtener un ejemplo completo, consulte el `CustomToken` ejemplo.  
  
```  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## Ejemplo  
  
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
  
## Vea también  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>