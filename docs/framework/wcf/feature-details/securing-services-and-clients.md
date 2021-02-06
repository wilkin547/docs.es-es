---
description: 'Más información sobre: protección de servicios y clientes'
title: Protección de servicios y clientes
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: ff947e8bf975fd3fb3c6513ee0bf49bb21a951dd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632638"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="eac26-103">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="eac26-103">Securing Services and Clients</span></span>

<span data-ttu-id="eac26-104">La información de esta sección se centra en la programación de la seguridad en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eac26-104">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="eac26-105">Generalmente, esto incluye la selección de un enlace proporcionado por el sistema adecuado, el establecimiento de las propiedades del elemento de seguridad y, a continuación, el establecimiento de las propiedades de los comportamientos del servicio que rigen la recuperación de las credenciales utilizadas por el servicio o el cliente.</span><span class="sxs-lookup"><span data-stu-id="eac26-105">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="eac26-106">Estas técnicas cubren los requisitos de seguridad de la mayoría de los usuarios para la mayoría de los escenarios, tal como se muestra en [escenarios de seguridad comunes](common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="eac26-106">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](common-security-scenarios.md).</span></span> <span data-ttu-id="eac26-107">Si su escenario requiere más capacidades, consulte en primer lugar las [capacidades de seguridad con enlaces personalizados](security-capabilities-with-custom-bindings.md). Si una solución no es aparente, vea [ampliar la seguridad](../extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="eac26-107">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../extending/extending-security.md).</span></span> <span data-ttu-id="eac26-108">Si va a crear (o interoperar con) un sistema que utiliza notificaciones enriquecidas, consulte los temas de [autorización](authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="eac26-108">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eac26-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="eac26-109">In This Section</span></span>  

 [<span data-ttu-id="eac26-110">Programación de la seguridad de WCF</span><span class="sxs-lookup"><span data-stu-id="eac26-110">Programming WCF Security</span></span>](programming-wcf-security.md)  
 <span data-ttu-id="eac26-111">Información general del modelo de programación utilizado para proteger los mensajes.</span><span class="sxs-lookup"><span data-stu-id="eac26-111">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="eac26-112">Información general de la seguridad del transporte</span><span class="sxs-lookup"><span data-stu-id="eac26-112">Transport Security Overview</span></span>](transport-security-overview.md)  
 <span data-ttu-id="eac26-113">Información general de cómo proteger los mensajes en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="eac26-113">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="eac26-114">Seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="eac26-114">Message Security</span></span>](message-security-in-wcf.md)  
 <span data-ttu-id="eac26-115">Resume las razones para utilizar la seguridad de nivel de mensaje en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eac26-115">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="eac26-116">Sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="eac26-116">Secure Sessions</span></span>](secure-sessions.md)  
 <span data-ttu-id="eac26-117">Explicación de las consideraciones necesarias para proteger una sesión de WCF.</span><span class="sxs-lookup"><span data-stu-id="eac26-117">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="eac26-118">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="eac26-118">Working with Certificates</span></span>](working-with-certificates.md)  
 <span data-ttu-id="eac26-119">Explicación de algunas de las tareas comunes necesarias para la utilización de los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="eac26-119">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eac26-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="eac26-120">Reference</span></span>  

 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="eac26-121">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="eac26-121">Related Sections</span></span>  

 [<span data-ttu-id="eac26-122">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="eac26-122">Security Concepts</span></span>](security-concepts.md)  
  
 [<span data-ttu-id="eac26-123">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="eac26-123">Extending Security</span></span>](../extending/extending-security.md)  
  
 [<span data-ttu-id="eac26-124">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="eac26-124">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
 [<span data-ttu-id="eac26-125">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="eac26-125">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="eac26-126">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="eac26-126">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="eac26-127">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="eac26-127">Extending Security</span></span>](../extending/extending-security.md)  
  
 [<span data-ttu-id="eac26-128">Autorización</span><span class="sxs-lookup"><span data-stu-id="eac26-128">Authorization</span></span>](authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="eac26-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="eac26-129">See also</span></span>

- [<span data-ttu-id="eac26-130">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="eac26-130">Basic WCF Programming</span></span>](../basic-wcf-programming.md)
- <span data-ttu-id="eac26-131">[Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="eac26-131">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
