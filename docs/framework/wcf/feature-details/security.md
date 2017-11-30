---
title: Seguridad en Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, programming
- security [WCF]
- Windows Communication Foundation, security
ms.assetid: 7ea87fcb-dcfb-4a4a-8b03-6b954575d45b
caps.latest.revision: "21"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 38f62a6ccc0c9291f3963173475f99d5800feb39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="windows-communication-foundation-security"></a><span data-ttu-id="577f6-102">Seguridad en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="577f6-102">Windows Communication Foundation Security</span></span>
<span data-ttu-id="577f6-103">Los temas de esta sección describen las características de seguridad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y cómo utilizarlas para ayudar a proteger los mensajes.</span><span class="sxs-lookup"><span data-stu-id="577f6-103">The topics in this section describe [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security features and how to use them to help secure messages.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="577f6-104">Windows Server AppFabric y seguridad, vea [modelo de seguridad de Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="577f6-104"> Windows Server AppFabric and security, see [Security Model for Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="577f6-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="577f6-105">In This Section</span></span>  
 [<span data-ttu-id="577f6-106">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="577f6-106">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 <span data-ttu-id="577f6-107">Describe las características de seguridad en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="577f6-107">Describes the security features in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="577f6-108">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="577f6-108">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
 <span data-ttu-id="577f6-109">Describe la terminología básica y los conceptos utilizados en la seguridad de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="577f6-109">Describes the basic terminology and concepts used in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security.</span></span>  
  
 [<span data-ttu-id="577f6-110">Escenarios comunes de seguridad</span><span class="sxs-lookup"><span data-stu-id="577f6-110">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 <span data-ttu-id="577f6-111">Describe los escenarios y topologías que puede configurar con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="577f6-111">Describes scenarios and topologies you can configure with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="577f6-112">Comportamientos de seguridad</span><span class="sxs-lookup"><span data-stu-id="577f6-112">Security Behaviors</span></span>](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 <span data-ttu-id="577f6-113">Proporciona información general sobre los comportamientos de WCF que afectan a la seguridad, como la configuración de las credenciales.</span><span class="sxs-lookup"><span data-stu-id="577f6-113">Provides an overview of WCF behaviors that affect security, such as setting credentials.</span></span>  
  
 [<span data-ttu-id="577f6-114">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="577f6-114">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 <span data-ttu-id="577f6-115">Una vista orientada a seguridad de los enlaces, incluidos los temas que muestran cómo crear los enlaces de seguridad personalizados.</span><span class="sxs-lookup"><span data-stu-id="577f6-115">A security-oriented view of the bindings, including topics that demonstrate how to create custom security bindings.</span></span>  
  
 [<span data-ttu-id="577f6-116">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="577f6-116">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 <span data-ttu-id="577f6-117">Describe cómo proteger mensajes mediante las características de seguridad [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="577f6-117">Describes how to secure messages using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security features.</span></span>  
  
 [<span data-ttu-id="577f6-118">Autenticación</span><span class="sxs-lookup"><span data-stu-id="577f6-118">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
 <span data-ttu-id="577f6-119">Muestra tareas de autenticación comunes.</span><span class="sxs-lookup"><span data-stu-id="577f6-119">Demonstrates common authentication tasks.</span></span>  
  
 [<span data-ttu-id="577f6-120">Autorización</span><span class="sxs-lookup"><span data-stu-id="577f6-120">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 <span data-ttu-id="577f6-121">Describe los escenarios de autorización comunes con implementaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="577f6-121">Describes common authorization scenarios with security implementations.</span></span>  
  
 [<span data-ttu-id="577f6-122">Federación y Tokens emitidos</span><span class="sxs-lookup"><span data-stu-id="577f6-122">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 <span data-ttu-id="577f6-123">Describe los fundamentos de federación y cómo crear clientes que se comuniquen con servidores federados.</span><span class="sxs-lookup"><span data-stu-id="577f6-123">Describes the basics of federation and how to create clients that communicate with federated servers.</span></span>  
  
 [<span data-ttu-id="577f6-124">Confianza parcial</span><span class="sxs-lookup"><span data-stu-id="577f6-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)  
 <span data-ttu-id="577f6-125">Describe cómo ejecutar escenarios parcialmente confiables y las limitaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] al ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="577f6-125">Describes how to run partially-trusted scenarios and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] limitations when running partially trusted.</span></span>  
  
 [<span data-ttu-id="577f6-126">Auditoría</span><span class="sxs-lookup"><span data-stu-id="577f6-126">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 <span data-ttu-id="577f6-127">Describe cómo auditar los eventos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="577f6-127">Describes how to audit security events.</span></span>  
  
 [<span data-ttu-id="577f6-128">Guía de seguridad y procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="577f6-128">Security Guidance and Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 <span data-ttu-id="577f6-129">Instrucciones para crear las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] seguras.</span><span class="sxs-lookup"><span data-stu-id="577f6-129">Guidelines for creating secure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="577f6-130">Referencia</span><span class="sxs-lookup"><span data-stu-id="577f6-130">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="577f6-131">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="577f6-131">Related Sections</span></span>  
 [<span data-ttu-id="577f6-132">Detalles de las características de WCF</span><span class="sxs-lookup"><span data-stu-id="577f6-132">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="577f6-133">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="577f6-133">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="577f6-134">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="577f6-134">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="577f6-135">Información conceptual</span><span class="sxs-lookup"><span data-stu-id="577f6-135">Conceptual Overview</span></span>](../../../../docs/framework/wcf/conceptual-overview.md)  
  
## <a name="see-also"></a><span data-ttu-id="577f6-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="577f6-136">See Also</span></span>  
 [<span data-ttu-id="577f6-137">Configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="577f6-137">Configuring Your Application</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-your-application.md)
