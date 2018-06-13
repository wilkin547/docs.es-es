---
title: Capacidades de seguridad con enlaces personalizados
ms.date: 03/30/2017
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2cfe5a18dd0fc7f8a8f54559d1d5b57e52cefa8f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497430"
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="6518f-102">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="6518f-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="6518f-103">Puede realizar las tareas de seguridad más habituales utilizando uno de los enlaces proporcionados por el sistema.</span><span class="sxs-lookup"><span data-stu-id="6518f-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="6518f-104">Si necesita más control, sin embargo, puede crear un enlace personalizado con <xref:System.ServiceModel.Channels.SecurityBindingElement>, como se explica en estos temas.</span><span class="sxs-lookup"><span data-stu-id="6518f-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="6518f-105">Para obtener más información acerca de los enlaces personalizados, consulte [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="6518f-105">For more information about custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6518f-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6518f-106">In This Section</span></span>  
 [<span data-ttu-id="6518f-107">Modos de autenticación de SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="6518f-107">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="6518f-108">Describe los modos de autenticación que son posibles con un enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="6518f-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="6518f-109">Creación de un enlace personalizado mediante SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="6518f-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="6518f-110">Describe los pasos básicos para crear un enlace personalizado con un elemento de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6518f-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="6518f-111">Creación de un SecurityBindingElement para un modo de autenticación especificado</span><span class="sxs-lookup"><span data-stu-id="6518f-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="6518f-112">Describe cómo crear un elemento de seguridad para un modo de autenticación especificado.</span><span class="sxs-lookup"><span data-stu-id="6518f-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="6518f-113">Deshabilitar sesiones seguras en WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="6518f-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="6518f-114">Describe cómo deshabilitar las sesiones seguras al crear un servicio de federación.</span><span class="sxs-lookup"><span data-stu-id="6518f-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="6518f-115">Habilitar la detección de repetición de mensajes</span><span class="sxs-lookup"><span data-stu-id="6518f-115">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="6518f-116">Describe cómo determinar cuándo se produce un ataque de reproducción.</span><span class="sxs-lookup"><span data-stu-id="6518f-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="6518f-117">Creación de una credencial auxiliar</span><span class="sxs-lookup"><span data-stu-id="6518f-117">How to: Create a Supporting Credential</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="6518f-118">Describe cómo proporcionar una credencial de soporte a un servicio, si el servicio lo requiere.</span><span class="sxs-lookup"><span data-stu-id="6518f-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="6518f-119">Configuración de una confirmación de firma</span><span class="sxs-lookup"><span data-stu-id="6518f-119">How to: Set Up a Signature Confirmation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="6518f-120">Describe los pasos para confirmar las firmas al firmar digitalmente los mensajes.</span><span class="sxs-lookup"><span data-stu-id="6518f-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="6518f-121">Definición de un sesgo de reloj máximo</span><span class="sxs-lookup"><span data-stu-id="6518f-121">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="6518f-122">Describe cómo establecer la diferencia horaria máxima permitida entre un servicio y un cliente.</span><span class="sxs-lookup"><span data-stu-id="6518f-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="6518f-123">Deshabilitar el cifrado de firmas digitales</span><span class="sxs-lookup"><span data-stu-id="6518f-123">How to: Disable Encryption of Digital Signatures</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="6518f-124">Describe cómo deshabilitar el cifrado de firmas digitales puede suponer una ventaja de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6518f-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6518f-125">Referencia</span><span class="sxs-lookup"><span data-stu-id="6518f-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [<span data-ttu-id="6518f-126">\<seguridad ></span><span class="sxs-lookup"><span data-stu-id="6518f-126">\<security></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="6518f-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="6518f-127">Related Sections</span></span>  
 [<span data-ttu-id="6518f-128">Descripción de los niveles de protección</span><span class="sxs-lookup"><span data-stu-id="6518f-128">Understanding Protection Level</span></span>](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [<span data-ttu-id="6518f-129">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="6518f-129">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="6518f-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="6518f-130">See Also</span></span>  
 [<span data-ttu-id="6518f-131">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="6518f-131">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [<span data-ttu-id="6518f-132">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="6518f-132">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="6518f-133">Enlaces proporcionados por el sistema</span><span class="sxs-lookup"><span data-stu-id="6518f-133">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
