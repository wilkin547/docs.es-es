---
title: "Extensión de la seguridad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
caps.latest.revision: "23"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ecbbaac0023ca528967abe2cb60c3d790772fb2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="extending-security"></a><span data-ttu-id="ae739-102">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="ae739-102">Extending Security</span></span>
<span data-ttu-id="ae739-103">Para alojar nuevos tipos de notificación y tokens personalizados, puede extender la infraestructura de seguridad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae739-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="ae739-104">Los temas de esta sección le muestran cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ae739-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ae739-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ae739-105">In This Section</span></span>  
 [<span data-ttu-id="ae739-106">Arquitectura de seguridad</span><span class="sxs-lookup"><span data-stu-id="ae739-106">Security Architecture</span></span>](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)  
 <span data-ttu-id="ae739-107">Describe la arquitectura del sistema de seguridad [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae739-107">Walks through the architecture of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security system.</span></span>  
  
 [<span data-ttu-id="ae739-108">Credencial personalizada y validación de la credencial</span><span class="sxs-lookup"><span data-stu-id="ae739-108">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="ae739-109">Explica cómo se utiliza el modelo de identidad al validar las credenciales personalizadas.</span><span class="sxs-lookup"><span data-stu-id="ae739-109">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="ae739-110">Tokens personalizados</span><span class="sxs-lookup"><span data-stu-id="ae739-110">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="ae739-111">Los tokens emitidos por un servicio de token de seguridad (STS) normalmente son tokens de SAML.</span><span class="sxs-lookup"><span data-stu-id="ae739-111">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="ae739-112">En este tema se explica cómo crear un tipo de token personalizado.</span><span class="sxs-lookup"><span data-stu-id="ae739-112">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="ae739-113">Autorización personalizada</span><span class="sxs-lookup"><span data-stu-id="ae739-113">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="ae739-114">Explica cómo implementar la autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="ae739-114">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="ae739-115">Invalidación de la identidad de un servicio para la autenticación</span><span class="sxs-lookup"><span data-stu-id="ae739-115">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="ae739-116">Describe cómo invalidar la identidad de un servicio para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="ae739-116">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="ae739-117">Creación de un comprobador de identidad de cliente personalizado</span><span class="sxs-lookup"><span data-stu-id="ae739-117">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="ae739-118">Muestra cómo validar una identidad del punto de conexión personalizada.</span><span class="sxs-lookup"><span data-stu-id="ae739-118">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="ae739-119">Uso de diferentes certificados X.509 para la firma y el cifrado</span><span class="sxs-lookup"><span data-stu-id="ae739-119">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="ae739-120">Los mensajes normalmente se firman y cifran con un certificado único.</span><span class="sxs-lookup"><span data-stu-id="ae739-120">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="ae739-121">En este tema se explica cómo se pueden utilizar dos certificados, cuando se requiere.</span><span class="sxs-lookup"><span data-stu-id="ae739-121">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="ae739-122">Cambio de proveedor criptográfico para la clave privada de un certificado X.509</span><span class="sxs-lookup"><span data-stu-id="ae739-122">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="ae739-123">Explica cómo cambiar el proveedor criptográfico utilizado para proporcionar la clave privada de un certificado X.509 y cómo integrar el proveedor en el marco [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae739-123">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ae739-124">Referencia</span><span class="sxs-lookup"><span data-stu-id="ae739-124">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="ae739-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ae739-125">Related Sections</span></span>  
 [<span data-ttu-id="ae739-126">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ae739-126">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="ae739-127">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="ae739-127">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="ae739-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae739-128">See Also</span></span>  
 [<span data-ttu-id="ae739-129">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="ae739-129">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
