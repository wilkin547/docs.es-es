---
description: 'Más información acerca de cómo: crear un servicio de token de seguridad'
title: Procedimiento para crear un servicio de token de seguridad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 98e82101-4cff-4bb8-a220-f7abed3556e5
ms.openlocfilehash: a3bfe6f97eeccdb31d3b8f4ef6c05a3c15257e91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734456"
---
# <a name="how-to-create-a-security-token-service"></a>Procedimiento para crear un servicio de token de seguridad

Un servicio de token de seguridad implementa el protocolo definido en la especificación de WS-Trust. Este protocolo define formatos de mensaje y patrones de intercambio de mensajes para emitir, renovar, cancelar y validar tokens de seguridad. Un servicio de token de seguridad determinado proporciona uno o más de estas funciones. Este tema aborda el escenario común: implementación de la emisión de token.  
  
## <a name="issuing-tokens"></a>Emitir tokens  

 WS-Trust define los formatos de mensaje, basándose en el elemento de esquema del lenguaje de definición de esquemas XML (XSD) `RequestSecurityToken` y en el elemento de esquema XSD `RequestSecurityTokenResponse` para realizar la emisión del token. Además, define los URI (Uniform Resource Identifier) de acción. El URI de acción asociado al `RequestSecurityToken` mensaje es `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue` . El URI de acción asociado al `RequestSecurityTokenResponse` mensaje es   `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue` .  
  
### <a name="request-message-structure"></a>Estructura de mensaje de solicitud  

 La estructura del mensaje de solicitud de problema está normalmente compuesta de los elementos siguientes:  
  
- Un URI del tipo de solicitud con un valor de `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue` .
  
- Un URI del tipo de token. En el caso de tokens de lenguaje de marcado de aserciones de seguridad (SAML) 1,1, el valor de este URI es `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1` .  
  
- Un valor de tamaño clave que indica el número de bits en la clave que se va asociar al token emitido.  
  
- Un tipo URI clave. En el caso de las claves simétricas, el valor de este identificador URI es `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey` .  
  
 Además, un par de otros elementos podrían estar presentes:  
  
- Material clave proporcionado por el cliente.  
  
- Información de ámbito que indica el servicio de destino con el que se utilizará el token emitido.  
  
 El servicio de token de seguridad utiliza la información en el mensaje de solicitud del problema cuando construye el mensaje de respuesta del problema.  
  
## <a name="response-message-structure"></a>Estructura del mensaje de respuesta  

 La estructura del mensaje de respuesta del problema está normalmente compuesta de los elementos siguientes;  
  
- El token de seguridad emitido, por ejemplo, una aserción SAML 1.1.  
  
- Un token de prueba asociado al token de seguridad. Para las claves simétricas, éste es a menudo una forma cifrada del material clave.  
  
- Hace referencia al token de seguridad emitido. Normalmente, el servicio del token de seguridad devuelve una referencia que se puede utilizar cuando el token emitido aparece en un mensaje subsiguiente enviado por el cliente y otro que se puede utilizar cuando el token no se encuentra presente en mensajes subsiguientes.  
  
 Además, un par de otros elementos podrían estar presentes:  
  
- Material clave proporcionado por el servicio del token de seguridad.  
  
- El algoritmo necesario para calcular la clave compartida.  
  
- Información de duración del token emitido.  
  
## <a name="processing-request-messages"></a>Procesar los mensajes de solicitud  

 El servicio del token de seguridad procesa la solicitud del problema examinando las varias partes del mensaje de solicitud y asegurándose de que puede emitir un token que satisfaga la solicitud. El servicio del token de seguridad debe determinar lo siguiente antes de construir el token que se va a emitir:  
  
- La solicitud realmente es una solicitud para un token que se va a emitir.  
  
- El servicio del token de seguridad soporta el tipo de token solicitado.  
  
- El solicitante está autorizado para realizar la solicitud.  
  
- El servicio del token de seguridad puede satisfacer las expectativas del solicitante con respecto al material clave.  
  
 Dos partes vitales de la construcción de un token determinan con qué clave se firmará el token y con qué clave se cifrará la clave compartida. El token debe ser firmado para que cuando el cliente presenta el token al servicio de destino, ese servicio pueda determinar que el token fue emitido por un servicio del token de seguridad en el que confía. El material clave debe cifrarse de manera que el servicio de destino pueda descifrar ese material de clave.  
  
 La firma de una aserción SAML implica la creación de una instancia <xref:System.IdentityModel.Tokens.SigningCredentials>. El constructor para esta clase toma lo siguiente:  
  
- <xref:System.IdentityModel.Tokens.SecurityKey> para que la clave lo utilice para firmar la aserción SAML.  
  
- Una cadena que identifica el algoritmo de firma a utilizar.  
  
- Una cadena que identifica el algoritmo de resumen a utilizar.  
  
- Opcionalmente, <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> que identifica la clave a utilizar para firmar la aserción.  
  
 [!code-csharp[c_CreateSTS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#1)]
 [!code-vb[c_CreateSTS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#1)]  
  
 El cifrado de la clave compartida implica tomar el material clave y cifrarlo con una clave que el servicio de destino pueda utilizar para descifrar la clave compartida. Normalmente, se utiliza la clave pública del servicio de destino.  
  
 [!code-csharp[c_CreateSTS#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#2)]
 [!code-vb[c_CreateSTS#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#2)]  
  
 Además, se necesita <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> para la clave cifrada.  
  
 [!code-csharp[c_CreateSTS#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#3)]
 [!code-vb[c_CreateSTS#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#3)]  
  
 <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> se utiliza a continuación para crear un `SamlSubject` como parte del `SamlToken`.  
  
 [!code-csharp[c_CreateSTS#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#4)]
 [!code-vb[c_CreateSTS#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#4)]  
  
 Para obtener más información, vea [ejemplo de Federación](../samples/federation-sample.md).  
  
## <a name="creating-response-messages"></a>Crear los mensajes de respuesta  

 Cuando el servicio de token de seguridad procesa la solicitud del problema y construye el token que se va a emitir junto con la clave de prueba, el mensaje de respuesta necesita ser construido, incluyendo como mínimo el token solicitado, el token de prueba y las referencias del token emitido. El token emitido es normalmente <xref:System.IdentityModel.Tokens.SamlSecurityToken> creado a partir de <xref:System.IdentityModel.Tokens.SamlAssertion>, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[c_CreateSTS#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#5)]
 [!code-vb[c_CreateSTS#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#5)]  
  
 En el caso donde el servicio del token de seguridad proporciona el material de la clave compartida, el token de prueba se construye creando <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.  
  
 [!code-csharp[c_CreateSTS#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#6)]
 [!code-vb[c_CreateSTS#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#6)]  
  
 Para obtener más información sobre cómo construir el token de prueba cuando el cliente y el servicio de token de seguridad proporcionan el material de clave para la clave compartida, vea [ejemplo de Federación](../samples/federation-sample.md).  
  
 Las referencias del token emitido se construyen creando instancias de la clase <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>.  
  
 [!code-csharp[c_CreateSTS#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#7)]
 [!code-vb[c_CreateSTS#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#7)]  
  
 Estos valores diferentes se serializan a continuación en el mensaje de respuesta devuelto al cliente.  
  
## <a name="example"></a>Ejemplo  

 Para ver el código completo de un servicio de token de seguridad, vea [ejemplo de Federación](../samples/federation-sample.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Tokens.SigningCredentials>
- <xref:System.IdentityModel.Tokens.SecurityKey>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>
- <xref:System.IdentityModel.Tokens.SamlSecurityToken>
- <xref:System.IdentityModel.Tokens.SamlAssertion>
- <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>
- [Ejemplo de federación](../samples/federation-sample.md)
