---
title: Seguridad en Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
author: BrucePerlerMS
ms.openlocfilehash: 2d4f2d67c8afd1687d9de506cf8a7616408069d2
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111456"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="10d24-102">Seguridad en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="10d24-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="10d24-103">Los temas de esta sección describen las características de seguridad de Windows Communication Foundation (WCF) y cómo utilizarlas para ayudar a proteger los mensajes.</span><span class="sxs-lookup"><span data-stu-id="10d24-103">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="10d24-104">Para obtener más información sobre la seguridad y Windows Server AppFabric, consulte [modelo de seguridad para Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="10d24-104">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10d24-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="10d24-105">In This Section</span></span>  
 [<span data-ttu-id="10d24-106">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="10d24-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="10d24-107">Describe las características de seguridad en WCF.</span><span class="sxs-lookup"><span data-stu-id="10d24-107">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="10d24-108">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="10d24-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="10d24-109">Describe la terminología básica y los conceptos usados en la seguridad de WCF.</span><span class="sxs-lookup"><span data-stu-id="10d24-109">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="10d24-110">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="10d24-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="10d24-111">Describe los escenarios y topologías que puede configurar con WCF.</span><span class="sxs-lookup"><span data-stu-id="10d24-111">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="10d24-112">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="10d24-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="10d24-113">Proporciona información general sobre los comportamientos de WCF que afectan a la seguridad, como la configuración de las credenciales.</span><span class="sxs-lookup"><span data-stu-id="10d24-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="10d24-114">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="10d24-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="10d24-115">Una vista orientada a seguridad de los enlaces, incluidos los temas que muestran cómo crear los enlaces de seguridad personalizados.</span><span class="sxs-lookup"><span data-stu-id="10d24-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="10d24-116">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="10d24-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="10d24-117">Describe cómo proteger mensajes mediante las características de seguridad WCF.</span><span class="sxs-lookup"><span data-stu-id="10d24-117">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="10d24-118">Autenticación</span><span class="sxs-lookup"><span data-stu-id="10d24-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="10d24-119">Muestra tareas de autenticación comunes.</span><span class="sxs-lookup"><span data-stu-id="10d24-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="10d24-120">Autorización</span><span class="sxs-lookup"><span data-stu-id="10d24-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="10d24-121">Describe los escenarios de autorización comunes con implementaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="10d24-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="10d24-122">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="10d24-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="10d24-123">Describe los fundamentos de federación y cómo crear clientes que se comuniquen con servidores federados.</span><span class="sxs-lookup"><span data-stu-id="10d24-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="10d24-124">Confianza parcial</span><span class="sxs-lookup"><span data-stu-id="10d24-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="10d24-125">Describe cómo ejecutar escenarios de confianza parcial y las limitaciones de WCF cuando se ejecuta en confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="10d24-125">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="10d24-126">Auditoría</span><span class="sxs-lookup"><span data-stu-id="10d24-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="10d24-127">Describe cómo auditar los eventos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="10d24-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="10d24-128">Orientación de seguridad y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="10d24-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="10d24-129">Directrices para crear aplicaciones seguras de WCF.</span><span class="sxs-lookup"><span data-stu-id="10d24-129">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="10d24-130">Referencia</span><span class="sxs-lookup"><span data-stu-id="10d24-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="10d24-131">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="10d24-131">Related Sections</span></span>  
 [<span data-ttu-id="10d24-132">Detalles de las características de WCF</span><span class="sxs-lookup"><span data-stu-id="10d24-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="10d24-133">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="10d24-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="10d24-134">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="10d24-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="10d24-135">Información conceptual</span><span class="sxs-lookup"><span data-stu-id="10d24-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="10d24-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="10d24-136">See Also</span></span>  
 [<span data-ttu-id="10d24-137">Configuración de su aplicación</span><span class="sxs-lookup"><span data-stu-id="10d24-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
