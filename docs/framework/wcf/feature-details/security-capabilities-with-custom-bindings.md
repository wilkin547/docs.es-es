---
title: Capacidades de seguridad con enlaces personalizados
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 1b12907481ccb3f3c5f4b8aaba6ede8ebfa6228a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288312"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="a86f2-102">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="a86f2-102">Security Capabilities with Custom Bindings</span></span>

<span data-ttu-id="a86f2-103">Puede realizar las tareas de seguridad más habituales utilizando uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="a86f2-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="a86f2-104">Si necesita más control, sin embargo, puede crear un enlace personalizado con <xref:System.ServiceModel.Channels.SecurityBindingElement>, como se explica en estos temas.</span><span class="sxs-lookup"><span data-stu-id="a86f2-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="a86f2-105">Para obtener más información sobre los enlaces personalizados, vea [enlaces personalizados](../extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="a86f2-105">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a86f2-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a86f2-106">In This Section</span></span>  

 [<span data-ttu-id="a86f2-107">Modos de autenticación de SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a86f2-107">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="a86f2-108">Describe los modos de autenticación que son posibles con un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="a86f2-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="a86f2-109">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a86f2-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="a86f2-110">Describe los pasos básicos para crear un enlace personalizado con un elemento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a86f2-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="a86f2-111">Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado</span><span class="sxs-lookup"><span data-stu-id="a86f2-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="a86f2-112">Describe cómo crear un elemento de seguridad para un modo de autenticación especificado.</span><span class="sxs-lookup"><span data-stu-id="a86f2-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="a86f2-113">Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a86f2-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="a86f2-114">Describe cómo deshabilitar las sesiones seguras al crear un servicio de federación.</span><span class="sxs-lookup"><span data-stu-id="a86f2-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="a86f2-115">Procedimiento para habilitar la detección de repetición de mensajes</span><span class="sxs-lookup"><span data-stu-id="a86f2-115">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="a86f2-116">Describe cómo determinar cuándo se produce un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="a86f2-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="a86f2-117">Procedimiento para crear una credencial de apoyo</span><span class="sxs-lookup"><span data-stu-id="a86f2-117">How to: Create a Supporting Credential</span></span>](how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="a86f2-118">Describe cómo proporcionar una credencial de soporte a un servicio, si el servicio lo requiere.</span><span class="sxs-lookup"><span data-stu-id="a86f2-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="a86f2-119">Procedimiento para establecer una confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="a86f2-119">How to: Set Up a Signature Confirmation</span></span>](how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="a86f2-120">Describe los pasos para confirmar las firmas al firmar digitalmente los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a86f2-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="a86f2-121">Procedimiento para establecer un sesgo de reloj máximo</span><span class="sxs-lookup"><span data-stu-id="a86f2-121">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="a86f2-122">Describe cómo establecer la diferencia horaria máxima permitida entre un servicio y un cliente.</span><span class="sxs-lookup"><span data-stu-id="a86f2-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="a86f2-123">Procedimiento para deshabilitar el cifrado de firmas digitales</span><span class="sxs-lookup"><span data-stu-id="a86f2-123">How to: Disable Encryption of Digital Signatures</span></span>](how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="a86f2-124">Describe cómo deshabilitar el cifrado de firmas digitales puede suponer una ventaja de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a86f2-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a86f2-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="a86f2-125">Reference</span></span>  

 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="a86f2-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="a86f2-126">Related Sections</span></span>  

 [<span data-ttu-id="a86f2-127">Descripción de los niveles de protección</span><span class="sxs-lookup"><span data-stu-id="a86f2-127">Understanding Protection Level</span></span>](../understanding-protection-level.md)  
  
 [<span data-ttu-id="a86f2-128">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="a86f2-128">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="a86f2-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a86f2-129">See also</span></span>

- [<span data-ttu-id="a86f2-130">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="a86f2-130">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="a86f2-131">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="a86f2-131">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="a86f2-132">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="a86f2-132">System-Provided Bindings</span></span>](../system-provided-bindings.md)
