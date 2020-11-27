---
title: Procedimiento para crear un comprobador de identidad de cliente personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f2d34e43-fa8b-46d2-91cf-d2960e13e16b
ms.openlocfilehash: 84982aca06bacb5718855602872fe4dab2376a9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256071"
---
# <a name="how-to-create-a-custom-client-identity-verifier"></a>Procedimiento para crear un comprobador de identidad de cliente personalizado

La característica de *identidad* de Windows Communication Foundation (WCF) permite a un cliente especificar de antemano la identidad esperada del servicio. Siempre que un servidor se autentica al cliente, se comprueba la identidad frente a la identidad prevista. (Para obtener una explicación de la identidad y cómo funciona, consulte [identidad de servicio y autenticación](../feature-details/service-identity-and-authentication.md)).  
  
 En caso necesario, la comprobación puede personalizarse mediante un comprobador de identidad personalizado. Por ejemplo, puede realizar controles adicionales de comprobación de identidad del servicio. En este ejemplo, el comprobador de identidad personalizado controla las notificaciones adicionales del certificado X.509 devueltas desde el servidor. Para obtener una aplicación de ejemplo, consulte [ejemplo de identidad de servicio](../samples/service-identity-sample.md).  
  
### <a name="to-extend-the-endpointidentity-class"></a>Para extender la clase EndpointIdentity  
  
1. Defina una nueva clase derivada de la clase <xref:System.ServiceModel.EndpointIdentity>. Este ejemplo asigna nombre a la `OrgEndpointIdentity` de la extensión  
  
2. Agregue los miembros privados y las propiedades que utilizará la clase <xref:System.ServiceModel.Security.IdentityVerifier> extendida para realizar la comprobación de identidad frente a las notificaciones del token de seguridad devueltas por el servicio. Este ejemplo define una propiedad: `OrganizationClaim`.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
     [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
### <a name="to-extend-the-identityverifier-class"></a>Para extender la clase IdentityVerifier  
  
1. Defina una nueva clase derivada de <xref:System.ServiceModel.Security.IdentityVerifier>. Este ejemplo asigna nombre a la `CustomIdentityVerifier` de la extensión  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#7)]
     [!code-vb[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#7)]  
  
2. Invalide el método <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A>. El método determina si la comprobación de la identidad tuvo éxito o fue fallida.  
  
3. El método `CheckAccess` posee dos parámetros. El primero es una instancia de la clase <xref:System.ServiceModel.EndpointIdentity>. El segundo es una instancia de la clase <xref:System.IdentityModel.Policy.AuthorizationContext>.  
  
     En la implementación del método, examine la colección de notificaciones devuelta por la propiedad <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> de la clase <xref:System.IdentityModel.Policy.AuthorizationContext>, y realice las comprobaciones de autenticación necesarias. Este ejemplo comienza buscando cualquier notificación de tipo "Nombre distintivo" y, a continuación, compara el nombre con la extensión de <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#1)]
     [!code-vb[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#1)]  
  
### <a name="to-implement-the-trygetidentity-method"></a>Para implementar el método TryGetIdentity  
  
1. Implemente el método <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A>, que determina si el cliente puede devolver una instancia de la clase <xref:System.ServiceModel.EndpointIdentity>. La infraestructura de WCF llama primero a la implementación del `TryGetIdentity` método para recuperar la identidad del servicio del mensaje. Después, la infraestructura llama a la implementación `CheckAccess` con la `EndpointIdentity` devuelta y a <xref:System.IdentityModel.Policy.AuthorizationContext>.  
  
2. En el método `TryGetIdentity`, agregue el siguiente código:  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#2)]
     [!code-vb[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#2)]  
  
### <a name="to-implement-a-custom-binding-and-set-the-custom-identityverifier"></a>Para implementar un enlace personalizado y establecer el método IdentityVerifier personalizado  
  
1. Cree un método que devuelva un objeto <xref:System.ServiceModel.Channels.Binding>. Este ejemplo comienza creando una instancia de la clase <xref:System.ServiceModel.WSHttpBinding> y estableciendo su modo de seguridad en <xref:System.ServiceModel.SecurityMode.Message>, y su <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> en <xref:System.ServiceModel.MessageCredentialType.None>.  
  
2. Cree una <xref:System.ServiceModel.Channels.BindingElementCollection> mediante el método <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.  
  
3. Recupere el <xref:System.ServiceModel.Channels.SecurityBindingElement> de la colección y conviértalo a una variable <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
4. Establezca la propiedad <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> de la clase <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> a una nueva instancia de la clase `CustomIdentityVerifier` creada anteriormente.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#3)]
     [!code-vb[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#3)]  
  
5. El enlace personalizado devuelto se utiliza para crear una instancia del cliente y la clase. El cliente puede realizar un control de comprobación de identidad personalizada del servicio, como muestra el código siguiente.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#4)]
     [!code-vb[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#4)]  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se muestra una implementación de la clase <xref:System.ServiceModel.Security.IdentityVerifier> completa.  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#5)]
 [!code-vb[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#5)]  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se muestra una implementación de la clase <xref:System.ServiceModel.EndpointIdentity> completa.  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
 [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- <xref:System.ServiceModel.EndpointIdentity>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [Ejemplo de identidad de servicio](../samples/service-identity-sample.md)
- [Directiva de autorización](../samples/authorization-policy.md)
