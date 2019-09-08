---
title: Procedimiento para crear un proveedor de tokens de seguridad personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
ms.openlocfilehash: 1ca12274358ed6de475b0c2b8b47dd5cb52e941e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797034"
---
# <a name="how-to-create-a-custom-security-token-provider"></a>Procedimiento para crear un proveedor de tokens de seguridad personalizado
En este tema se muestra cómo crear nuevos tipos de token con un proveedor de tokens de seguridad personalizado y cómo integrar el proveedor con un administrador de tokens de seguridad personalizado.  
  
> [!NOTE]
> Cree un proveedor de tokens personalizado si los tokens proporcionados por el sistema ubicados en el espacio de nombres <xref:System.IdentityModel.Tokens> no coinciden con sus requisitos.  
  
 El proveedor de tokens de seguridad crea una representación de token de seguridad basada en información en el cliente o en las credenciales de servicio. Para usar el proveedor de tokens de seguridad personalizado en la seguridad de Windows Communication Foundation (WCF), debe crear las credenciales personalizadas y las implementaciones del administrador de tokens de seguridad.  
  
 Para obtener más información sobre las credenciales personalizadas y el administrador [de tokens de seguridad, vea el tutorial: Crear credenciales](walkthrough-creating-custom-client-and-service-credentials.md)de cliente y servicio personalizadas.  
  
### <a name="to-create-a-custom-security-token-provider"></a>Para crear un proveedor de tokens de seguridad personalizado  
  
1. Defina una clase nueva derivada de la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider>.  
  
2. Implemente el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>. El método es responsable de crear y devolver una instancia del token de seguridad. El ejemplo siguiente crea una clase denominada `MySecurityTokenProvider`e invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> para devolver una instancia de la clase <xref:System.IdentityModel.Tokens.X509SecurityToken>. El constructor de clase necesita una instancia de la clase <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a>Para integrar un proveedor de tokens de seguridad personalizado con un administrador de tokens de seguridad personalizado  
  
1. Defina una clase nueva derivada de la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>. (El siguiente ejemplo se deriva de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, que se deriva de la clase <xref:System.IdentityModel.Selectors.SecurityTokenManager>).  
  
2. Si no está ya invalidado, invalide el método <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>.  
  
     El <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> método es responsable de devolver una instancia de la <xref:System.IdentityModel.Selectors.SecurityTokenProvider> clase adecuada al <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parámetro que el marco de seguridad de WCF ha pasado al método. Modifique el método para devolver la implementación de proveedor de tokens de seguridad personalizado (creada en el procedimiento anterior) cuando se llama al método con un parámetro de token de seguridad adecuado. Para obtener más información sobre el administrador de tokens de [seguridad, vea el tutorial: Crear credenciales](walkthrough-creating-custom-client-and-service-credentials.md)de cliente y servicio personalizadas.  
  
3. Agregue la lógica personalizada al método para permitirle que devuelva su proveedor de tokens de seguridad personalizado basado en el parámetro <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>. El ejemplo siguiente devuelve el proveedor de tokens de seguridad personalizado si se cumplen los requisitos del token. Los requisitos incluyen un token de seguridad X.509 y la dirección del mensaje (que el token se utiliza para la salida del mensaje). Para todos los casos restantes, el código llama a la clase base para mantener el comportamiento proporcionado por el sistema para otros requisitos de token de seguridad.  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a>Ejemplo  
 A continuación se presenta una implementación <xref:System.IdentityModel.Selectors.SecurityTokenProvider> completa junto con una implementación <xref:System.IdentityModel.Selectors.SecurityTokenManager> correspondiente.  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Selectors.SecurityTokenProvider>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.IdentityModel.Tokens.X509SecurityToken>
- [Tutorial: Creación de credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md)
- [Cómo: Crear un autenticador de tokens de seguridad personalizado](how-to-create-a-custom-security-token-authenticator.md)
