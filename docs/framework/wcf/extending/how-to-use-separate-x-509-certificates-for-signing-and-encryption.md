---
description: 'Más información acerca de cómo: usar certificados X. 509 independientes para la firma y el cifrado'
title: Procedimiento para usar diferentes certificados X.509 para la firma y el cifrado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, extensibility
- ClientCredentials class
- ClientCredentialsSecurityTokenManager class
ms.assetid: 0b06ce4e-7835-4d82-8baf-d525c71a0e49
ms.openlocfilehash: a1cb72265d9fa2742718b88bd574efe4cc9a4918
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99644247"
---
# <a name="how-to-use-separate-x509-certificates-for-signing-and-encryption"></a>Procedimiento para usar diferentes certificados X.509 para la firma y el cifrado

En este tema se muestra cómo configurar Windows Communication Foundation (WCF) para usar certificados diferentes para la firma y el cifrado de mensajes tanto en el cliente como en el servicio.

Para permitir el uso de certificados independientes para la firma y el cifrado, se deben crear credenciales de cliente o servicio personalizadas (o ambas) porque WCF no proporciona una API para establecer varios certificados de cliente o de servicio. Además, se debe proporcionar un administrador de tokens de seguridad para sacar el máximo partido a la información de varios certificados y crear un proveedor de tokens de seguridad adecuado para el uso de claves especificado y la dirección del mensaje.

El diagrama siguiente muestra las clases principales que se utilizan, las clases de las que se heredan (identificadas mediante una flecha que señala hacia arriba) y los tipos de valor devueltos de ciertos métodos y propiedades.

- `MyClientCredentials` es una implementación personalizada de <xref:System.ServiceModel.Description.ClientCredentials>.

  - Todas sus propiedades, que se muestran en el diagrama, devuelven instancias de <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.

  - Su método <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> devuelve una instancia de `MyClientCredentialsSecurityTokenManager`.

- `MyClientCredentialsSecurityTokenManager` es una implementación personalizada de <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.

  - Su método <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> devuelve una instancia de <xref:System.IdentityModel.Selectors.X509SecurityTokenProvider>.

![Gráfico que muestra cómo se usan las credenciales del cliente](./media/e4971edd-a59f-4571-b36f-7e6b2f0d610f.gif "e4971edd-a59f-4571-b36f-7e6b2f0d610f")

Para obtener más información sobre las credenciales personalizadas, vea [Tutorial: crear credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md).

Además, debe crear un comprobador de identidad personalizado y vincularlo a un elemento de enlace de seguridad en un enlace personalizado. También debe utilizar las credenciales personalizadas en lugar de las credenciales predeterminadas.

En el diagrama siguiente, se muestran las clases implicadas en el enlace personalizado y cómo se vincula el comprobador de identidad personalizado. Hay varios elementos de enlace implicados. Todos ellos se heredan de <xref:System.ServiceModel.Channels.BindingElement>. <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> tiene la propiedad <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>, que devuelve una instancia de <xref:System.ServiceModel.Security.IdentityVerifier>, a partir de la cual se personaliza `MyIdentityVerifier`.

![Gráfico que muestra un elemento de enlace personalizado](./media/dddea4a2-0bb4-4921-9bf4-20d4d82c3da5.gif "dddea4a2-0bb4-4921-9bf4-20d4d82c3da5")

Para obtener más información acerca de cómo crear un comprobador de identidad personalizado, consulte Cómo: [crear un comprobador de identidad de cliente personalizado](how-to-create-a-custom-client-identity-verifier.md).

### <a name="to-use-separate-certificates-for-signing-and-encryption"></a>Para utilizar certificados independientes para la firma y el cifrado

1. Defina una nueva clase de credenciales de cliente que herede de la clase <xref:System.ServiceModel.Description.ClientCredentials>. Implemente cuatro nuevas propiedades para permitir la especificación de múltiples certificados: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate` y `ServiceEncryptingCertificate`. Invalide también el método <xref:System.ServiceModel.Description.ClientCredentials.CreateSecurityTokenManager%2A> para devolver una instancia de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> personalizada que se define en el paso siguiente.

     [!code-csharp[c_FourCerts#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#1)]
     [!code-vb[c_FourCerts#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#1)]

2. Defina un nuevo administrador de tokens de seguridad del cliente que herede de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>. Invalide el método <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> para crear un proveedor de tokens de seguridad adecuado. El parámetro `requirement` (un <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>) proporciona la dirección del mensaje y el uso de las claves.

     [!code-csharp[c_FourCerts#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#2)]
     [!code-vb[c_FourCerts#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#2)]

3. Defina una nueva clase de credenciales de servicio que hereda de la clase <xref:System.ServiceModel.Description.ServiceCredentials>. Implemente cuatro nuevas propiedades para permitir la especificación de múltiples certificados: `ClientSigningCertificate`, `ClientEncryptingCertificate`, `ServiceSigningCertificate` y `ServiceEncryptingCertificate`. Invalide también el método <xref:System.ServiceModel.Description.ServiceCredentials.CreateSecurityTokenManager%2A> para devolver una instancia de la clase <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> personalizada que se define en el paso siguiente.

     [!code-csharp[c_FourCerts#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#3)]
     [!code-vb[c_FourCerts#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#3)]

4. Defina un nuevo administrador de tokens de seguridad de servicio que herede de la clase <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>. Invalide el método <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager.CreateSecurityTokenProvider%2A> para crear un proveedor de tokens de seguridad adecuado dada la dirección del mensaje pasada y el uso de las claves.

     [!code-csharp[c_FourCerts#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#4)]
     [!code-vb[c_FourCerts#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#4)]

### <a name="to-use-multiple-certificates-on-the-client"></a>Para utilizar varios certificados en el cliente

1. Cree un enlace personalizado. El elemento de enlace de seguridad debe funcionar en modo dúplex para permitir que distintos proveedores de tokens de seguridad estén presentes para las solicitudes y respuestas. Una manera de hacerlo es utilizar un transporte de tipo dúplex o utilizar <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> tal y como se muestra en el código siguiente. Vincule el objeto <xref:System.ServiceModel.Security.IdentityVerifier> personalizado que se define en el paso siguiente al elemento de enlace de seguridad. Reemplace las credenciales de cliente predeterminadas con las credenciales de cliente personalizadas creadas previamente.

     [!code-csharp[c_FourCerts#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#5)]
     [!code-vb[c_FourCerts#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#5)]

2. Defina un objeto <xref:System.ServiceModel.Security.IdentityVerifier> personalizado. El servicio tiene varias identidades porque se usan certificados diferentes para cifrar la solicitud y firmar la respuesta.

    > [!NOTE]
    > En el ejemplo siguiente, el comprobador de identidad personalizado proporcionado no realiza ninguna comprobación de identidad del punto de conexión con fines de demostración. No se trata de una práctica recomendada para el código de producción.

     [!code-csharp[c_FourCerts#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#6)]
     [!code-vb[c_FourCerts#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#6)]

### <a name="to-use-multiple-certificates-on-the-service"></a>Para utilizar varios certificados en el servicio

1. Cree un enlace personalizado. El elemento de enlace de seguridad debe funcionar en modo dúplex para permitir que distintos proveedores de tokens de seguridad estén presentes para las solicitudes y respuestas. Tal y como ocurre con el cliente, utilice un transporte de tipo dúplex o use <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> tal y como se muestra en el código siguiente. Reemplace las credenciales de servicio predeterminadas con las credenciales de servicio personalizadas creadas previamente.

     [!code-csharp[c_FourCerts#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_fourcerts/cs/source.cs#7)]
     [!code-vb[c_FourCerts#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_fourcerts/vb/source.vb#7)]

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>
- <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>
- <xref:System.ServiceModel.Security.IdentityVerifier>
- [Tutorial: Crear credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md)
