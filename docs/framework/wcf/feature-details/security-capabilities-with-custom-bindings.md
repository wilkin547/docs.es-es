---
description: 'Más información sobre: capacidades de seguridad con enlaces personalizados'
title: Capacidades de seguridad con enlaces personalizados
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 0d4298bcb0b22d607c4abb15d879e3b093394bad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779847"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="2ee8c-103">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="2ee8c-103">Security Capabilities with Custom Bindings</span></span>

<span data-ttu-id="2ee8c-104">Puede realizar las tareas de seguridad más habituales utilizando uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-104">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="2ee8c-105">Si necesita más control, sin embargo, puede crear un enlace personalizado con <xref:System.ServiceModel.Channels.SecurityBindingElement>, como se explica en estos temas.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-105">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="2ee8c-106">Para obtener más información sobre los enlaces personalizados, vea [enlaces personalizados](../extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="2ee8c-106">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ee8c-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2ee8c-107">In This Section</span></span>  

 [<span data-ttu-id="2ee8c-108">Modos de autenticación de SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2ee8c-108">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="2ee8c-109">Describe los modos de autenticación que son posibles con un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-109">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="2ee8c-110">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2ee8c-110">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="2ee8c-111">Describe los pasos básicos para crear un enlace personalizado con un elemento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-111">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="2ee8c-112">Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado</span><span class="sxs-lookup"><span data-stu-id="2ee8c-112">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="2ee8c-113">Describe cómo crear un elemento de seguridad para un modo de autenticación especificado.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-113">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="2ee8c-114">Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="2ee8c-114">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="2ee8c-115">Describe cómo deshabilitar las sesiones seguras al crear un servicio de federación.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-115">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="2ee8c-116">Procedimiento para habilitar la detección de repetición de mensajes</span><span class="sxs-lookup"><span data-stu-id="2ee8c-116">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="2ee8c-117">Describe cómo determinar cuándo se produce un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-117">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="2ee8c-118">Procedimiento para crear una credencial de apoyo</span><span class="sxs-lookup"><span data-stu-id="2ee8c-118">How to: Create a Supporting Credential</span></span>](how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="2ee8c-119">Describe cómo proporcionar una credencial de soporte a un servicio, si el servicio lo requiere.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-119">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="2ee8c-120">Procedimiento para establecer una confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="2ee8c-120">How to: Set Up a Signature Confirmation</span></span>](how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="2ee8c-121">Describe los pasos para confirmar las firmas al firmar digitalmente los mensajes.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-121">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="2ee8c-122">Procedimiento para establecer un sesgo de reloj máximo</span><span class="sxs-lookup"><span data-stu-id="2ee8c-122">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="2ee8c-123">Describe cómo establecer la diferencia horaria máxima permitida entre un servicio y un cliente.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-123">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="2ee8c-124">Procedimiento para deshabilitar el cifrado de firmas digitales</span><span class="sxs-lookup"><span data-stu-id="2ee8c-124">How to: Disable Encryption of Digital Signatures</span></span>](how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="2ee8c-125">Describe cómo deshabilitar el cifrado de firmas digitales puede suponer una ventaja de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="2ee8c-125">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2ee8c-126">Referencia</span><span class="sxs-lookup"><span data-stu-id="2ee8c-126">Reference</span></span>  

 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="2ee8c-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2ee8c-127">Related Sections</span></span>  

 [<span data-ttu-id="2ee8c-128">Descripción de los niveles de protección</span><span class="sxs-lookup"><span data-stu-id="2ee8c-128">Understanding Protection Level</span></span>](../understanding-protection-level.md)  
  
 [<span data-ttu-id="2ee8c-129">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="2ee8c-129">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="2ee8c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ee8c-130">See also</span></span>

- [<span data-ttu-id="2ee8c-131">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="2ee8c-131">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="2ee8c-132">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="2ee8c-132">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="2ee8c-133">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="2ee8c-133">System-Provided Bindings</span></span>](../system-provided-bindings.md)
