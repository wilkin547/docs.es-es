---
title: Capacidades de seguridad con enlaces personalizados
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
ms.openlocfilehash: 51359dd555db44891b4c8fe7bca9b62cab5f8d29
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708524"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="ff0c2-102">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="ff0c2-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="ff0c2-103">Puede realizar las tareas de seguridad más habituales utilizando uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="ff0c2-104">Si necesita más control, sin embargo, puede crear un enlace personalizado con <xref:System.ServiceModel.Channels.SecurityBindingElement>, como se explica en estos temas.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="ff0c2-105">Para obtener más información acerca de los enlaces personalizados, consulte [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="ff0c2-105">For more information about custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff0c2-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ff0c2-106">In This Section</span></span>  
 [<span data-ttu-id="ff0c2-107">Modos de autenticación de SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ff0c2-107">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="ff0c2-108">Describe los modos de autenticación que son posibles con un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="ff0c2-109">Cómo: Crear un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ff0c2-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="ff0c2-110">Describe los pasos básicos para crear un enlace personalizado con un elemento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="ff0c2-111">Cómo: Crear un SecurityBindingElement para un modo de autenticación especificado</span><span class="sxs-lookup"><span data-stu-id="ff0c2-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="ff0c2-112">Describe cómo crear un elemento de seguridad para un modo de autenticación especificado.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="ff0c2-113">Cómo: Deshabilitar las sesiones seguras en WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ff0c2-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="ff0c2-114">Describe cómo deshabilitar las sesiones seguras al crear un servicio de federación.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="ff0c2-115">Cómo: Habilitar la detección de reproducción de mensajes</span><span class="sxs-lookup"><span data-stu-id="ff0c2-115">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="ff0c2-116">Describe cómo determinar cuándo se produce un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="ff0c2-117">Cómo: Crear una credencial de aprobación</span><span class="sxs-lookup"><span data-stu-id="ff0c2-117">How to: Create a Supporting Credential</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="ff0c2-118">Describe cómo proporcionar una credencial de soporte a un servicio, si el servicio lo requiere.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="ff0c2-119">Cómo: Configurar una confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="ff0c2-119">How to: Set Up a Signature Confirmation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="ff0c2-120">Describe los pasos para confirmar las firmas al firmar digitalmente los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="ff0c2-121">Cómo: Conjunto un sesgo de reloj máximo</span><span class="sxs-lookup"><span data-stu-id="ff0c2-121">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="ff0c2-122">Describe cómo establecer la diferencia horaria máxima permitida entre un servicio y un cliente.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="ff0c2-123">Cómo: Deshabilitar el cifrado de firmas digitales</span><span class="sxs-lookup"><span data-stu-id="ff0c2-123">How to: Disable Encryption of Digital Signatures</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="ff0c2-124">Describe cómo deshabilitar el cifrado de firmas digitales puede suponer una ventaja de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="ff0c2-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ff0c2-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="ff0c2-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [<span data-ttu-id="ff0c2-126">\<security></span><span class="sxs-lookup"><span data-stu-id="ff0c2-126">\<security></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="ff0c2-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ff0c2-127">Related Sections</span></span>  
 [<span data-ttu-id="ff0c2-128">Descripción de los niveles de protección</span><span class="sxs-lookup"><span data-stu-id="ff0c2-128">Understanding Protection Level</span></span>](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [<span data-ttu-id="ff0c2-129">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ff0c2-129">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff0c2-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff0c2-130">See also</span></span>
- [<span data-ttu-id="ff0c2-131">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="ff0c2-131">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
- [<span data-ttu-id="ff0c2-132">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="ff0c2-132">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="ff0c2-133">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="ff0c2-133">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
