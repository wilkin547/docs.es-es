---
title: Procedimiento para crear un servicio de token de seguridad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 98e82101-4cff-4bb8-a220-f7abed3556e5
ms.openlocfilehash: 1cfcca524e5dd2b0c1560eb7600795766e2db1d6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598962"
---
# <a name="how-to-create-a-security-token-service"></a><span data-ttu-id="17a62-102">Procedimiento para crear un servicio de token de seguridad</span><span class="sxs-lookup"><span data-stu-id="17a62-102">How to: Create a Security Token Service</span></span>
<span data-ttu-id="17a62-103">Un servicio de token de seguridad implementa el protocolo definido en la especificación de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="17a62-103">A security token service implements the protocol defined in the WS-Trust specification.</span></span> <span data-ttu-id="17a62-104">Este protocolo define formatos de mensaje y patrones de intercambio de mensajes para emitir, renovar, cancelar y validar tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="17a62-104">This protocol defines message formats and message exchange patterns for issuing, renewing, canceling, and validating security tokens.</span></span> <span data-ttu-id="17a62-105">Un servicio de token de seguridad determinado proporciona uno o más de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="17a62-105">A given security token service provides one or more of these capabilities.</span></span> <span data-ttu-id="17a62-106">Este tema aborda el escenario común: implementación de la emisión de token.</span><span class="sxs-lookup"><span data-stu-id="17a62-106">This topic looks at the most common scenario: implementing token issuance.</span></span>  
  
## <a name="issuing-tokens"></a><span data-ttu-id="17a62-107">Emitir tokens</span><span class="sxs-lookup"><span data-stu-id="17a62-107">Issuing Tokens</span></span>  
 <span data-ttu-id="17a62-108">WS-Trust define los formatos de mensaje, basándose en el elemento de esquema del lenguaje de definición de esquemas XML (XSD) `RequestSecurityToken` y en el elemento de esquema XSD `RequestSecurityTokenResponse` para realizar la emisión del token.</span><span class="sxs-lookup"><span data-stu-id="17a62-108">WS-Trust defines message formats, based on the `RequestSecurityToken` XML Schema definition language (XSD) schema element, and `RequestSecurityTokenResponse` XSD schema element for performing token issuance.</span></span> <span data-ttu-id="17a62-109">Además, define los URI (Uniform Resource Identifier) de acción.</span><span class="sxs-lookup"><span data-stu-id="17a62-109">In addition, it defines the associated Action Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="17a62-110">El URI de acción asociado al `RequestSecurityToken` mensaje es `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue` .</span><span class="sxs-lookup"><span data-stu-id="17a62-110">The action URI associated with the `RequestSecurityToken` message is `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`.</span></span> <span data-ttu-id="17a62-111">El URI de acción asociado al `RequestSecurityTokenResponse` mensaje es `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue` .</span><span class="sxs-lookup"><span data-stu-id="17a62-111">The action URI associated with the `RequestSecurityTokenResponse` message is   `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`.</span></span>  
  
### <a name="request-message-structure"></a><span data-ttu-id="17a62-112">Estructura de mensaje de solicitud</span><span class="sxs-lookup"><span data-stu-id="17a62-112">Request Message Structure</span></span>  
 <span data-ttu-id="17a62-113">La estructura del mensaje de solicitud de problema está normalmente compuesta de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="17a62-113">The issue request message structure typically consists of the following items:</span></span>  
  
- <span data-ttu-id="17a62-114">Un URI del tipo de solicitud con un valor de `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue` .</span><span class="sxs-lookup"><span data-stu-id="17a62-114">A request type URI with a value of `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue`.</span></span>
  
- <span data-ttu-id="17a62-115">Un URI del tipo de token.</span><span class="sxs-lookup"><span data-stu-id="17a62-115">A token type URI.</span></span> <span data-ttu-id="17a62-116">En el caso de tokens de lenguaje de marcado de aserciones de seguridad (SAML) 1,1, el valor de este URI es `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1` .</span><span class="sxs-lookup"><span data-stu-id="17a62-116">For Security Assertions Markup Language (SAML) 1.1 tokens, the value of this URI is `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`.</span></span>  
  
- <span data-ttu-id="17a62-117">Un valor de tamaño clave que indica el número de bits en la clave que se va asociar al token emitido.</span><span class="sxs-lookup"><span data-stu-id="17a62-117">A key size value that indicates the number of bits in the key to be associated with the issued token.</span></span>  
  
- <span data-ttu-id="17a62-118">Un tipo URI clave.</span><span class="sxs-lookup"><span data-stu-id="17a62-118">A key type URI.</span></span> <span data-ttu-id="17a62-119">En el caso de las claves simétricas, el valor de este identificador URI es `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey` .</span><span class="sxs-lookup"><span data-stu-id="17a62-119">For symmetric keys, the value of this URI is `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey`.</span></span>  
  
 <span data-ttu-id="17a62-120">Además, un par de otros elementos podrían estar presentes:</span><span class="sxs-lookup"><span data-stu-id="17a62-120">In addition, a couple of other items might be present:</span></span>  
  
- <span data-ttu-id="17a62-121">Material clave proporcionado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="17a62-121">Key material provided by the client.</span></span>  
  
- <span data-ttu-id="17a62-122">Información de ámbito que indica el servicio de destino con el que se utilizará el token emitido.</span><span class="sxs-lookup"><span data-stu-id="17a62-122">Scope information that indicates the target service that the issued token will be used with.</span></span>  
  
 <span data-ttu-id="17a62-123">El servicio de token de seguridad utiliza la información en el mensaje de solicitud del problema cuando construye el mensaje de respuesta del problema.</span><span class="sxs-lookup"><span data-stu-id="17a62-123">The security token service uses the information in the issue request message when it constructs the Issue Response message.</span></span>  
  
## <a name="response-message-structure"></a><span data-ttu-id="17a62-124">Estructura del mensaje de respuesta</span><span class="sxs-lookup"><span data-stu-id="17a62-124">Response Message Structure</span></span>  
 <span data-ttu-id="17a62-125">La estructura del mensaje de respuesta del problema está normalmente compuesta de los elementos siguientes;</span><span class="sxs-lookup"><span data-stu-id="17a62-125">The issue response message structure typically consists of the following items;</span></span>  
  
- <span data-ttu-id="17a62-126">El token de seguridad emitido, por ejemplo, una aserción SAML 1.1.</span><span class="sxs-lookup"><span data-stu-id="17a62-126">The issued security token, for example, a SAML 1.1 assertion.</span></span>  
  
- <span data-ttu-id="17a62-127">Un token de prueba asociado al token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="17a62-127">A proof token associated with the security token.</span></span> <span data-ttu-id="17a62-128">Para las claves simétricas, éste es a menudo una forma cifrada del material clave.</span><span class="sxs-lookup"><span data-stu-id="17a62-128">For symmetric keys, this is often an encrypted form of the key material.</span></span>  
  
- <span data-ttu-id="17a62-129">Hace referencia al token de seguridad emitido.</span><span class="sxs-lookup"><span data-stu-id="17a62-129">References to the issued security token.</span></span> <span data-ttu-id="17a62-130">Normalmente, el servicio del token de seguridad devuelve una referencia que se puede utilizar cuando el token emitido aparece en un mensaje subsiguiente enviado por el cliente y otro que se puede utilizar cuando el token no se encuentra presente en mensajes subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="17a62-130">Typically, the security token service returns a reference that can be used when the issued token appears in a subsequent message sent by the client and another that can be used when the token is not present in subsequent messages.</span></span>  
  
 <span data-ttu-id="17a62-131">Además, un par de otros elementos podrían estar presentes:</span><span class="sxs-lookup"><span data-stu-id="17a62-131">In addition, a couple of other items might be present:</span></span>  
  
- <span data-ttu-id="17a62-132">Material clave proporcionado por el servicio del token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="17a62-132">Key material provided by the security token service.</span></span>  
  
- <span data-ttu-id="17a62-133">El algoritmo necesario para calcular la clave compartida.</span><span class="sxs-lookup"><span data-stu-id="17a62-133">The algorithm needed to compute the shared key.</span></span>  
  
- <span data-ttu-id="17a62-134">Información de duración del token emitido.</span><span class="sxs-lookup"><span data-stu-id="17a62-134">Lifetime information for the issued token.</span></span>  
  
## <a name="processing-request-messages"></a><span data-ttu-id="17a62-135">Procesar los mensajes de solicitud</span><span class="sxs-lookup"><span data-stu-id="17a62-135">Processing Request Messages</span></span>  
 <span data-ttu-id="17a62-136">El servicio del token de seguridad procesa la solicitud del problema examinando las varias partes del mensaje de solicitud y asegurándose de que puede emitir un token que satisfaga la solicitud.</span><span class="sxs-lookup"><span data-stu-id="17a62-136">The security token service processes the issue request by examining the various pieces of the request message and ensuring that it can issue a token that satisfies the request.</span></span> <span data-ttu-id="17a62-137">El servicio del token de seguridad debe determinar lo siguiente antes de construir el token que se va a emitir:</span><span class="sxs-lookup"><span data-stu-id="17a62-137">The security token service must determine the following before it constructs the token to be issued:</span></span>  
  
- <span data-ttu-id="17a62-138">La solicitud realmente es una solicitud para un token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="17a62-138">The request really is a request for a token to be issued.</span></span>  
  
- <span data-ttu-id="17a62-139">El servicio del token de seguridad soporta el tipo de token solicitado.</span><span class="sxs-lookup"><span data-stu-id="17a62-139">The security token service supports the requested token type.</span></span>  
  
- <span data-ttu-id="17a62-140">El solicitante está autorizado para realizar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="17a62-140">The requester is authorized to make the request.</span></span>  
  
- <span data-ttu-id="17a62-141">El servicio del token de seguridad puede satisfacer las expectativas del solicitante con respecto al material clave.</span><span class="sxs-lookup"><span data-stu-id="17a62-141">The security token service can meet the requester's expectations with respect to key material.</span></span>  
  
 <span data-ttu-id="17a62-142">Dos partes vitales de la construcción de un token determinan con qué clave se firmará el token y con qué clave se cifrará la clave compartida.</span><span class="sxs-lookup"><span data-stu-id="17a62-142">Two vital parts of constructing a token are determining what key to sign the token with and what key to encrypt the shared key with.</span></span> <span data-ttu-id="17a62-143">El token debe ser firmado para que cuando el cliente presenta el token al servicio de destino, ese servicio pueda determinar que el token fue emitido por un servicio del token de seguridad en el que confía.</span><span class="sxs-lookup"><span data-stu-id="17a62-143">The token needs to be signed so that when the client presents the token to the target service, that service can determine that the token was issued by a security token service that it trusts.</span></span> <span data-ttu-id="17a62-144">El material clave debe cifrarse de manera que el servicio de destino pueda descifrar ese material de clave.</span><span class="sxs-lookup"><span data-stu-id="17a62-144">The key material needs to be encrypted in such a way that the target service can decrypt that key material.</span></span>  
  
 <span data-ttu-id="17a62-145">La firma de una aserción SAML implica la creación de una instancia <xref:System.IdentityModel.Tokens.SigningCredentials>.</span><span class="sxs-lookup"><span data-stu-id="17a62-145">Signing a SAML assertion involves creating a <xref:System.IdentityModel.Tokens.SigningCredentials> instance.</span></span> <span data-ttu-id="17a62-146">El constructor para esta clase toma lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="17a62-146">The constructor for this class takes the following:</span></span>  
  
- <span data-ttu-id="17a62-147"><xref:System.IdentityModel.Tokens.SecurityKey> para que la clave lo utilice para firmar la aserción SAML.</span><span class="sxs-lookup"><span data-stu-id="17a62-147">A <xref:System.IdentityModel.Tokens.SecurityKey> for the key to use to sign the SAML assertion.</span></span>  
  
- <span data-ttu-id="17a62-148">Una cadena que identifica el algoritmo de firma a utilizar.</span><span class="sxs-lookup"><span data-stu-id="17a62-148">A string identifying the signature algorithm to use.</span></span>  
  
- <span data-ttu-id="17a62-149">Una cadena que identifica el algoritmo de resumen a utilizar.</span><span class="sxs-lookup"><span data-stu-id="17a62-149">A string identifying the digest algorithm to use.</span></span>  
  
- <span data-ttu-id="17a62-150">Opcionalmente, <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> que identifica la clave a utilizar para firmar la aserción.</span><span class="sxs-lookup"><span data-stu-id="17a62-150">Optionally, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> that identifies the key to use to sign the assertion.</span></span>  
  
 [!code-csharp[c_CreateSTS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#1)]
 [!code-vb[c_CreateSTS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#1)]  
  
 <span data-ttu-id="17a62-151">El cifrado de la clave compartida implica tomar el material clave y cifrarlo con una clave que el servicio de destino pueda utilizar para descifrar la clave compartida.</span><span class="sxs-lookup"><span data-stu-id="17a62-151">Encrypting the shared key involves taking the key material and encrypting it with a key that the target service can use to decrypt the shared key.</span></span> <span data-ttu-id="17a62-152">Normalmente, se utiliza la clave pública del servicio de destino.</span><span class="sxs-lookup"><span data-stu-id="17a62-152">Typically, the public key of the target service is used.</span></span>  
  
 [!code-csharp[c_CreateSTS#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#2)]
 [!code-vb[c_CreateSTS#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#2)]  
  
 <span data-ttu-id="17a62-153">Además, se necesita <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> para la clave cifrada.</span><span class="sxs-lookup"><span data-stu-id="17a62-153">In addition, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> for the encrypted key is needed.</span></span>  
  
 [!code-csharp[c_CreateSTS#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#3)]
 [!code-vb[c_CreateSTS#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#3)]  
  
 <span data-ttu-id="17a62-154"><xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> se utiliza a continuación para crear un `SamlSubject` como parte del `SamlToken`.</span><span class="sxs-lookup"><span data-stu-id="17a62-154">This <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> is then used to create a `SamlSubject` as part of the `SamlToken`.</span></span>  
  
 [!code-csharp[c_CreateSTS#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#4)]
 [!code-vb[c_CreateSTS#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#4)]  
  
 <span data-ttu-id="17a62-155">Para obtener más información, vea [ejemplo de Federación](../samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="17a62-155">For more information, see [Federation Sample](../samples/federation-sample.md).</span></span>  
  
## <a name="creating-response-messages"></a><span data-ttu-id="17a62-156">Crear los mensajes de respuesta</span><span class="sxs-lookup"><span data-stu-id="17a62-156">Creating Response Messages</span></span>  
 <span data-ttu-id="17a62-157">Cuando el servicio de token de seguridad procesa la solicitud del problema y construye el token que se va a emitir junto con la clave de prueba, el mensaje de respuesta necesita ser construido, incluyendo como mínimo el token solicitado, el token de prueba y las referencias del token emitido.</span><span class="sxs-lookup"><span data-stu-id="17a62-157">Once the security token service processes the issue request and constructs the token to be issued along with the proof key, the response message needs to be constructed, including at least the requested token, the proof token, and the issued token references.</span></span> <span data-ttu-id="17a62-158">El token emitido es normalmente <xref:System.IdentityModel.Tokens.SamlSecurityToken> creado a partir de <xref:System.IdentityModel.Tokens.SamlAssertion>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="17a62-158">The issued token is typically a <xref:System.IdentityModel.Tokens.SamlSecurityToken> created from the <xref:System.IdentityModel.Tokens.SamlAssertion>, as shown in the following example.</span></span>  
  
 [!code-csharp[c_CreateSTS#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#5)]
 [!code-vb[c_CreateSTS#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#5)]  
  
 <span data-ttu-id="17a62-159">En el caso donde el servicio del token de seguridad proporciona el material de la clave compartida, el token de prueba se construye creando <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="17a62-159">In the case where the security token service provides the shared key material, the proof token is constructed by creating a <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span></span>  
  
 [!code-csharp[c_CreateSTS#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#6)]
 [!code-vb[c_CreateSTS#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#6)]  
  
 <span data-ttu-id="17a62-160">Para obtener más información sobre cómo construir el token de prueba cuando el cliente y el servicio de token de seguridad proporcionan el material de clave para la clave compartida, vea [ejemplo de Federación](../samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="17a62-160">For more information about how to construct the proof token when the client and the security token service both provide key material for the shared key, see [Federation Sample](../samples/federation-sample.md).</span></span>  
  
 <span data-ttu-id="17a62-161">Las referencias del token emitido se construyen creando instancias de la clase <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>.</span><span class="sxs-lookup"><span data-stu-id="17a62-161">The issued token references are constructed by creating instances of the <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> class.</span></span>  
  
 [!code-csharp[c_CreateSTS#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#7)]
 [!code-vb[c_CreateSTS#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#7)]  
  
 <span data-ttu-id="17a62-162">Estos valores diferentes se serializan a continuación en el mensaje de respuesta devuelto al cliente.</span><span class="sxs-lookup"><span data-stu-id="17a62-162">These various values are then serialized into the response message returned to the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17a62-163">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17a62-163">Example</span></span>  
 <span data-ttu-id="17a62-164">Para ver el código completo de un servicio de token de seguridad, vea [ejemplo de Federación](../samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="17a62-164">For full code for a security token service, see [Federation Sample](../samples/federation-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17a62-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="17a62-165">See also</span></span>

- <xref:System.IdentityModel.Tokens.SigningCredentials>
- <xref:System.IdentityModel.Tokens.SecurityKey>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>
- <xref:System.IdentityModel.Tokens.SamlSecurityToken>
- <xref:System.IdentityModel.Tokens.SamlAssertion>
- <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>
- [<span data-ttu-id="17a62-166">Ejemplo de federación</span><span class="sxs-lookup"><span data-stu-id="17a62-166">Federation Sample</span></span>](../samples/federation-sample.md)
