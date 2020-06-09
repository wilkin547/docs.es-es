---
title: Protección de servicios y clientes
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: db0a0dcfbe04a7b7dbfabfed59f9b8637d0a2797
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84586213"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="5e0d3-102">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="5e0d3-102">Securing Services and Clients</span></span>
<span data-ttu-id="5e0d3-103">La información de esta sección se centra en la programación de la seguridad en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5e0d3-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="5e0d3-104">Generalmente, esto incluye la selección de un enlace proporcionado por el sistema adecuado, el establecimiento de las propiedades del elemento de seguridad y, a continuación, el establecimiento de las propiedades de los comportamientos del servicio que rigen la recuperación de las credenciales utilizadas por el servicio o el cliente.</span><span class="sxs-lookup"><span data-stu-id="5e0d3-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="5e0d3-105">Estas técnicas cubren los requisitos de seguridad de la mayoría de los usuarios para la mayoría de los escenarios, tal como se muestra en [escenarios de seguridad comunes](common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="5e0d3-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](common-security-scenarios.md).</span></span> <span data-ttu-id="5e0d3-106">Si su escenario requiere más capacidades, consulte en primer lugar las [capacidades de seguridad con enlaces personalizados](security-capabilities-with-custom-bindings.md). Si una solución no es aparente, vea [ampliar la seguridad](../extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="5e0d3-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../extending/extending-security.md).</span></span> <span data-ttu-id="5e0d3-107">Si va a crear (o interoperar con) un sistema que utiliza notificaciones enriquecidas, consulte los temas de [autorización](authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="5e0d3-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e0d3-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5e0d3-108">In This Section</span></span>  
 [<span data-ttu-id="5e0d3-109">Programación de la seguridad de WCF</span><span class="sxs-lookup"><span data-stu-id="5e0d3-109">Programming WCF Security</span></span>](programming-wcf-security.md)  
 <span data-ttu-id="5e0d3-110">Información general del modelo de programación utilizado para proteger los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5e0d3-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="5e0d3-111">Información general de la seguridad del transporte</span><span class="sxs-lookup"><span data-stu-id="5e0d3-111">Transport Security Overview</span></span>](transport-security-overview.md)  
 <span data-ttu-id="5e0d3-112">Información general de cómo proteger los mensajes en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="5e0d3-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="5e0d3-113">Seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="5e0d3-113">Message Security</span></span>](message-security-in-wcf.md)  
 <span data-ttu-id="5e0d3-114">Resume las razones para utilizar la seguridad de nivel de mensaje en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5e0d3-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="5e0d3-115">Sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="5e0d3-115">Secure Sessions</span></span>](secure-sessions.md)  
 <span data-ttu-id="5e0d3-116">Explicación de las consideraciones necesarias para proteger una sesión de WCF.</span><span class="sxs-lookup"><span data-stu-id="5e0d3-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="5e0d3-117">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="5e0d3-117">Working with Certificates</span></span>](working-with-certificates.md)  
 <span data-ttu-id="5e0d3-118">Explicación de algunas de las tareas comunes necesarias para la utilización de los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="5e0d3-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5e0d3-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="5e0d3-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="5e0d3-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5e0d3-120">Related Sections</span></span>  
 [<span data-ttu-id="5e0d3-121">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="5e0d3-121">Security Concepts</span></span>](security-concepts.md)  
  
 [<span data-ttu-id="5e0d3-122">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="5e0d3-122">Extending Security</span></span>](../extending/extending-security.md)  
  
 [<span data-ttu-id="5e0d3-123">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="5e0d3-123">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
 [<span data-ttu-id="5e0d3-124">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="5e0d3-124">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="5e0d3-125">Capacidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="5e0d3-125">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="5e0d3-126">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="5e0d3-126">Extending Security</span></span>](../extending/extending-security.md)  
  
 [<span data-ttu-id="5e0d3-127">Autorización</span><span class="sxs-lookup"><span data-stu-id="5e0d3-127">Authorization</span></span>](authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="5e0d3-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e0d3-128">See also</span></span>

- [<span data-ttu-id="5e0d3-129">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="5e0d3-129">Basic WCF Programming</span></span>](../basic-wcf-programming.md)
- <span data-ttu-id="5e0d3-130">[Modelo de seguridad para Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="5e0d3-130">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
