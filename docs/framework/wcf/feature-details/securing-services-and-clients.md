---
title: Protección de servicios y clientes
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: 719ab26198bd7b83310025e03e541fa11b109612
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746414"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="526e7-102">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="526e7-102">Securing Services and Clients</span></span>
<span data-ttu-id="526e7-103">La información de esta sección se centra en la programación de la seguridad en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="526e7-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="526e7-104">Generalmente, esto incluye la selección de un enlace proporcionado por el sistema adecuado, el establecimiento de las propiedades del elemento de seguridad y, a continuación, el establecimiento de las propiedades de los comportamientos del servicio que rigen la recuperación de las credenciales utilizadas por el servicio o el cliente.</span><span class="sxs-lookup"><span data-stu-id="526e7-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="526e7-105">Estas técnicas cubren los requisitos de seguridad de la mayoría de los usuarios para la mayoría de los escenarios, tal como se muestra en [escenarios de seguridad comunes](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="526e7-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="526e7-106">Si su escenario requiere más capacidades, consulte en primer lugar las [capacidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md). Si una solución no es aparente, vea [ampliar la seguridad](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="526e7-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="526e7-107">Si va a crear (o interoperar con) un sistema que utiliza notificaciones enriquecidas, consulte los temas de [autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="526e7-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="526e7-108">Esta sección</span><span class="sxs-lookup"><span data-stu-id="526e7-108">In This Section</span></span>  
 [<span data-ttu-id="526e7-109">Programación de la seguridad de WCF</span><span class="sxs-lookup"><span data-stu-id="526e7-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="526e7-110">Información general del modelo de programación utilizado para proteger los mensajes.</span><span class="sxs-lookup"><span data-stu-id="526e7-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="526e7-111">Información general de la seguridad del transporte</span><span class="sxs-lookup"><span data-stu-id="526e7-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="526e7-112">Información general de cómo proteger los mensajes en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="526e7-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="526e7-113">Seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="526e7-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="526e7-114">Resume las razones para utilizar la seguridad de nivel de mensaje en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="526e7-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="526e7-115">Sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="526e7-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="526e7-116">Explicación de las consideraciones necesarias para proteger una sesión de WCF.</span><span class="sxs-lookup"><span data-stu-id="526e7-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="526e7-117">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="526e7-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="526e7-118">Explicación de algunas de las tareas comunes necesarias para la utilización de los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="526e7-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="526e7-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="526e7-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="526e7-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="526e7-120">Related Sections</span></span>  
 [<span data-ttu-id="526e7-121">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="526e7-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="526e7-122">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="526e7-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="526e7-123">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="526e7-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="526e7-124">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="526e7-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="526e7-125">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="526e7-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="526e7-126">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="526e7-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="526e7-127">Autorización</span><span class="sxs-lookup"><span data-stu-id="526e7-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="526e7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="526e7-128">See also</span></span>

- [<span data-ttu-id="526e7-129">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="526e7-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
- <span data-ttu-id="526e7-130">[Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="526e7-130">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
