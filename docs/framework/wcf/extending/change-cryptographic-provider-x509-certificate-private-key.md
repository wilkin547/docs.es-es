---
title: Filtrar Cambiar el proveedor de servicios criptográficos de clave privada de un certificado X.509
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptographic provider [WCF], changing
- cryptographic provider [WCF]
ms.assetid: b4254406-272e-4774-bd61-27e39bbb6c12
ms.openlocfilehash: 4e11dd90d1cc57f3f2f559c22e1548b8fbcedaea
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261917"
---
# <a name="how-to-change-the-cryptographic-provider-for-an-x509-certificates-private-key"></a>Filtrar Cambiar el proveedor de servicios criptográficos de clave privada de un certificado X.509
En este tema se muestra cómo cambiar el proveedor criptográfico utilizado para proporcionar la clave privada de un certificado X.509 y cómo integrar el proveedor en el marco de seguridad de Windows Communication Foundation (WCF). Para obtener más información sobre el uso de certificados, consulte [trabajar con certificados](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 El marco de seguridad WCF proporciona una manera de introducir nuevos tipos de token de seguridad, como se describe en [Cómo: Crear un Token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md). También es posible utilizar un token personalizado para reemplazar los tipos existentes de token proporcionados por el sistema.  
  
 En este tema, un token X.509 personalizado que proporciona una implementación diferente para la clave privada del certificado reemplaza el token de seguridad X.509 proporcionado por el sistema. Esto es útil en escenarios donde un proveedor criptográfico diferente al proveedor criptográfico predeterminado de Windows proporciona la clave privada real. Un ejemplo de un proveedor criptográfico alternativo es un módulo de seguridad de hardware que lleva a cabo todas las operaciones criptográficas relacionadas con clave privada, y no almacena las claves privadas en memoria, de modo que mejora la seguridad del sistema.  
  
 El siguiente ejemplo solamente sirve de demostración. No reemplaza el proveedor criptográfico predeterminado de Windows, pero muestra donde se pudo integrar este tipo de proveedor.  
  
## <a name="procedures"></a>Procedimientos  
 Cada token de seguridad que tiene una clave o claves de seguridad asociadas debe implementar la propiedad <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A>, que devuelve una colección de claves desde la instancia del token de seguridad. Si el token es un token de seguridad X.509, la colección contiene una instancia única de la clase <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> que representa claves públicas y claves privadas asociadas al certificado. Para reemplazar el proveedor criptográfico predeterminado utilizado para proporcionar las claves del certificado, cree una nueva implementación de esta clase.  
  
#### <a name="to-create-a-custom-x509-asymmetric-key"></a>Crear una clave asimétrica X.509 personalizada  
  
1.  Defina una clase nueva derivada de la clase <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>.  
  
2.  Reemplace la propiedad de solo lectura <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A>. Esta propiedad devuelve el tamaño de clave real del par de clave pública/privada del certificado.  
  
3.  Invalide el método <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A> . Este método se llama el marco de seguridad WCF para descifrar una clave simétrica con la clave privada del certificado. (La clave se cifró previamente con la clave pública del certificado.)  
  
4.  Invalide el método <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A> . Este método se llama el marco de seguridad WCF para obtener una instancia de la <xref:System.Security.Cryptography.AsymmetricAlgorithm> clase que representa el proveedor de servicios criptográficos de clave privada o pública del certificado, dependiendo de los parámetros pasados al método.  
  
5.  Opcional. Invalide el método <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A>. Invalide este método si se requiere una implementación diferente de la clase <xref:System.Security.Cryptography.HashAlgorithm>.  
  
6.  Invalide el método <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A>. Este método devuelve una instancia de la clase <xref:System.Security.Cryptography.AsymmetricSignatureFormatter> que está asociada a la clave privada del certificado.  
  
7.  Invalide el método <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A>. Este método se utiliza para indicar si la implementación de clave de seguridad admite un algoritmo criptográfico determinado.  
  
     [!code-csharp[c_CustomX509Token#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#1)]
     [!code-vb[c_CustomX509Token#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#1)]  
  
 El siguiente procedimiento muestra cómo integrar la implementación de claves personalizada del seguridad asimétrico de X.509 creada en el procedimiento anterior con el marco de seguridad WCF con el fin de reemplazar la seguridad X.509 proporcionado por el sistema de token.  
  
#### <a name="to-replace-the-system-provided-x509-security-token-with-a-custom-x509-asymmetric-security-key-token"></a>Reemplazar el token de seguridad X.509 proporcionado por el sistema por un token clave de seguridad asimétrico personalizado X.509.  
  
1.  Cree un token de seguridad X.509 personalizado que devuelve la clave de seguridad asimétrica personalizada X.509 en lugar de la clave de seguridad proporcionada por el sistema, tal y como se muestra en el ejemplo siguiente. Para obtener más información acerca de los tokens de seguridad personalizado, vea [Cómo: Crear un Token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
     [!code-csharp[c_CustomX509Token#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#2)]
     [!code-vb[c_CustomX509Token#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#2)]  
  
2.  Cree un proveedor de token de seguridad personalizado que devuelve un token de seguridad X.509 personalizado, tal y como se muestra en el ejemplo. Para obtener más información acerca de los proveedores de tokens de seguridad personalizado, vea [Cómo: Crear un proveedor de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).  
  
     [!code-csharp[c_CustomX509Token#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#3)]
     [!code-vb[c_CustomX509Token#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#3)]  
  
3.  Si es necesario utilizar la clave de seguridad personalizada en el lado del iniciador, cree un administrador de tokens de seguridad de cliente personalizados y las clases de credenciales de cliente personalizadas, tal y como se muestra en el ejemplo siguiente. Para obtener más información sobre las credenciales de cliente personalizadas y administradores de tokens de seguridad de cliente, consulte [Tutorial: Creación de cliente personalizada y las credenciales de servicio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#4)]
     [!code-vb[c_CustomX509Token#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#4)]  
  
     [!code-csharp[c_CustomX509Token#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#6)]
     [!code-vb[c_CustomX509Token#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#6)]  
  
4.  Si es necesario utilizar la clave de seguridad personalizada en el lado del receptor, cree un administrador de tokens de seguridad de servicio personalizados y las clases de credenciales de servicio personalizadas, tal y como se muestra en el ejemplo siguiente. Para obtener más información sobre las credenciales de servicio personalizadas y administradores de tokens de seguridad de servicio, consulte [Tutorial: Creación de cliente personalizada y las credenciales de servicio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#5)]
     [!code-vb[c_CustomX509Token#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#5)]  
  
     [!code-csharp[c_CustomX509Token#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#7)]
     [!code-vb[c_CustomX509Token#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#7)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>
- <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey>
- <xref:System.IdentityModel.Tokens.SecurityKey>
- <xref:System.Security.Cryptography.AsymmetricAlgorithm>
- <xref:System.Security.Cryptography.HashAlgorithm>
- <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>
- [Tutorial: Creación de cliente personalizada y las credenciales de servicio](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)
- [Cómo: Crear un autenticador de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)
- [Cómo: Crear un proveedor de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)
- [Cómo: Crear un Token personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)
