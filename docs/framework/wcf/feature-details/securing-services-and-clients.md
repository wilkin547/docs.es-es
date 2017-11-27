---
title: "Protección de servicios y clientes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: ed37992b5488d33b9292bdd54eef47f9eb12f225
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="8fe34-102">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="8fe34-102">Securing Services and Clients</span></span>
<span data-ttu-id="8fe34-103">La información de esta sección se centra en programar la seguridad en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fe34-103">The information in this section focuses on programming security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="8fe34-104">Generalmente, esto incluye la selección de un enlace proporcionado por el sistema adecuado, el establecimiento de las propiedades del elemento de seguridad y, a continuación, el establecimiento de las propiedades de los comportamientos del servicio que rigen la recuperación de las credenciales utilizadas por el servicio o el cliente.</span><span class="sxs-lookup"><span data-stu-id="8fe34-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="8fe34-105">Estas técnicas cubran los requisitos de seguridad de la mayoría de los usuarios para la mayoría de los escenarios, como se muestra en [escenarios comunes de seguridad](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="8fe34-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="8fe34-106">Si su escenario requiere más capacidades, primero vea [capacidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); si no es evidente, una solución, consulte [extender seguridad](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="8fe34-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="8fe34-107">Si está creando (o interoperar con) un sistema que utiliza notificaciones completo, vea los temas de [autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="8fe34-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8fe34-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8fe34-108">In This Section</span></span>  
 [<span data-ttu-id="8fe34-109">Programar la seguridad WCF</span><span class="sxs-lookup"><span data-stu-id="8fe34-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="8fe34-110">Información general del modelo de programación utilizado para proteger los mensajes.</span><span class="sxs-lookup"><span data-stu-id="8fe34-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="8fe34-111">Información general sobre la seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="8fe34-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="8fe34-112">Información general de cómo proteger los mensajes en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="8fe34-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="8fe34-113">Seguridad de mensajes</span><span class="sxs-lookup"><span data-stu-id="8fe34-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="8fe34-114">Resume las razones para utilizar la seguridad del nivel de mensaje en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fe34-114">Summarizes reasons for using message-level security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
 [<span data-ttu-id="8fe34-115">Sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="8fe34-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="8fe34-116">Una explicación de las consideraciones necesarias para proteger una sesión [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8fe34-116">A discussion of the considerations required when securing a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] session.</span></span>  
  
 [<span data-ttu-id="8fe34-117">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="8fe34-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="8fe34-118">Explicación de algunas de las tareas comunes necesarias para la utilización de los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="8fe34-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8fe34-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="8fe34-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="8fe34-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="8fe34-120">Related Sections</span></span>  
 [<span data-ttu-id="8fe34-121">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="8fe34-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="8fe34-122">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="8fe34-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="8fe34-123">Escenarios comunes de seguridad</span><span class="sxs-lookup"><span data-stu-id="8fe34-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="8fe34-124">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="8fe34-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="8fe34-125">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="8fe34-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="8fe34-126">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="8fe34-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="8fe34-127">Autorización</span><span class="sxs-lookup"><span data-stu-id="8fe34-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="8fe34-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fe34-128">See Also</span></span>  
 [<span data-ttu-id="8fe34-129">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="8fe34-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="8fe34-130">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="8fe34-130">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
