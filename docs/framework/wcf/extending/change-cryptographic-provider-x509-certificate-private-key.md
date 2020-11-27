---
title: Procedimiento para cambiar el proveedor criptográfico para la clave privada de un certificado X.509
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptographic provider [WCF], changing
- cryptographic provider [WCF]
ms.assetid: b4254406-272e-4774-bd61-27e39bbb6c12
ms.openlocfilehash: 33d42f26407787b26e1447f8b8f619dd6fc15229
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262117"
---
# <a name="how-to-change-the-cryptographic-provider-for-an-x509-certificates-private-key"></a>Procedimiento para cambiar el proveedor criptográfico para la clave privada de un certificado X.509

En este tema se muestra cómo cambiar el proveedor de servicios criptográficos que se usa para proporcionar la clave privada de un certificado X. 509 y cómo integrar el proveedor en el marco de seguridad de Windows Communication Foundation (WCF). Para obtener más información sobre el uso de certificados, consulte [trabajar con certificados](../feature-details/working-with-certificates.md).  
  
 El marco de seguridad de WCF proporciona una manera de introducir nuevos tipos de tokens de seguridad, tal y como se describe en [Cómo: crear un token personalizado](how-to-create-a-custom-token.md). También es posible utilizar un token personalizado para reemplazar los tipos existentes de token proporcionados por el sistema.  
  
 En este tema, un token X.509 personalizado que proporciona una implementación diferente para la clave privada del certificado reemplaza el token de seguridad X.509 proporcionado por el sistema. Esto es útil en escenarios donde un proveedor criptográfico diferente al proveedor criptográfico predeterminado de Windows proporciona la clave privada real. Un ejemplo de un proveedor criptográfico alternativo es un módulo de seguridad de hardware que lleva a cabo todas las operaciones criptográficas relacionadas con clave privada, y no almacena las claves privadas en memoria, de modo que mejora la seguridad del sistema.  
  
 El siguiente ejemplo solamente sirve de demostración. No reemplaza el proveedor criptográfico predeterminado de Windows, pero muestra donde se pudo integrar este tipo de proveedor.  
  
## <a name="procedures"></a>Procedimientos  

 Cada token de seguridad que tiene una clave o claves de seguridad asociadas debe implementar la propiedad <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A>, que devuelve una colección de claves desde la instancia del token de seguridad. Si el token es un token de seguridad X.509, la colección contiene una instancia única de la clase <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey> que representa claves públicas y claves privadas asociadas al certificado. Para reemplazar el proveedor criptográfico predeterminado utilizado para proporcionar las claves del certificado, cree una nueva implementación de esta clase.  
  
#### <a name="to-create-a-custom-x509-asymmetric-key"></a>Crear una clave asimétrica X.509 personalizada  
  
1. Defina una clase nueva derivada de la clase <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>.  
  
2. Reemplace la propiedad de solo lectura <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A>. Esta propiedad devuelve el tamaño de clave real del par de clave pública/privada del certificado.  
  
3. Invalide el método <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A>. El marco de seguridad de WCF llama a este método para descifrar una clave simétrica con la clave privada del certificado. (La clave se cifró previamente con la clave pública del certificado.)  
  
4. Invalide el método <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A>. El marco de seguridad de WCF llama a este método para obtener una instancia de la <xref:System.Security.Cryptography.AsymmetricAlgorithm> clase que representa el proveedor de servicios criptográficos para la clave pública o privada del certificado, dependiendo de los parámetros pasados al método.  
  
5. Opcional. Invalide el método <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A>. Invalide este método si se requiere una implementación diferente de la clase <xref:System.Security.Cryptography.HashAlgorithm>.  
  
6. Invalide el método <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A>. Este método devuelve una instancia de la clase <xref:System.Security.Cryptography.AsymmetricSignatureFormatter> que está asociada a la clave privada del certificado.  
  
7. Invalide el método <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A>. Este método se utiliza para indicar si la implementación de clave de seguridad admite un algoritmo criptográfico determinado.  
  
     [!code-csharp[c_CustomX509Token#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#1)]
     [!code-vb[c_CustomX509Token#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#1)]  
  
 En el procedimiento siguiente se muestra cómo integrar la implementación de la clave de seguridad asimétrica personalizada X. 509 creada en el procedimiento anterior con el marco de seguridad de WCF para reemplazar el token de seguridad X. 509 proporcionado por el sistema.  
  
#### <a name="to-replace-the-system-provided-x509-security-token-with-a-custom-x509-asymmetric-security-key-token"></a>Reemplazar el token de seguridad X.509 proporcionado por el sistema por un token clave de seguridad asimétrico personalizado X.509.  
  
1. Cree un token de seguridad X.509 personalizado que devuelve la clave de seguridad asimétrica personalizada X.509 en lugar de la clave de seguridad proporcionada por el sistema, tal y como se muestra en el ejemplo siguiente. Para obtener más información sobre los tokens de seguridad personalizados, consulte [Cómo: crear un token personalizado](how-to-create-a-custom-token.md).  
  
     [!code-csharp[c_CustomX509Token#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#2)]
     [!code-vb[c_CustomX509Token#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#2)]  
  
2. Cree un proveedor de token de seguridad personalizado que devuelve un token de seguridad X.509 personalizado, tal y como se muestra en el ejemplo. Para obtener más información acerca de los proveedores de tokens de seguridad personalizados, consulte [Cómo: crear un proveedor de tokens de seguridad personalizado](how-to-create-a-custom-security-token-provider.md).  
  
     [!code-csharp[c_CustomX509Token#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#3)]
     [!code-vb[c_CustomX509Token#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#3)]  
  
3. Si es necesario utilizar la clave de seguridad personalizada en el lado del iniciador, cree un administrador de tokens de seguridad de cliente personalizados y las clases de credenciales de cliente personalizadas, tal y como se muestra en el ejemplo siguiente. Para obtener más información sobre las credenciales de cliente personalizadas y los administradores de tokens de seguridad de cliente, vea [Tutorial: crear credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#4)]
     [!code-vb[c_CustomX509Token#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#4)]  
  
     [!code-csharp[c_CustomX509Token#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#6)]
     [!code-vb[c_CustomX509Token#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#6)]  
  
4. Si es necesario utilizar la clave de seguridad personalizada en el lado del receptor, cree un administrador de tokens de seguridad de servicio personalizados y las clases de credenciales de servicio personalizadas, tal y como se muestra en el ejemplo siguiente. Para obtener más información acerca de las credenciales de servicio personalizadas y los administradores de tokens de seguridad de servicio, vea [Tutorial: crear credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md).  
  
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
- [Tutorial: Crear credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md)
- [Procedimiento para crear un autenticador de tokens de seguridad personalizado](how-to-create-a-custom-security-token-authenticator.md)
- [Procedimiento para crear un proveedor de tokens de seguridad personalizado](how-to-create-a-custom-security-token-provider.md)
- [Procedimiento para crear un token personalizado](how-to-create-a-custom-token.md)
