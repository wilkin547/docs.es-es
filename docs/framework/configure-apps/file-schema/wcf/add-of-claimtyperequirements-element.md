---
title: "&lt;add&gt; de &lt;claimTypeRequirements&gt; (elemento) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;add&gt; de &lt;claimTypeRequirements&gt; (elemento)
Especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.  Por ejemplo, los servicios indican los requisitos en las credenciales de entrada, que deben poseer un cierto conjunto de tipos de notificaciones.  
  
## Sintaxis  
  
```  
  
<claimTypeRequirements>  
      <add claimType="URI"  
        isOptional="Boolean" />  
</claimTypeRequirements>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|claimType|URI que define el tipo de una notificación.  Por ejemplo, para comprar un producto de un sitio web, el usuario debe presentar una tarjeta de crédito válida con límite de crédito suficiente.  El tipo de notificación sería el URI de la tarjeta de crédito.|  
|isOptional|Valor de tipo booleano que especifica si se trata de una notificación opcional.  Establezca este atributo en `false` si se trata de una notificación necesaria.<br /><br /> Puede usar este atributo cuando el servicio pregunte para obtener alguna información, pero no lo requiere.  Por ejemplo, si le exige al usuario que escriba su nombre, apellido y dirección, pero decide que el número de teléfono es opcional.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<claimTypeRequirements\>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|Especifica una colección de tipos de notificación requeridos.  Cada elemento es del tipo <xref:System.ServiceModel.Configuration.ClaimTypeElement>.<br /><br /> En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.  Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.  Cada elemento de la colección especifica los tipos de notificaciones necesarias y opcionales que se espera que aparezcan en una credencial aliada.|  
  
## Comentarios  
 En un escenario aliado, los servicios indican los requisitos de las credenciales de entrada.  Por ejemplo, las credenciales de entrada deben poseer un determinado conjunto de tipos de notificación.  Este requisito se manifiesta en una directiva de seguridad.  Cuando un cliente solicita las credenciales de un servicio aliado \(por ejemplo, CardSpace\), coloca los requisitos en una solicitud del token \(RequestSecurityToken\) para que el servicio aliado pueda emitir las credenciales que satisfacen según los requisitos.  
  
## Ejemplo  
 La siguiente configuración agrega dos requisitos de tipo de notificación a un enlace de seguridad.  
  
```  
<bindings>  
    <wsFederationHttpBinding>  
      <binding name="myFederatedBinding">  
        <security mode="Message">  
          <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">  
            <claimTypeRequirements>  
              <add claimType=  
"http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress"/>  
              <add claimType=  
"http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"    
optional="true" />  
            </claims>  
          </message>  
        </security>  
      </binding>  
    </wsFederationHttpBinding>  
</bindings>  
```  
  
## Vea también  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>   
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>   
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>   
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>   
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>