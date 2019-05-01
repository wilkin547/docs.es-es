---
title: Tokens y notificaciones SAML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
- issued tokens
- SAML token
ms.assetid: 930b6e34-9eab-4e95-826c-4e06659bb977
ms.openlocfilehash: 04517e5089f55c2d2b08a492439026d33ed9069d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991081"
---
# <a name="saml-tokens-and-claims"></a>Tokens y notificaciones SAML
Lenguaje de marcado de aserción de seguridad (SAML) *tokens* son representaciones XML de notificaciones. De forma predeterminada, los tokens SAML que Windows Communication Foundation (WCF) se usa en escenarios de seguridad federada son *tokens emitidos*.  
  
 Los tokens SAML llevan instrucciones que son conjuntos de notificaciones realizadas por una entidad sobre otra entidad. Por ejemplo, en escenarios de seguridad asociados, las instrucciones son realizadas por un servicio de token de seguridad sobre un usuario del sistema. El servicio de token de seguridad firma el token SAML para indicar la veracidad de las instrucciones contenidas en el token. Además, el token SAML está asociado a material clave criptográfico del que el usuario del token SAML demuestra tener conocimiento. Esta prueba convence al usuario de confianza que el token SAML fue realmente emitido para ese usuario. Por ejemplo, en un escenario típico:  
  
1. Un cliente solicita un token de SAML de un servicio de token de seguridad, autenticándose para ese servicio de token de seguridad usando las credenciales de Windows.  
  
2. El servicio de token de seguridad emite un token SAML para el cliente. El token SAML se firma con un certificado asociado al servicio de token de seguridad y contiene una clave de prueba cifrada para el servicio de destino.  
  
3. El cliente también recibe una copia de la *clave de prueba*. El cliente presenta el token SAML para el servicio de aplicación (el *confianza*) y firma el mensaje con esa clave de prueba.  
  
4. La firma a través del token SAML indica al usuario de confianza que el servicio de token de seguridad emitió el token. La firma del mensaje creada con la clave de prueba indica al usuario de confianza que el token fue emitido para el cliente.  
  
## <a name="from-claims-to-samlattributes"></a>De notificaciones a SamlAttributes  
 En WCF, las instrucciones en tokens SAML se modelan como <xref:System.IdentityModel.Tokens.SamlAttribute> objetos, que se pueden rellenar directamente desde <xref:System.IdentityModel.Claims.Claim> objetos, que proporciona el <xref:System.IdentityModel.Claims.Claim> objeto tiene un <xref:System.IdentityModel.Claims.Claim.Right%2A> propiedad de <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y <xref:System.IdentityModel.Claims.Claim.Resource%2A> es propiedad de tipo <xref:System.String>. Por ejemplo:  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
>  Cuando los tokens SAML se serializan en mensajes, o cuando los emite un servicio de token de seguridad o son presentados por los clientes a servicios como parte de autenticación, la cuota de tamaño máximo del mensaje debe ser suficientemente grande para alojar el token SAML y las otras partes del mensaje. En casos normales, las cuotas de tamaño del mensaje predeterminadas son suficientes. Sin embargo, en casos donde un token SAML es grande que porque contiene centenares de notificaciones, puede necesitar aumentar las cuotas para alojar el token serializado. Para obtener más información, consulte [consideraciones de seguridad para datos](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).  
  
## <a name="from-samlattributes-to-claims"></a>De SamlAttributes a notificaciones  
 Cuando los tokens SAML se reciben en mensajes, las diversas instrucciones en el token SAML se convierten en objetos <xref:System.IdentityModel.Policy.IAuthorizationPolicy> que se colocan en <xref:System.IdentityModel.Policy.AuthorizationContext>. La propiedad <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> de <xref:System.IdentityModel.Policy.AuthorizationContext> devuelve las notificaciones de cada instrucción SAML y se pueden examinar para determinar si autenticar y autorizar al usuario.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Policy.AuthorizationContext>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [Federación](../../../../docs/framework/wcf/feature-details/federation.md)
- [Cómo: Crear a un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [Cómo: Configurar las credenciales en un servicio de federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
- [Administración de notificaciones y autorización con el modelo de identidad](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
- [Notificaciones y tokens](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
- [Creación de notificaciones y valores de recursos](../../../../docs/framework/wcf/feature-details/claim-creation-and-resource-values.md)
- [Cómo: Crear una demanda personalizada](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
