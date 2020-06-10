---
title: Capacidades de seguridad con enlaces personalizados
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 48d17543f2b133c74bcfa82cfe1a2a0de28b1d01
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595198"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="c3fc1-102">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="c3fc1-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="c3fc1-103">Puede realizar las tareas de seguridad más habituales utilizando uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="c3fc1-104">Si necesita más control, sin embargo, puede crear un enlace personalizado con <xref:System.ServiceModel.Channels.SecurityBindingElement>, como se explica en estos temas.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="c3fc1-105">Para obtener más información sobre los enlaces personalizados, vea [enlaces personalizados](../extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="c3fc1-105">For more information about custom bindings, see [Custom Bindings](../extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c3fc1-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c3fc1-106">In This Section</span></span>  
 [<span data-ttu-id="c3fc1-107">Modos de autenticación de SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="c3fc1-107">SecurityBindingElement Authentication Modes</span></span>](securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="c3fc1-108">Describe los modos de autenticación que son posibles con un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="c3fc1-109">Procedimiento para crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="c3fc1-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="c3fc1-110">Describe los pasos básicos para crear un enlace personalizado con un elemento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="c3fc1-111">Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado</span><span class="sxs-lookup"><span data-stu-id="c3fc1-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="c3fc1-112">Describe cómo crear un elemento de seguridad para un modo de autenticación especificado.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="c3fc1-113">Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="c3fc1-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="c3fc1-114">Describe cómo deshabilitar las sesiones seguras al crear un servicio de federación.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="c3fc1-115">Procedimiento para habilitar la detección de repetición de mensajes</span><span class="sxs-lookup"><span data-stu-id="c3fc1-115">How to: Enable Message Replay Detection</span></span>](how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="c3fc1-116">Describe cómo determinar cuándo se produce un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="c3fc1-117">Procedimiento para crear una credencial de apoyo</span><span class="sxs-lookup"><span data-stu-id="c3fc1-117">How to: Create a Supporting Credential</span></span>](how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="c3fc1-118">Describe cómo proporcionar una credencial de soporte a un servicio, si el servicio lo requiere.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="c3fc1-119">Procedimiento para establecer una confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="c3fc1-119">How to: Set Up a Signature Confirmation</span></span>](how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="c3fc1-120">Describe los pasos para confirmar las firmas al firmar digitalmente los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="c3fc1-121">Procedimiento para establecer un sesgo de reloj máximo</span><span class="sxs-lookup"><span data-stu-id="c3fc1-121">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="c3fc1-122">Describe cómo establecer la diferencia horaria máxima permitida entre un servicio y un cliente.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="c3fc1-123">Procedimiento para deshabilitar el cifrado de firmas digitales</span><span class="sxs-lookup"><span data-stu-id="c3fc1-123">How to: Disable Encryption of Digital Signatures</span></span>](how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="c3fc1-124">Describe cómo deshabilitar el cifrado de firmas digitales puede suponer una ventaja de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c3fc1-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c3fc1-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="c3fc1-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="c3fc1-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c3fc1-126">Related Sections</span></span>  
 [<span data-ttu-id="c3fc1-127">Descripción de los niveles de protección</span><span class="sxs-lookup"><span data-stu-id="c3fc1-127">Understanding Protection Level</span></span>](../understanding-protection-level.md)  
  
 [<span data-ttu-id="c3fc1-128">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c3fc1-128">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="c3fc1-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3fc1-129">See also</span></span>

- [<span data-ttu-id="c3fc1-130">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="c3fc1-130">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="c3fc1-131">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="c3fc1-131">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="c3fc1-132">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="c3fc1-132">System-Provided Bindings</span></span>](../system-provided-bindings.md)
