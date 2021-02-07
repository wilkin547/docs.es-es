---
description: 'Más información acerca de: seguridad de Windows Communication Foundation'
title: Seguridad en Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
ms.openlocfilehash: 8cf748504c85844f82f8941be1b60bb29478f730
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726798"
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="ebfcf-103">Seguridad en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ebfcf-103">Windows Communication Foundation Security</span></span>

<span data-ttu-id="ebfcf-104">En los temas de esta sección se describen las características de seguridad de Windows Communication Foundation (WCF) y cómo usarlas para proteger los mensajes.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-104">The topics in this section describe Windows Communication Foundation (WCF) security features and how to use them to help secure messages.</span></span>  
  
 <span data-ttu-id="ebfcf-105">Para obtener más información acerca de Windows Server AppFabric y la seguridad, vea [modelo de seguridad para Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10)) .</span><span class="sxs-lookup"><span data-stu-id="ebfcf-105">For more information about Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ebfcf-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ebfcf-106">In This Section</span></span>  

 [<span data-ttu-id="ebfcf-107">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="ebfcf-107">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="ebfcf-108">Describe las características de seguridad de WCF.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-108">Describes the security features in WCF.</span></span>  
  
 [<span data-ttu-id="ebfcf-109">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="ebfcf-109">Security Concepts</span></span>](security-concepts.md)  
 <span data-ttu-id="ebfcf-110">Describe la terminología y los conceptos básicos que se usan en la seguridad de WCF.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-110">Describes the basic terminology and concepts used in WCF security.</span></span>  
  
 [<span data-ttu-id="ebfcf-111">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="ebfcf-111">Common Security Scenarios</span></span>](common-security-scenarios.md)  
 <span data-ttu-id="ebfcf-112">Describe escenarios y topologías que se pueden configurar con WCF.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-112">Describes scenarios and topologies you can configure with WCF.</span></span>  
  
 [<span data-ttu-id="ebfcf-113">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="ebfcf-113">Security Behaviors</span></span>](security-behaviors-in-wcf.md)  
 <span data-ttu-id="ebfcf-114">Proporciona información general sobre los comportamientos de WCF que afectan a la seguridad, como la configuración de las credenciales.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-114">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="ebfcf-115">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="ebfcf-115">Bindings and Security</span></span>](bindings-and-security.md)  
 <span data-ttu-id="ebfcf-116">Una vista orientada a seguridad de los enlaces, incluidos los temas que muestran cómo crear los enlaces de seguridad personalizados.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-116">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="ebfcf-117">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="ebfcf-117">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
 <span data-ttu-id="ebfcf-118">Describe cómo proteger los mensajes mediante las características de seguridad de WCF.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-118">Describes how to secure messages using WCF security features.</span></span>  
  
 [<span data-ttu-id="ebfcf-119">Autenticación</span><span class="sxs-lookup"><span data-stu-id="ebfcf-119">Authentication</span></span>](authentication-in-wcf.md)  
 <span data-ttu-id="ebfcf-120">Muestra tareas de autenticación comunes.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-120">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="ebfcf-121">Autorización</span><span class="sxs-lookup"><span data-stu-id="ebfcf-121">Authorization</span></span>](authorization-in-wcf.md)  
 <span data-ttu-id="ebfcf-122">Describe los escenarios de autorización comunes con implementaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-122">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="ebfcf-123">Federación y tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="ebfcf-123">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
 <span data-ttu-id="ebfcf-124">Describe los fundamentos de federación y cómo crear clientes que se comuniquen con servidores federados.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-124">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="ebfcf-125">Confianza parcial</span><span class="sxs-lookup"><span data-stu-id="ebfcf-125">Partial Trust</span></span>](partial-trust.md)  
 <span data-ttu-id="ebfcf-126">Describe cómo ejecutar escenarios de confianza parcial y limitaciones de WCF cuando se ejecuta en modo de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-126">Describes how to run partially-trusted scenarios and WCF limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="ebfcf-127">Auditoría</span><span class="sxs-lookup"><span data-stu-id="ebfcf-127">Auditing</span></span>](auditing-security-events.md)  
 <span data-ttu-id="ebfcf-128">Describe cómo auditar los eventos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-128">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="ebfcf-129">Orientación de seguridad y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="ebfcf-129">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)  
 <span data-ttu-id="ebfcf-130">Directrices para crear aplicaciones WCF seguras.</span><span class="sxs-lookup"><span data-stu-id="ebfcf-130">Guidelines for creating secure WCF applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ebfcf-131">Referencia</span><span class="sxs-lookup"><span data-stu-id="ebfcf-131">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="ebfcf-132">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ebfcf-132">Related Sections</span></span>  

 [<span data-ttu-id="ebfcf-133">Detalles de las características de WCF</span><span class="sxs-lookup"><span data-stu-id="ebfcf-133">WCF Feature Details</span></span>](index.md)  
  
 [<span data-ttu-id="ebfcf-134">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="ebfcf-134">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
 [<span data-ttu-id="ebfcf-135">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="ebfcf-135">Getting Started Tutorial</span></span>](../getting-started-tutorial.md)  
  
 [<span data-ttu-id="ebfcf-136">Información general conceptual</span><span class="sxs-lookup"><span data-stu-id="ebfcf-136">Conceptual Overview</span></span>](../conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="ebfcf-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebfcf-137">See also</span></span>

- [<span data-ttu-id="ebfcf-138">Configuración de su aplicación</span><span class="sxs-lookup"><span data-stu-id="ebfcf-138">Configuring Your Application</span></span>](../diagnostics/configuring-your-application.md)
