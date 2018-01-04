---
title: Tokens y notificaciones SAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
- issued tokens
- SAML token
ms.assetid: 930b6e34-9eab-4e95-826c-4e06659bb977
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2b35ba4da503663a2bb92597ed193c408e7c99b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="saml-tokens-and-claims"></a><span data-ttu-id="1261e-102">Tokens y notificaciones SAML</span><span class="sxs-lookup"><span data-stu-id="1261e-102">SAML Tokens and Claims</span></span>
<span data-ttu-id="1261e-103">Lenguaje de marcado de aserciones de seguridad (SAML) *tokens* son representaciones XML de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="1261e-103">Security Assertions Markup Language (SAML) *tokens* are XML representations of claims.</span></span> <span data-ttu-id="1261e-104">De forma predeterminada, los tokens SAML [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] usos en escenarios de seguridad federada son *tokens emitidos*.</span><span class="sxs-lookup"><span data-stu-id="1261e-104">By default, SAML tokens [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses in federated security scenarios are *issued tokens*.</span></span>  
  
 <span data-ttu-id="1261e-105">Los tokens SAML llevan instrucciones que son conjuntos de notificaciones realizadas por una entidad sobre otra entidad.</span><span class="sxs-lookup"><span data-stu-id="1261e-105">SAML tokens carry statements that are sets of claims made by one entity about another entity.</span></span> <span data-ttu-id="1261e-106">Por ejemplo, en escenarios de seguridad asociados, las instrucciones son realizadas por un servicio de token de seguridad sobre un usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="1261e-106">For example, in federated security scenarios, the statements are made by a security token service about a user in the system.</span></span> <span data-ttu-id="1261e-107">El servicio de token de seguridad firma el token SAML para indicar la veracidad de las instrucciones contenidas en el token.</span><span class="sxs-lookup"><span data-stu-id="1261e-107">The security token service signs the SAML token to indicate the veracity of the statements contained in the token.</span></span> <span data-ttu-id="1261e-108">Además, el token SAML está asociado a material clave criptográfico del que el usuario del token SAML demuestra tener conocimiento.</span><span class="sxs-lookup"><span data-stu-id="1261e-108">In addition, the SAML token is associated with cryptographic key material that the user of the SAML token proves knowledge of.</span></span> <span data-ttu-id="1261e-109">Esta prueba convence al usuario de confianza que el token SAML fue realmente emitido para ese usuario.</span><span class="sxs-lookup"><span data-stu-id="1261e-109">This proof satisfies the relying party that the SAML token was, in fact, issued to that user.</span></span> <span data-ttu-id="1261e-110">Por ejemplo, en un escenario típico:</span><span class="sxs-lookup"><span data-stu-id="1261e-110">For example, in a typical scenario:</span></span>  
  
1.  <span data-ttu-id="1261e-111">Un cliente solicita un token de SAML de un servicio de token de seguridad, autenticándose para ese servicio de token de seguridad usando las credenciales de Windows.</span><span class="sxs-lookup"><span data-stu-id="1261e-111">A client requests a SAML token from a security token service, authenticating to that security token service by using Windows credentials.</span></span>  
  
2.  <span data-ttu-id="1261e-112">El servicio de token de seguridad emite un token SAML para el cliente.</span><span class="sxs-lookup"><span data-stu-id="1261e-112">The security token service issues a SAML token to the client.</span></span> <span data-ttu-id="1261e-113">El token SAML se firma con un certificado asociado al servicio de token de seguridad y contiene una clave de prueba cifrada para el servicio de destino.</span><span class="sxs-lookup"><span data-stu-id="1261e-113">The SAML token is signed with a certificate associated with the security token service and contains a proof key encrypted for the target service.</span></span>  
  
3.  <span data-ttu-id="1261e-114">El cliente también recibe una copia de la *clave de prueba*.</span><span class="sxs-lookup"><span data-stu-id="1261e-114">The client also receives a copy of the *proof key*.</span></span> <span data-ttu-id="1261e-115">El cliente presenta el token SAML al servicio de aplicación (el *usuario de confianza*) y firma el mensaje con esa clave de prueba.</span><span class="sxs-lookup"><span data-stu-id="1261e-115">The client then presents the SAML token to the application service (the *relying party*) and signs the message with that proof key.</span></span>  
  
4.  <span data-ttu-id="1261e-116">La firma a través del token SAML indica al usuario de confianza que el servicio de token de seguridad emitió el token.</span><span class="sxs-lookup"><span data-stu-id="1261e-116">The signature over the SAML token tells the relying party that the security token service issued the token.</span></span> <span data-ttu-id="1261e-117">La firma del mensaje creada con la clave de prueba indica al usuario de confianza que el token fue emitido para el cliente.</span><span class="sxs-lookup"><span data-stu-id="1261e-117">The message signature created with the proof key tells the relying party that the token was issued to the client.</span></span>  
  
## <a name="from-claims-to-samlattributes"></a><span data-ttu-id="1261e-118">De notificaciones a SamlAttributes</span><span class="sxs-lookup"><span data-stu-id="1261e-118">From Claims to SamlAttributes</span></span>  
 <span data-ttu-id="1261e-119">En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las instrucciones en tokens SAML se modelan como objetos <xref:System.IdentityModel.Tokens.SamlAttribute>, que se pueden rellenar directamente a partir de los objetos <xref:System.IdentityModel.Claims.Claim>, siempre que el objeto <xref:System.IdentityModel.Claims.Claim> tenga una propiedad <xref:System.IdentityModel.Claims.Claim.Right%2A> de <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> y la propiedad <xref:System.IdentityModel.Claims.Claim.Resource%2A> sea del tipo <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="1261e-119">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], statements in SAML tokens are modeled as <xref:System.IdentityModel.Tokens.SamlAttribute> objects, which can be populated directly from <xref:System.IdentityModel.Claims.Claim> objects, provided the <xref:System.IdentityModel.Claims.Claim> object has a <xref:System.IdentityModel.Claims.Claim.Right%2A> property of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> and the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property is of type <xref:System.String>.</span></span> <span data-ttu-id="1261e-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1261e-120">For example:</span></span>  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
>  <span data-ttu-id="1261e-121">Cuando los tokens SAML se serializan en mensajes, o cuando los emite un servicio de token de seguridad o son presentados por los clientes a servicios como parte de autenticación, la cuota de tamaño máximo del mensaje debe ser suficientemente grande para alojar el token SAML y las otras partes del mensaje.</span><span class="sxs-lookup"><span data-stu-id="1261e-121">When SAML tokens are serialized in messages, either when they are issued by a security token service or when they are presented by clients to services as part of authentication, the maximum message size quota must be sufficiently large to accommodate the SAML token and the other message parts.</span></span> <span data-ttu-id="1261e-122">En casos normales, las cuotas de tamaño del mensaje predeterminadas son suficientes.</span><span class="sxs-lookup"><span data-stu-id="1261e-122">In normal cases, the default message size quotas are sufficient.</span></span> <span data-ttu-id="1261e-123">Sin embargo, en casos donde un token SAML es grande que porque contiene centenares de notificaciones, puede necesitar aumentar las cuotas para alojar el token serializado.</span><span class="sxs-lookup"><span data-stu-id="1261e-123">However, in cases where a SAML token is large because it contains hundreds of claims, you may need to increase the quotas to accommodate the serialized token.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="1261e-124">[Consideraciones de seguridad para datos](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span><span class="sxs-lookup"><span data-stu-id="1261e-124"> [Security Considerations for Data](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span></span>  
  
## <a name="from-samlattributes-to-claims"></a><span data-ttu-id="1261e-125">De SamlAttributes a notificaciones</span><span class="sxs-lookup"><span data-stu-id="1261e-125">From SamlAttributes to Claims</span></span>  
 <span data-ttu-id="1261e-126">Cuando los tokens SAML se reciben en mensajes, las diversas instrucciones en el token SAML se convierten en objetos <xref:System.IdentityModel.Policy.IAuthorizationPolicy> que se colocan en <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="1261e-126">When SAML tokens are received in messages, the various statements in the SAML token are turned into <xref:System.IdentityModel.Policy.IAuthorizationPolicy> objects that are placed into the <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="1261e-127">La propiedad <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> de <xref:System.IdentityModel.Policy.AuthorizationContext> devuelve las notificaciones de cada instrucción SAML y se pueden examinar para determinar si autenticar y autorizar al usuario.</span><span class="sxs-lookup"><span data-stu-id="1261e-127">The claims from each SAML statement are returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> and can be examined to determine whether to authenticate and authorize the user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1261e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="1261e-128">See Also</span></span>  
 <xref:System.IdentityModel.Policy.AuthorizationContext>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 <xref:System.IdentityModel.Claims.ClaimSet>  
 [<span data-ttu-id="1261e-129">Federación</span><span class="sxs-lookup"><span data-stu-id="1261e-129">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 [<span data-ttu-id="1261e-130">Creación de un cliente federado</span><span class="sxs-lookup"><span data-stu-id="1261e-130">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="1261e-131">Configuración de las credenciales en un servicio de federación</span><span class="sxs-lookup"><span data-stu-id="1261e-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="1261e-132">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="1261e-132">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="1261e-133">Notificaciones y tokens</span><span class="sxs-lookup"><span data-stu-id="1261e-133">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)  
 [<span data-ttu-id="1261e-134">Creación de notificaciones y valores de recursos</span><span class="sxs-lookup"><span data-stu-id="1261e-134">Claim Creation and Resource Values</span></span>](../../../../docs/framework/wcf/feature-details/claim-creation-and-resource-values.md)  
 [<span data-ttu-id="1261e-135">Creación de una notificación personalizada</span><span class="sxs-lookup"><span data-stu-id="1261e-135">How to: Create a Custom Claim</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
