---
title: 'Cómo: Configurar un emisor local'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 15263371-514e-4ea6-90fb-14b4939154cd
ms.openlocfilehash: 2b227398af3ea0dfd7cd866f1110ccc1737553c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495098"
---
# <a name="how-to-configure-a-local-issuer"></a>Cómo: Configurar un emisor local
En este tema se describe cómo configurar un cliente para utilizar un emisor local para los tokens emitidos.  
  
 A menudo, cuando un cliente se comunica con un servicio federado, el servicio especifica la dirección del servicio de token de seguridad que se espera que emita el token y que el cliente utilizará para autenticarse con el servicio federado. En determinadas situaciones, el cliente puede configurarse para utilizar un *emisor local*.  
  
 Windows Communication Foundation (WCF) utiliza un emisor local en casos donde es la dirección del emisor de un enlace federado http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous o `null`. En casos como éste, debe configurar <xref:System.ServiceModel.Description.ClientCredentials> con la dirección del emisor local y el enlace que se va a utilizar para comunicarse con ese emisor.  
  
> [!NOTE]
>  Si el <xref:System.ServiceModel.Description.ClientCredentials.SupportInteractive%2A> propiedad de la `ClientCredentials` clase se establece en `true`, no se especifica una dirección de emisor local y la dirección del emisor especificado por el [ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) u otros enlace federado es http://schemas.xmlsoap.org/ws/2005/05/identity/issuer/self, http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous, o es `null`, a continuación, las ventanas [!INCLUDE[infocard](../../../../includes/infocard-md.md)] emisor se utiliza.  
  
### <a name="to-configure-the-local-issuer-in-code"></a>Para configurar el emisor local en código  
  
1.  Cree una variable de tipo <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
2.  Establezca la variable en la instancia devuelta de la propiedad <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A> de la clase `ClientCredentials`. Esa instancia es devuelta por la propiedad <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> del cliente (heredada de <xref:System.ServiceModel.ClientBase%601>) o la propiedad <xref:System.ServiceModel.ChannelFactory.Credentials%2A> de <xref:System.ServiceModel.ChannelFactory>:  
  
     [!code-csharp[c_CreateSTS#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#9)]
     [!code-vb[c_CreateSTS#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#9)]  
  
3.  Establezca la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerAddress%2A> en una nueva instancia de <xref:System.ServiceModel.EndpointAddress>, con la dirección del emisor local como un argumento para el constructor.  
  
     [!code-csharp[c_CreateSTS#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#10)]
     [!code-vb[c_CreateSTS#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#10)]  
  
     De manera alternativa, cree una nueva instancia <xref:System.Uri> como un argumento para el constructor.  
  
     [!code-csharp[c_CreateSTS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#11)]
     [!code-vb[c_CreateSTS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#11)]  
  
     El `addressHeaders` parámetro es una matriz de <xref:System.ServiceModel.Channels.AddressHeader> instancias, tal como se muestra.  
  
     [!code-csharp[c_CreateSTS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#12)]
     [!code-vb[c_CreateSTS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#12)]  
  
4.  Establezca el enlace para el emisor local utilizando la <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerBinding%2A> propiedad.  
  
     [!code-csharp[c_CreateSTS#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#13)]
     [!code-vb[c_CreateSTS#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#13)]  
  
5.  Opcional. Agregue los comportamientos del extremo configurados para el emisor local agregando tales comportamientos a la colección devuelta por la propiedad <xref:System.ServiceModel.Security.IssuedTokenClientCredential.LocalIssuerChannelBehaviors%2A>.  
  
     [!code-csharp[c_CreateSTS#14](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#14)]
     [!code-vb[c_CreateSTS#14](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#14)]  
  
### <a name="to-configure-the-local-issuer-in-configuration"></a>Para configurar el emisor local en la configuración  
  
1.  Crear un [ \<localIssuer >](../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md) elemento como elemento secundario de la [ \<issuedToken >](../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md) elemento que es un elemento secundario de la [ \<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento en un comportamiento del extremo.  
  
2.  Establezca el atributo `address` en la dirección del emisor local que aceptará las solicitudes del token.  
  
3.  Establezca los atributos `binding` y `bindingConfiguration` en valores que hacen referencia al enlace adecuado que se debe usar cuando se comunica con el extremo del emisor local.  
  
4.  Opcional. Establecer el [ \<identidad >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) elemento como elemento secundario de la <`localIssuer`> elemento y especifique la información de identidad para el emisor local.  
  
5.  Opcional. Establecer el [ \<encabezados >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) elemento como elemento secundario de la <`localIssuer`> elemento y especifique los encabezados adicionales que son necesarios para poder direccionar el emisor local correctamente.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Tenga en cuenta que si se especifica una dirección y un enlace del emisor para un enlace determinado, el emisor local no se utiliza para los puntos de conexión que utilizan ese enlace. Los clientes que siempre esperan utilizar el emisor local deberían asegurarse de que no utilizan este enlace o que modifican el enlace de manera que la dirección del emisor sea `null`.  
  
## <a name="see-also"></a>Vea también  
 [Configuración de las credenciales en un servicio de federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [Creación de un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Creación de un WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
