---
title: Procedimiento para crear un token personalizado
description: Obtenga información sobre cómo crear un token de seguridad personalizado en WCF mediante la clase SecurityToken y cómo integrarlo con un proveedor de tokens de seguridad y un autenticador.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SecurityTokenParameters class
- security [WCF], creating custom tokens
- WSSecurityTokenSerializer class
- SecurityToken class
ms.assetid: 6d892973-1558-4115-a9e1-696777776125
ms.openlocfilehash: a95d663c2669186fcb3eb1fb2f0c426ade945f1c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247538"
---
# <a name="how-to-create-a-custom-token"></a>Procedimiento para crear un token personalizado
Este tema muestra cómo crear un token de seguridad personalizado mediante la clase <xref:System.IdentityModel.Tokens.SecurityToken> y cómo integrarlo en un autenticador y en un proveedor de token de seguridad personalizado. Para obtener un ejemplo de código completo, vea el ejemplo de [token personalizado](../samples/custom-token.md) .  
  
 Un *token de seguridad* es esencialmente un elemento XML que utiliza el marco de seguridad Windows Communication Foundation (WCF) para representar las notificaciones sobre un remitente dentro del mensaje SOAP. La seguridad de WCF proporciona varios tokens para los modos de autenticación proporcionados por el sistema. En los ejemplos se incluye un token de seguridad de certificado X.509 representado por la clase <xref:System.IdentityModel.Tokens.X509SecurityToken> o un token de seguridad Username representado por la clase <xref:System.IdentityModel.Tokens.UserNameSecurityToken>.  
  
 A veces los tipos proporcionados no admiten un modo de autenticación o credencial. En ese caso, es necesario para crear un token de seguridad personalizado para proporcionar una representación XML de la credencial personalizada dentro del mensaje SOAP.  
  
 En los procedimientos siguientes se muestra cómo crear un token de seguridad personalizado y cómo integrarlo con la infraestructura de seguridad de WCF. En este tema se crea un token de tarjeta de crédito que se utiliza para pasar información sobre la tarjeta de crédito del cliente al servidor.  
  
 Para obtener más información sobre las credenciales personalizadas y el administrador de tokens de seguridad, vea [Tutorial: crear credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md).  
  
 Vea el espacio de nombres <xref:System.IdentityModel.Tokens> para obtener más clases que representen tokens de seguridad.  
  
## <a name="procedures"></a>Procedimientos  
 Es necesario proporcionar a una aplicación cliente una manera de especificar información de la tarjeta de crédito para la infraestructura de seguridad. Una clase de credenciales de cliente personalizada pone esta información a disposición de la aplicación. El primer paso es crear una clase para que represente la información de la tarjeta de crédito para las credenciales de cliente personalizadas.  
  
#### <a name="to-create-a-class-that-represents-credit-card-information-inside-client-credentials"></a>Para crear una clase que represente información de la tarjeta de crédito dentro de las credenciales de cliente  
  
1. Defina una nueva clase que represente la información de la tarjeta de crédito para la aplicación. En el siguiente ejemplo se nombra la clase `CreditCardInfo`.  
  
2. Agregue las propiedades adecuadas a la clase para permitir que una aplicación establezca la información necesaria para el token personalizado. En este ejemplo, la clase tiene tres propiedades: `CardNumber`, `CardIssuer`y `ExpirationDate`.  
  
     [!code-csharp[c_CustomToken#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#4)]
     [!code-vb[c_CustomToken#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#4)]  
  
 A continuación, se ha de crear una clase que represente el token de seguridad personalizado. Esta clase la usan las clases de proveedor de tokens de seguridad, autenticador y serializador para pasar información sobre el token de seguridad hacia y desde la infraestructura de seguridad de WCF.  
  
#### <a name="to-create-a-custom-security-token-class"></a>Para crear una clase de token de seguridad personalizada  
  
1. Defina una clase nueva derivada de la clase <xref:System.IdentityModel.Tokens.SecurityToken>. En este ejemplo se crea una clase denominada `CreditCardToken`.  
  
2. Invalide la propiedad <xref:System.IdentityModel.Tokens.SecurityToken.Id%2A>. Esta propiedad se utiliza para obtener el identificador local del token de seguridad que se utiliza para señalar a la representación XML del token de seguridad desde otros elementos dentro del mensaje SOAP. En este ejemplo, se le puede pasar un identificador de token como parámetro de constructor o se puede generar uno nuevo aleatorio cada vez que se cree una instancia de token de seguridad.  
  
3. Implemente la propiedad <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A>. Esta propiedad devuelve una colección de claves de seguridad que representa la instancia del token de seguridad. WCF puede usar estas claves para firmar o cifrar partes del mensaje SOAP. En este ejemplo, el token de seguridad de la tarjeta de crédito no puede contener ninguna clave de seguridad; por consiguiente, la implementación siempre devuelve una colección vacía.  
  
4. Invalide las propiedades <xref:System.IdentityModel.Tokens.SecurityToken.ValidFrom%2A> y <xref:System.IdentityModel.Tokens.SecurityToken.ValidTo%2A>. WCF usa estas propiedades para determinar la validez de la instancia del token de seguridad. En este ejemplo, el token de seguridad de la tarjeta de crédito solo tiene una fecha de expiración, por lo que la propiedad `ValidFrom` devuelve <xref:System.DateTime> que representa la fecha y hora de creación de la instancia.  
  
     [!code-csharp[c_CustomToken#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#1)]
     [!code-vb[c_CustomToken#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#1)]  
  
 Cuando se crea un nuevo tipo de token de seguridad, requiere una implementación de la clase <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters>. La implementación se utiliza en la configuración del elemento de enlace de seguridad para representar el nuevo tipo de token. La clase de los parámetros de token de seguridad sirve como plantilla que se emplea para igualar a la instancia del token de seguridad real cuando se procesa un mensaje. La plantilla proporciona propiedades adicionales que una aplicación puede utilizar para especificar los criterios a los que debe ajustarse el token de seguridad para que pueda usarse o autenticarse. En el ejemplo siguiente no se agregan propiedades adicionales, por lo que solo se compara el tipo de token de seguridad cuando la infraestructura de WCF busca una instancia de token de seguridad para usar o validar.  
  
#### <a name="to-create-a-custom-security-token-parameters-class"></a>Para crear una clase de parámetros de token de seguridad personalizada  
  
1. Defina una clase nueva derivada de la clase <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters>.  
  
2. Implemente el método <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.CloneCore%2A>. Copie todos los campos internos definidos en su clase, si hubiese alguno. Este ejemplo no define ningún campo adicional.  
  
3. Implemente la propiedad de solo lectura <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.SupportsClientAuthentication%2A>. Esta propiedad devuelve `true` si el tipo de token de seguridad representado por esta clase se puede utilizar para autenticar un cliente a un servicio. En este ejemplo, el token de seguridad de la tarjeta de crédito se puede utilizar para autenticar un cliente a un servicio.  
  
4. Implemente la propiedad de solo lectura <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.SupportsServerAuthentication%2A>. Esta propiedad devuelve `true` si el tipo de token de seguridad representado por esta clase se puede utilizar para autenticar un servicio a un cliente. En este ejemplo, el token de seguridad de la tarjeta de crédito no se puede utilizar para autenticar un servicio a un cliente.  
  
5. Implemente la propiedad de solo lectura <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.SupportsClientWindowsIdentity%2A>. Esta propiedad devuelve `true` si el tipo de token de seguridad representado por esta clase puede asignarse a una cuenta de Windows. En ese caso, el resultado de la autenticación se representa mediante una instancia de la clase <xref:System.Security.Principal.WindowsIdentity>. En este ejemplo, el token no se puede asignar a una cuenta de Windows.  
  
6. Implemente el método <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.CreateKeyIdentifierClause%28System.IdentityModel.Tokens.SecurityToken%2CSystem.ServiceModel.Security.Tokens.SecurityTokenReferenceStyle%29>. El marco de seguridad de WCF llama a este método cuando requiere una referencia a la instancia del token de seguridad representada por esta clase de parámetros de token de seguridad. Tanto la instancia del token de seguridad real como el <xref:System.ServiceModel.Security.Tokens.SecurityTokenReferenceStyle> que especifica el tipo de la referencia que se solicita se pasan a este método como argumentos. En este ejemplo el token de seguridad de la tarjeta de crédito solo admite referencias internas. La clase <xref:System.IdentityModel.Tokens.SecurityToken> tiene funcionalidad para crear referencias internas, por lo que la implementación no precisa código adicional.  
  
7. Implemente el método <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.InitializeSecurityTokenRequirement%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>. WCF llama a este método para convertir la instancia de la clase de parámetros de token de seguridad en una instancia de la <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> clase. Los proveedores de tokens de seguridad utilizan el resultado para crear la instancia del token de seguridad adecuada.  
  
     [!code-csharp[c_CustomToken#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#2)]
     [!code-vb[c_CustomToken#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#2)]  
  
 Los tokens de seguridad se transmiten dentro de los mensajes SOAP, lo que necesita un mecanismo de traducción entre la representación del token de seguridad en memoria y la representación en tránsito. WCF usa un serializador de tokens de seguridad para realizar esta tarea. Todos los tokens personalizados deben estar acompañados de un serializador de tokens de seguridad personalizado que pueda serializar y deserializar el token de seguridad personalizado del mensaje SOAP.  
  
> [!NOTE]
> Las claves derivadas están habilitadas de forma predeterminada. Si crea un token de seguridad personalizado y lo usa como el token principal, WCF deriva una clave a partir de él. En este proceso, llama al serializador del token de seguridad personalizado para escribir la <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> para el token de seguridad personalizado durante la serialización de `DerivedKeyToken` en la conexión. En el extremo receptor, al deserializar el token fuera de la conexión, el serializador `DerivedKeyToken` espera un elemento `SecurityTokenReference` como elemento secundario de nivel superior bajo sí mismo. Si el serializador del token de seguridad personalizado no agregó un elemento `SecurityTokenReference` durante la serialización de su tipo de cláusula, se produce una excepción.  
  
#### <a name="to-create-a-custom-security-token-serializer"></a>Para crear un serializador de tokens de seguridad personalizado  
  
1. Defina una clase nueva derivada de la clase <xref:System.ServiceModel.Security.WSSecurityTokenSerializer>.  
  
2. Invalide el método <xref:System.ServiceModel.Security.WSSecurityTokenSerializer.CanReadTokenCore%28System.Xml.XmlReader%29>, que se basa en un <xref:System.Xml.XmlReader> para leer la secuencia XML. El método devuelve `true` si la implementación del serializador puede deserializar el token de seguridad dado su elemento actual. En este ejemplo, este método comprueba si el elemento XML actual del lector XML tiene el nombre de elemento y espacio de nombres correctos. Si no es así, llama a la implementación de la clase base de este método para controlar el elemento XML.  
  
3. Invalide el método <xref:System.ServiceModel.Security.WSSecurityTokenSerializer.ReadTokenCore%28System.Xml.XmlReader%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%29> . Este método lee el contenido XML del token de seguridad y construye la representación en memoria adecuada para el mismo. Si no reconoce el elemento XML sobre el que se alza el lector XML pasado, llama a la implementación de la clase base para procesar los tipos de token proporcionados por el sistema.  
  
4. Invalide el método <xref:System.ServiceModel.Security.WSSecurityTokenSerializer.CanWriteTokenCore%28System.IdentityModel.Tokens.SecurityToken%29> . Este método devuelve `true` si puede convertir la representación del token en memoria (pasado como argumento) en la representación XML. Si no puede convertirlo, llama a la implementación de la clase base.  
  
5. Invalide el método <xref:System.ServiceModel.Security.WSSecurityTokenSerializer.WriteTokenCore%28System.Xml.XmlWriter%2CSystem.IdentityModel.Tokens.SecurityToken%29> . Este método convierte una representación de tokens de seguridad en memoria en una representación XML. Si el método no puede convertirlo, llama a la implementación de la clase base.  
  
     [!code-csharp[c_CustomToken#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#3)]
     [!code-vb[c_CustomToken#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#3)]  
  
 Después de completar los cuatro procedimientos anteriores, integre el token de seguridad personalizado con el proveedor de tokens de seguridad, autenticador, administrador y credenciales de cliente y servicio.  
  
#### <a name="to-integrate-the-custom-security-token-with-a-security-token-provider"></a>Para integrar el token de seguridad personalizado con un proveedor de tokens de seguridad  
  
1. El proveedor de tokens de seguridad crea, modifica (si es necesario) y devuelve una instancia del token. Para crear un proveedor personalizado para el token de seguridad personalizado, cree una clase que herede de la clase <xref:System.IdentityModel.Selectors.SecurityTokenProvider>. En el ejemplo siguiente se invalida el método <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> para devolver una instancia de `CreditCardToken`. Para obtener más información acerca de los proveedores de tokens de seguridad personalizados, consulte [Cómo: crear un proveedor de tokens de seguridad personalizado](how-to-create-a-custom-security-token-provider.md).  
  
     [!code-csharp[c_CustomToken#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#6)]
     [!code-vb[c_CustomToken#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#6)]  
  
#### <a name="to-integrate-the-custom-security-token-with-a-security-token-authenticator"></a>Para integrar el token de seguridad personalizado con un autenticador de tokens de seguridad  
  
1. El autenticador de tokens de seguridad valida el contenido del token de seguridad cuando se extrae del mensaje. Para crear un autenticador personalizado para el token de seguridad personalizado, cree una clase que herede de la clase <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>. En el siguiente ejemplo se reemplaza el método <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.ValidateTokenCore%2A>. Para obtener más información sobre los autenticadores de tokens de seguridad personalizados, consulte [Cómo: crear un autenticador de tokens de seguridad personalizado](how-to-create-a-custom-security-token-authenticator.md).  
  
     [!code-csharp[c_CustomToken#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#7)]
     [!code-vb[c_CustomToken#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#7)]  
  
     [!code-csharp[c_CustomToken#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#12)]
     [!code-vb[c_CustomToken#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#12)]  
  
#### <a name="to-integrate-the-custom-security-token-with-a-security-token-manager"></a>Para integrar el token de seguridad personalizado con un administrador de tokens de seguridad  
  
1. El administrador de tokens de seguridad crea el proveedor de tokens, el autenticador de seguridad y las instancias del serializador de tokens adecuados. Para crear un administrador de tokens personalizado, cree una clase que herede de la clase <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>. Los métodos principales de la clase usan un <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> para crear el proveedor y las credenciales de cliente o servicio adecuados. Para obtener más información acerca de los administradores de tokens de seguridad personalizados, vea [Tutorial: crear credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomToken#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#8)]
     [!code-vb[c_CustomToken#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#8)]  
  
     [!code-csharp[c_CustomToken#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#9)]
     [!code-vb[c_CustomToken#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#9)]  
  
#### <a name="to-integrate-the-custom-security-token-with-custom-client-and-service-credentials"></a>Para integrar el token de seguridad personalizado con credenciales de cliente y servicio personalizadas  
  
1. Es necesario agregar credenciales de cliente y servicio personalizadas para proporcionar una API de manera que la aplicación permita especificar la información de tokens personalizados que utiliza la infraestructura de tokens de seguridad personalizados antes creada para proporcionar y autenticar el contenido del token de seguridad personalizado. Los ejemplos siguientes muestran cómo hacerlo. Para obtener más información acerca de las credenciales de cliente y servicio personalizadas, vea [Tutorial: crear credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomToken#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#10)]
     [!code-vb[c_CustomToken#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#10)]  
  
     [!code-csharp[c_customToken#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#11)]
     [!code-vb[c_customToken#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#11)]  
  
 La clase de parámetros de token de seguridad personalizada creada anteriormente se utiliza para indicar al marco de seguridad de WCF que se debe usar un token de seguridad personalizado al comunicarse con un servicio. En el siguiente procedimiento se muestra cómo hacerlo:  
  
#### <a name="to-integrate-the-custom-security-token-with-the-binding"></a>Para integrar el token de seguridad personalizado con el enlace  
  
1. La clase de parámetros de tokens de seguridad personalizados ha de especificarse en una de las colecciones de parámetros de tokens que se exponen en la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>. El siguiente ejemplo usa la colección devuelta por `SignedEncrypted`. El código agrega el token personalizado de la tarjeta de crédito a cada mensaje enviado desde el cliente al servicio con su contenido firmado y cifrado automáticamente.  
  
     [!code-csharp[c_CustomToken#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtoken/cs/source.cs#13)]
     [!code-vb[c_CustomToken#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtoken/vb/source.vb#13)]  
  
 En este tema se muestran los distintos elementos de código necesarios para implementar y usar un token personalizado. Para ver un ejemplo completo de cómo encajan todos estos fragmentos de código, vea [token personalizado](../samples/custom-token.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Tokens.SecurityToken>
- <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters>
- <xref:System.ServiceModel.Security.WSSecurityTokenSerializer>
- <xref:System.IdentityModel.Selectors.SecurityTokenProvider>
- <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.Channels.SecurityBindingElement>
- [Tutorial: Crear credenciales de cliente y servicio personalizadas](walkthrough-creating-custom-client-and-service-credentials.md)
- [Procedimiento para crear un autenticador de tokens de seguridad personalizado](how-to-create-a-custom-security-token-authenticator.md)
- [Procedimiento para crear un proveedor de tokens de seguridad personalizado](how-to-create-a-custom-security-token-provider.md)
