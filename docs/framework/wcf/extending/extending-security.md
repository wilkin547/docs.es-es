---
description: Más información acerca de cómo ampliar la seguridad
title: Extensión de la seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 8dd514e16106ac5cdae072d92c7de66cefd39fe4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685730"
---
# <a name="extending-security"></a><span data-ttu-id="32b1d-103">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="32b1d-103">Extending Security</span></span>

<span data-ttu-id="32b1d-104">Para dar cabida a nuevos tipos de notificaciones y tokens personalizados, puede extender la infraestructura de seguridad de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="32b1d-104">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="32b1d-105">Los temas de esta sección le muestran cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="32b1d-105">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32b1d-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="32b1d-106">In This Section</span></span>  
  
 [<span data-ttu-id="32b1d-107">Credencial personalizada y validación de la credencial</span><span class="sxs-lookup"><span data-stu-id="32b1d-107">Custom Credential and Credential Validation</span></span>](custom-credential-and-credential-validation.md)  
 <span data-ttu-id="32b1d-108">Explica cómo se utiliza el modelo de identidad al validar las credenciales personalizadas.</span><span class="sxs-lookup"><span data-stu-id="32b1d-108">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="32b1d-109">Tokens personalizados</span><span class="sxs-lookup"><span data-stu-id="32b1d-109">Custom Tokens</span></span>](custom-tokens.md)  
 <span data-ttu-id="32b1d-110">Los tokens emitidos por un servicio de token de seguridad (STS) normalmente son tokens de SAML.</span><span class="sxs-lookup"><span data-stu-id="32b1d-110">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="32b1d-111">En este tema se explica cómo crear un tipo de token personalizado.</span><span class="sxs-lookup"><span data-stu-id="32b1d-111">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="32b1d-112">Autorización personalizada</span><span class="sxs-lookup"><span data-stu-id="32b1d-112">Custom Authorization</span></span>](custom-authorization.md)  
 <span data-ttu-id="32b1d-113">Explica cómo implementar la autorización personalizada.</span><span class="sxs-lookup"><span data-stu-id="32b1d-113">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="32b1d-114">Invalidación de la identidad de un servicio para la autenticación</span><span class="sxs-lookup"><span data-stu-id="32b1d-114">Overriding the Identity of a Service for Authentication</span></span>](overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="32b1d-115">Describe cómo invalidar la identidad de un servicio para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="32b1d-115">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="32b1d-116">Procedimiento para crear un comprobador de identidad de cliente personalizado</span><span class="sxs-lookup"><span data-stu-id="32b1d-116">How to: Create a Custom Client Identity Verifier</span></span>](how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="32b1d-117">Muestra cómo validar una identidad del extremo personalizada.</span><span class="sxs-lookup"><span data-stu-id="32b1d-117">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="32b1d-118">Procedimiento para usar diferentes certificados X.509 para la firma y el cifrado</span><span class="sxs-lookup"><span data-stu-id="32b1d-118">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="32b1d-119">Los mensajes normalmente se firman y cifran con un certificado único.</span><span class="sxs-lookup"><span data-stu-id="32b1d-119">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="32b1d-120">En este tema se explica cómo se pueden utilizar dos certificados, cuando se requiere.</span><span class="sxs-lookup"><span data-stu-id="32b1d-120">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="32b1d-121">Procedimiento para cambiar el proveedor criptográfico para la clave privada de un certificado X.509</span><span class="sxs-lookup"><span data-stu-id="32b1d-121">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="32b1d-122">Explica cómo cambiar el proveedor de servicios criptográficos que se usa para proporcionar la clave privada de un certificado X. 509 y cómo integrar el proveedor en el marco de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="32b1d-122">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="32b1d-123">Referencia</span><span class="sxs-lookup"><span data-stu-id="32b1d-123">Reference</span></span>  

 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="32b1d-124">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="32b1d-124">Related Sections</span></span>  

 [<span data-ttu-id="32b1d-125">Seguridad</span><span class="sxs-lookup"><span data-stu-id="32b1d-125">Security</span></span>](../feature-details/security.md)  
  
 [<span data-ttu-id="32b1d-126">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="32b1d-126">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="32b1d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="32b1d-127">See also</span></span>

- [<span data-ttu-id="32b1d-128">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="32b1d-128">Security Overview</span></span>](../feature-details/security-overview.md)
