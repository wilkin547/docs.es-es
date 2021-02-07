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
# <a name="how-to-create-a-security-token-service"></a><span data-ttu-id="9a373-103">Procedimiento para crear un servicio de token de seguridad</span><span class="sxs-lookup"><span data-stu-id="9a373-103">How to: Create a Security Token Service</span></span>

<span data-ttu-id="9a373-104">Un servicio de token de seguridad implementa el protocolo definido en la especificación de WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="9a373-104">A security token service implements the protocol defined in the WS-Trust specification.</span></span> <span data-ttu-id="9a373-105">Este protocolo define formatos de mensaje y patrones de intercambio de mensajes para emitir, renovar, cancelar y validar tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9a373-105">This protocol defines message formats and message exchange patterns for issuing, renewing, canceling, and validating security tokens.</span></span> <span data-ttu-id="9a373-106">Un servicio de token de seguridad determinado proporciona uno o más de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="9a373-106">A given security token service provides one or more of these capabilities.</span></span> <span data-ttu-id="9a373-107">Este tema aborda el escenario común: implementación de la emisión de token.</span><span class="sxs-lookup"><span data-stu-id="9a373-107">This topic looks at the most common scenario: implementing token issuance.</span></span>  
  
## <a name="issuing-tokens"></a><span data-ttu-id="9a373-108">Emitir tokens</span><span class="sxs-lookup"><span data-stu-id="9a373-108">Issuing Tokens</span></span>  

 <span data-ttu-id="9a373-109">WS-Trust define los formatos de mensaje, basándose en el elemento de esquema del lenguaje de definición de esquemas XML (XSD) `RequestSecurityToken` y en el elemento de esquema XSD `RequestSecurityTokenResponse` para realizar la emisión del token.</span><span class="sxs-lookup"><span data-stu-id="9a373-109">WS-Trust defines message formats, based on the `RequestSecurityToken` XML Schema definition language (XSD) schema element, and `RequestSecurityTokenResponse` XSD schema element for performing token issuance.</span></span> <span data-ttu-id="9a373-110">Además, define los URI (Uniform Resource Identifier) de acción.</span><span class="sxs-lookup"><span data-stu-id="9a373-110">In addition, it defines the associated Action Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="9a373-111">El URI de acción asociado al `RequestSecurityToken` mensaje es `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue` .</span><span class="sxs-lookup"><span data-stu-id="9a373-111">The action URI associated with the `RequestSecurityToken` message is `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`.</span></span> <span data-ttu-id="9a373-112">El URI de acción asociado al `RequestSecurityTokenResponse` mensaje es   `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue` .</span><span class="sxs-lookup"><span data-stu-id="9a373-112">The action URI associated with the `RequestSecurityTokenResponse` message is   `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`.</span></span>  
  
### <a name="request-message-structure"></a><span data-ttu-id="9a373-113">Estructura de mensaje de solicitud</span><span class="sxs-lookup"><span data-stu-id="9a373-113">Request Message Structure</span></span>  

 <span data-ttu-id="9a373-114">La estructura del mensaje de solicitud de problema está normalmente compuesta de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a373-114">The issue request message structure typically consists of the following items:</span></span>  
  
- <span data-ttu-id="9a373-115">Un URI del tipo de solicitud con un valor de `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue` .</span><span class="sxs-lookup"><span data-stu-id="9a373-115">A request type URI with a value of `http://schemas.xmlsoap.org/ws/2005/02/trust/Issue`.</span></span>
  
- <span data-ttu-id="9a373-116">Un URI del tipo de token.</span><span class="sxs-lookup"><span data-stu-id="9a373-116">A token type URI.</span></span> <span data-ttu-id="9a373-117">En el caso de tokens de lenguaje de marcado de aserciones de seguridad (SAML) 1,1, el valor de este URI es `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1` .</span><span class="sxs-lookup"><span data-stu-id="9a373-117">For Security Assertions Markup Language (SAML) 1.1 tokens, the value of this URI is `http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1`.</span></span>  
  
- <span data-ttu-id="9a373-118">Un valor de tamaño clave que indica el número de bits en la clave que se va asociar al token emitido.</span><span class="sxs-lookup"><span data-stu-id="9a373-118">A key size value that indicates the number of bits in the key to be associated with the issued token.</span></span>  
  
- <span data-ttu-id="9a373-119">Un tipo URI clave.</span><span class="sxs-lookup"><span data-stu-id="9a373-119">A key type URI.</span></span> <span data-ttu-id="9a373-120">En el caso de las claves simétricas, el valor de este identificador URI es `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey` .</span><span class="sxs-lookup"><span data-stu-id="9a373-120">For symmetric keys, the value of this URI is `http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey`.</span></span>  
  
 <span data-ttu-id="9a373-121">Además, un par de otros elementos podrían estar presentes:</span><span class="sxs-lookup"><span data-stu-id="9a373-121">In addition, a couple of other items might be present:</span></span>  
  
- <span data-ttu-id="9a373-122">Material clave proporcionado por el cliente.</span><span class="sxs-lookup"><span data-stu-id="9a373-122">Key material provided by the client.</span></span>  
  
- <span data-ttu-id="9a373-123">Información de ámbito que indica el servicio de destino con el que se utilizará el token emitido.</span><span class="sxs-lookup"><span data-stu-id="9a373-123">Scope information that indicates the target service that the issued token will be used with.</span></span>  
  
 <span data-ttu-id="9a373-124">El servicio de token de seguridad utiliza la información en el mensaje de solicitud del problema cuando construye el mensaje de respuesta del problema.</span><span class="sxs-lookup"><span data-stu-id="9a373-124">The security token service uses the information in the issue request message when it constructs the Issue Response message.</span></span>  
  
## <a name="response-message-structure"></a><span data-ttu-id="9a373-125">Estructura del mensaje de respuesta</span><span class="sxs-lookup"><span data-stu-id="9a373-125">Response Message Structure</span></span>  

 <span data-ttu-id="9a373-126">La estructura del mensaje de respuesta del problema está normalmente compuesta de los elementos siguientes;</span><span class="sxs-lookup"><span data-stu-id="9a373-126">The issue response message structure typically consists of the following items;</span></span>  
  
- <span data-ttu-id="9a373-127">El token de seguridad emitido, por ejemplo, una aserción SAML 1.1.</span><span class="sxs-lookup"><span data-stu-id="9a373-127">The issued security token, for example, a SAML 1.1 assertion.</span></span>  
  
- <span data-ttu-id="9a373-128">Un token de prueba asociado al token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9a373-128">A proof token associated with the security token.</span></span> <span data-ttu-id="9a373-129">Para las claves simétricas, éste es a menudo una forma cifrada del material clave.</span><span class="sxs-lookup"><span data-stu-id="9a373-129">For symmetric keys, this is often an encrypted form of the key material.</span></span>  
  
- <span data-ttu-id="9a373-130">Hace referencia al token de seguridad emitido.</span><span class="sxs-lookup"><span data-stu-id="9a373-130">References to the issued security token.</span></span> <span data-ttu-id="9a373-131">Normalmente, el servicio del token de seguridad devuelve una referencia que se puede utilizar cuando el token emitido aparece en un mensaje subsiguiente enviado por el cliente y otro que se puede utilizar cuando el token no se encuentra presente en mensajes subsiguientes.</span><span class="sxs-lookup"><span data-stu-id="9a373-131">Typically, the security token service returns a reference that can be used when the issued token appears in a subsequent message sent by the client and another that can be used when the token is not present in subsequent messages.</span></span>  
  
 <span data-ttu-id="9a373-132">Además, un par de otros elementos podrían estar presentes:</span><span class="sxs-lookup"><span data-stu-id="9a373-132">In addition, a couple of other items might be present:</span></span>  
  
- <span data-ttu-id="9a373-133">Material clave proporcionado por el servicio del token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="9a373-133">Key material provided by the security token service.</span></span>  
  
- <span data-ttu-id="9a373-134">El algoritmo necesario para calcular la clave compartida.</span><span class="sxs-lookup"><span data-stu-id="9a373-134">The algorithm needed to compute the shared key.</span></span>  
  
- <span data-ttu-id="9a373-135">Información de duración del token emitido.</span><span class="sxs-lookup"><span data-stu-id="9a373-135">Lifetime information for the issued token.</span></span>  
  
## <a name="processing-request-messages"></a><span data-ttu-id="9a373-136">Procesar los mensajes de solicitud</span><span class="sxs-lookup"><span data-stu-id="9a373-136">Processing Request Messages</span></span>  

 <span data-ttu-id="9a373-137">El servicio del token de seguridad procesa la solicitud del problema examinando las varias partes del mensaje de solicitud y asegurándose de que puede emitir un token que satisfaga la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9a373-137">The security token service processes the issue request by examining the various pieces of the request message and ensuring that it can issue a token that satisfies the request.</span></span> <span data-ttu-id="9a373-138">El servicio del token de seguridad debe determinar lo siguiente antes de construir el token que se va a emitir:</span><span class="sxs-lookup"><span data-stu-id="9a373-138">The security token service must determine the following before it constructs the token to be issued:</span></span>  
  
- <span data-ttu-id="9a373-139">La solicitud realmente es una solicitud para un token que se va a emitir.</span><span class="sxs-lookup"><span data-stu-id="9a373-139">The request really is a request for a token to be issued.</span></span>  
  
- <span data-ttu-id="9a373-140">El servicio del token de seguridad soporta el tipo de token solicitado.</span><span class="sxs-lookup"><span data-stu-id="9a373-140">The security token service supports the requested token type.</span></span>  
  
- <span data-ttu-id="9a373-141">El solicitante está autorizado para realizar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9a373-141">The requester is authorized to make the request.</span></span>  
  
- <span data-ttu-id="9a373-142">El servicio del token de seguridad puede satisfacer las expectativas del solicitante con respecto al material clave.</span><span class="sxs-lookup"><span data-stu-id="9a373-142">The security token service can meet the requester's expectations with respect to key material.</span></span>  
  
 <span data-ttu-id="9a373-143">Dos partes vitales de la construcción de un token determinan con qué clave se firmará el token y con qué clave se cifrará la clave compartida.</span><span class="sxs-lookup"><span data-stu-id="9a373-143">Two vital parts of constructing a token are determining what key to sign the token with and what key to encrypt the shared key with.</span></span> <span data-ttu-id="9a373-144">El token debe ser firmado para que cuando el cliente presenta el token al servicio de destino, ese servicio pueda determinar que el token fue emitido por un servicio del token de seguridad en el que confía.</span><span class="sxs-lookup"><span data-stu-id="9a373-144">The token needs to be signed so that when the client presents the token to the target service, that service can determine that the token was issued by a security token service that it trusts.</span></span> <span data-ttu-id="9a373-145">El material clave debe cifrarse de manera que el servicio de destino pueda descifrar ese material de clave.</span><span class="sxs-lookup"><span data-stu-id="9a373-145">The key material needs to be encrypted in such a way that the target service can decrypt that key material.</span></span>  
  
 <span data-ttu-id="9a373-146">La firma de una aserción SAML implica la creación de una instancia <xref:System.IdentityModel.Tokens.SigningCredentials>.</span><span class="sxs-lookup"><span data-stu-id="9a373-146">Signing a SAML assertion involves creating a <xref:System.IdentityModel.Tokens.SigningCredentials> instance.</span></span> <span data-ttu-id="9a373-147">El constructor para esta clase toma lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a373-147">The constructor for this class takes the following:</span></span>  
  
- <span data-ttu-id="9a373-148"><xref:System.IdentityModel.Tokens.SecurityKey> para que la clave lo utilice para firmar la aserción SAML.</span><span class="sxs-lookup"><span data-stu-id="9a373-148">A <xref:System.IdentityModel.Tokens.SecurityKey> for the key to use to sign the SAML assertion.</span></span>  
  
- <span data-ttu-id="9a373-149">Una cadena que identifica el algoritmo de firma a utilizar.</span><span class="sxs-lookup"><span data-stu-id="9a373-149">A string identifying the signature algorithm to use.</span></span>  
  
- <span data-ttu-id="9a373-150">Una cadena que identifica el algoritmo de resumen a utilizar.</span><span class="sxs-lookup"><span data-stu-id="9a373-150">A string identifying the digest algorithm to use.</span></span>  
  
- <span data-ttu-id="9a373-151">Opcionalmente, <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> que identifica la clave a utilizar para firmar la aserción.</span><span class="sxs-lookup"><span data-stu-id="9a373-151">Optionally, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> that identifies the key to use to sign the assertion.</span></span>  
  
 [!code-csharp[c_CreateSTS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#1)]
 [!code-vb[c_CreateSTS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#1)]  
  
 <span data-ttu-id="9a373-152">El cifrado de la clave compartida implica tomar el material clave y cifrarlo con una clave que el servicio de destino pueda utilizar para descifrar la clave compartida.</span><span class="sxs-lookup"><span data-stu-id="9a373-152">Encrypting the shared key involves taking the key material and encrypting it with a key that the target service can use to decrypt the shared key.</span></span> <span data-ttu-id="9a373-153">Normalmente, se utiliza la clave pública del servicio de destino.</span><span class="sxs-lookup"><span data-stu-id="9a373-153">Typically, the public key of the target service is used.</span></span>  
  
 [!code-csharp[c_CreateSTS#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#2)]
 [!code-vb[c_CreateSTS#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#2)]  
  
 <span data-ttu-id="9a373-154">Además, se necesita <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> para la clave cifrada.</span><span class="sxs-lookup"><span data-stu-id="9a373-154">In addition, a <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> for the encrypted key is needed.</span></span>  
  
 [!code-csharp[c_CreateSTS#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#3)]
 [!code-vb[c_CreateSTS#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#3)]  
  
 <span data-ttu-id="9a373-155"><xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> se utiliza a continuación para crear un `SamlSubject` como parte del `SamlToken`.</span><span class="sxs-lookup"><span data-stu-id="9a373-155">This <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> is then used to create a `SamlSubject` as part of the `SamlToken`.</span></span>  
  
 [!code-csharp[c_CreateSTS#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#4)]
 [!code-vb[c_CreateSTS#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#4)]  
  
 <span data-ttu-id="9a373-156">Para obtener más información, vea [ejemplo de Federación](../samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="9a373-156">For more information, see [Federation Sample](../samples/federation-sample.md).</span></span>  
  
## <a name="creating-response-messages"></a><span data-ttu-id="9a373-157">Crear los mensajes de respuesta</span><span class="sxs-lookup"><span data-stu-id="9a373-157">Creating Response Messages</span></span>  

 <span data-ttu-id="9a373-158">Cuando el servicio de token de seguridad procesa la solicitud del problema y construye el token que se va a emitir junto con la clave de prueba, el mensaje de respuesta necesita ser construido, incluyendo como mínimo el token solicitado, el token de prueba y las referencias del token emitido.</span><span class="sxs-lookup"><span data-stu-id="9a373-158">Once the security token service processes the issue request and constructs the token to be issued along with the proof key, the response message needs to be constructed, including at least the requested token, the proof token, and the issued token references.</span></span> <span data-ttu-id="9a373-159">El token emitido es normalmente <xref:System.IdentityModel.Tokens.SamlSecurityToken> creado a partir de <xref:System.IdentityModel.Tokens.SamlAssertion>, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9a373-159">The issued token is typically a <xref:System.IdentityModel.Tokens.SamlSecurityToken> created from the <xref:System.IdentityModel.Tokens.SamlAssertion>, as shown in the following example.</span></span>  
  
 [!code-csharp[c_CreateSTS#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#5)]
 [!code-vb[c_CreateSTS#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#5)]  
  
 <span data-ttu-id="9a373-160">En el caso donde el servicio del token de seguridad proporciona el material de la clave compartida, el token de prueba se construye creando <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="9a373-160">In the case where the security token service provides the shared key material, the proof token is constructed by creating a <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>.</span></span>  
  
 [!code-csharp[c_CreateSTS#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#6)]
 [!code-vb[c_CreateSTS#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#6)]  
  
 <span data-ttu-id="9a373-161">Para obtener más información sobre cómo construir el token de prueba cuando el cliente y el servicio de token de seguridad proporcionan el material de clave para la clave compartida, vea [ejemplo de Federación](../samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="9a373-161">For more information about how to construct the proof token when the client and the security token service both provide key material for the shared key, see [Federation Sample](../samples/federation-sample.md).</span></span>  
  
 <span data-ttu-id="9a373-162">Las referencias del token emitido se construyen creando instancias de la clase <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>.</span><span class="sxs-lookup"><span data-stu-id="9a373-162">The issued token references are constructed by creating instances of the <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause> class.</span></span>  
  
 [!code-csharp[c_CreateSTS#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#7)]
 [!code-vb[c_CreateSTS#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#7)]  
  
 <span data-ttu-id="9a373-163">Estos valores diferentes se serializan a continuación en el mensaje de respuesta devuelto al cliente.</span><span class="sxs-lookup"><span data-stu-id="9a373-163">These various values are then serialized into the response message returned to the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a373-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a373-164">Example</span></span>  

 <span data-ttu-id="9a373-165">Para ver el código completo de un servicio de token de seguridad, vea [ejemplo de Federación](../samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="9a373-165">For full code for a security token service, see [Federation Sample](../samples/federation-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a373-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a373-166">See also</span></span>

- <xref:System.IdentityModel.Tokens.SigningCredentials>
- <xref:System.IdentityModel.Tokens.SecurityKey>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>
- <xref:System.IdentityModel.Tokens.SamlSecurityToken>
- <xref:System.IdentityModel.Tokens.SamlAssertion>
- <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>
- <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>
- [<span data-ttu-id="9a373-167">Ejemplo de federación</span><span class="sxs-lookup"><span data-stu-id="9a373-167">Federation Sample</span></span>](../samples/federation-sample.md)
