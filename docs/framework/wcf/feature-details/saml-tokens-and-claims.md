---
title: "Tokens y notificaciones SAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "federación"
  - "tokens emitidos"
  - "Token SAML"
  - "WCF, federación"
ms.assetid: 930b6e34-9eab-4e95-826c-4e06659bb977
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Tokens y notificaciones SAML
*Los tokens* de Security Assertions Markup Language\(SAML\) son representaciones XML de notificaciones.De forma predeterminada, los tokens SAML [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] utilizados en escenarios de seguridad asociados son *tokens emitidos*.  
  
 Los tokens SAML llevan instrucciones que son conjuntos de notificaciones realizadas por una entidad sobre otra entidad.Por ejemplo, en escenarios de seguridad asociados, las instrucciones son realizadas por un servicio de token de seguridad sobre un usuario del sistema.El servicio de token de seguridad firma el token SAML para indicar la veracidad de las instrucciones contenidas en el token.Además, el token SAML está asociado a material clave criptográfico del que el usuario del token SAML demuestra tener conocimiento.Esta prueba convence al usuario de confianza que el token SAML fue realmente emitido para ese usuario.Por ejemplo, en un escenario típico:  
  
1.  Un cliente solicita un token de SAML de un servicio de token de seguridad, autenticándose para ese servicio de token de seguridad usando las credenciales de Windows.  
  
2.  El servicio de token de seguridad emite un token SAML para el cliente.El token SAML se firma con un certificado asociado al servicio de token de seguridad y contiene una clave de prueba cifrada para el servicio de destino.  
  
3.  El cliente también recibe una copia de la *clave de prueba*.El cliente presenta a continuación el token SAML al servicio de aplicación \(el *usuario de confianza*\) y firma el mensaje con esa clave de prueba.  
  
4.  La firma a través del token SAML indica al usuario de confianza que el servicio de token de seguridad emitió el token.La firma del mensaje creada con la clave de prueba indica al usuario de confianza que el token fue emitido para el cliente.  
  
## De notificaciones a SamlAttributes  
 En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las instrucciones en tokens SAML se modelan como objetos <xref:System.IdentityModel.Tokens.SamlAttribute>, que se pueden rellenar directamente a partir de los objetos <xref:System.IdentityModel.Claims.Claim>, siempre que el objeto <xref:System.IdentityModel.Claims.Claim> tenga una propiedad <xref:System.IdentityModel.Claims.Claim.Right%2A> de <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y la propiedad <xref:System.IdentityModel.Claims.Claim.Resource%2A> sea del tipo <xref:System.String>.Por ejemplo:  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
>  Cuando los tokens SAML se serializan en mensajes, o cuando los emite un servicio de token de seguridad o son presentados por los clientes a servicios como parte de autenticación, la cuota de tamaño máximo del mensaje debe ser suficientemente grande para alojar el token SAML y las otras partes del mensaje.En casos normales, las cuotas de tamaño del mensaje predeterminadas son suficientes.Sin embargo, en casos donde un token SAML es grande que porque contiene centenares de notificaciones, puede necesitar aumentar las cuotas para alojar el token serializado.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Consideraciones de seguridad para datos](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).  
  
## De SamlAttributes a notificaciones  
 Cuando los tokens SAML se reciben en mensajes, las diversas instrucciones en el token SAML se convierten en objetos <xref:System.IdentityModel.Policy.IAuthorizationPolicy> que se colocan en <xref:System.IdentityModel.Policy.AuthorizationContext>.La propiedad <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> de <xref:System.IdentityModel.Policy.AuthorizationContext> devuelve las notificaciones de cada instrucción SAML y se pueden examinar para determinar si autenticar y autorizar al usuario.  
  
## Vea también  
 <xref:System.IdentityModel.Policy.AuthorizationContext>   
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>   
 <xref:System.IdentityModel.Claims.ClaimSet>   
 [Federación](../../../../docs/framework/wcf/feature-details/federation.md)   
 [Cómo crear un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [Cómo: Configurar las credenciales en un servicio de federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)   
 [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)   
 [Notificaciones y tokens](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)   
 [Creación de notificaciones y valores de recursos](../../../../docs/framework/wcf/feature-details/claim-creation-and-resource-values.md)   
 [Cómo crear una notificación personalizada](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)