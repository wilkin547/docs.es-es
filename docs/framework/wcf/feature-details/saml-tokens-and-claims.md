---
title: Tokens y notificaciones SAML
description: Obtenga información sobre cómo usa WFC tokens de SAML para llevar instrucciones que son conjuntos de notificaciones realizadas por una entidad sobre otra entidad.
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
ms.openlocfilehash: c054e594af69def96879852a5145675b3123614a
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244951"
---
# <a name="saml-tokens-and-claims"></a>Tokens y notificaciones SAML
Los *tokens* del lenguaje de marcado de aserciones de seguridad (SAML) son representaciones XML de notificaciones. De forma predeterminada, los tokens SAML Windows Communication Foundation (WCF) emplea en escenarios de seguridad federados son *tokens emitidos*.  
  
 Los tokens SAML llevan instrucciones que son conjuntos de notificaciones realizadas por una entidad sobre otra entidad. Por ejemplo, en escenarios de seguridad asociados, las instrucciones son realizadas por un servicio de token de seguridad sobre un usuario del sistema. El servicio de token de seguridad firma el token SAML para indicar la veracidad de las instrucciones contenidas en el token. Además, el token SAML está asociado a material clave criptográfico del que el usuario del token SAML demuestra tener conocimiento. Esta prueba convence al usuario de confianza que el token SAML fue realmente emitido para ese usuario. Por ejemplo, en un escenario típico:  
  
1. Un cliente solicita un token de SAML de un servicio de token de seguridad, autenticándose para ese servicio de token de seguridad usando las credenciales de Windows.  
  
2. El servicio de token de seguridad emite un token SAML para el cliente. El token SAML se firma con un certificado asociado al servicio de token de seguridad y contiene una clave de prueba cifrada para el servicio de destino.  
  
3. El cliente también recibe una copia de la *clave de prueba*. Después, el cliente presenta el token SAML al servicio de aplicación (el *usuario de confianza*) y firma el mensaje con esa clave de prueba.  
  
4. La firma a través del token SAML indica al usuario de confianza que el servicio de token de seguridad emitió el token. La firma del mensaje creada con la clave de prueba indica al usuario de confianza que el token fue emitido para el cliente.  
  
## <a name="from-claims-to-samlattributes"></a>De notificaciones a SamlAttributes  
 En WCF, las instrucciones de los tokens SAML se modelan como <xref:System.IdentityModel.Tokens.SamlAttribute> objetos, que se pueden rellenar directamente a partir de <xref:System.IdentityModel.Claims.Claim> objetos, siempre que el <xref:System.IdentityModel.Claims.Claim> objeto tenga una <xref:System.IdentityModel.Claims.Claim.Right%2A> propiedad de <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y la <xref:System.IdentityModel.Claims.Claim.Resource%2A> propiedad sea de tipo <xref:System.String> . Por ejemplo:  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
> Cuando los tokens SAML se serializan en mensajes, o cuando los emite un servicio de token de seguridad o son presentados por los clientes a servicios como parte de autenticación, la cuota de tamaño máximo del mensaje debe ser suficientemente grande para alojar el token SAML y las otras partes del mensaje. En casos normales, las cuotas de tamaño del mensaje predeterminadas son suficientes. Sin embargo, en casos donde un token SAML es grande que porque contiene centenares de notificaciones, puede necesitar aumentar las cuotas para alojar el token serializado. Para obtener más información, vea [consideraciones de seguridad para los datos](security-considerations-for-data.md).  
  
## <a name="from-samlattributes-to-claims"></a>De SamlAttributes a notificaciones  
 Cuando los tokens SAML se reciben en mensajes, las diversas instrucciones en el token SAML se convierten en objetos <xref:System.IdentityModel.Policy.IAuthorizationPolicy> que se colocan en <xref:System.IdentityModel.Policy.AuthorizationContext>. La propiedad <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> de <xref:System.IdentityModel.Policy.AuthorizationContext> devuelve las notificaciones de cada instrucción SAML y se pueden examinar para determinar si autenticar y autorizar al usuario.  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Policy.AuthorizationContext>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- <xref:System.IdentityModel.Claims.ClaimSet>
- [Federación](federation.md)
- [Procedimiento para crear un cliente federado](how-to-create-a-federated-client.md)
- [Procedimiento para configurar las credenciales en un servicio de federación](how-to-configure-credentials-on-a-federation-service.md)
- [Administración de notificaciones y autorización con el modelo de identidad](managing-claims-and-authorization-with-the-identity-model.md)
- [Notificaciones y tokens](claims-and-tokens.md)
- [Creación de notificaciones y valores de recursos](claim-creation-and-resource-values.md)
- [Procedimiento para crear una notificación personalizada](../extending/how-to-create-a-custom-claim.md)
