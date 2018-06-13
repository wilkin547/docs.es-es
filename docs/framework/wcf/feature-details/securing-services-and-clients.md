---
title: Protección de servicios y clientes
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2e0440aadcad7c4297cdc6e6489ca004480420ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497417"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="4c131-102">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="4c131-102">Securing Services and Clients</span></span>
<span data-ttu-id="4c131-103">La información de esta sección se centra en programar la seguridad de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4c131-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="4c131-104">Generalmente, esto incluye la selección de un enlace proporcionado por el sistema adecuado, el establecimiento de las propiedades del elemento de seguridad y, a continuación, el establecimiento de las propiedades de los comportamientos del servicio que rigen la recuperación de las credenciales utilizadas por el servicio o el cliente.</span><span class="sxs-lookup"><span data-stu-id="4c131-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="4c131-105">Estas técnicas cubran los requisitos de seguridad de la mayoría de los usuarios para la mayoría de los escenarios, como se muestra en [escenarios comunes de seguridad](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="4c131-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="4c131-106">Si su escenario requiere más capacidades, primero vea [capacidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); si no es evidente, una solución, consulte [extender seguridad](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="4c131-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="4c131-107">Si está creando (o interoperar con) un sistema que utiliza notificaciones completo, vea los temas de [autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="4c131-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c131-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4c131-108">In This Section</span></span>  
 [<span data-ttu-id="4c131-109">Programación de la seguridad de WCF</span><span class="sxs-lookup"><span data-stu-id="4c131-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="4c131-110">Información general del modelo de programación utilizado para proteger los mensajes.</span><span class="sxs-lookup"><span data-stu-id="4c131-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="4c131-111">Información general de la seguridad del transporte</span><span class="sxs-lookup"><span data-stu-id="4c131-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="4c131-112">Información general de cómo proteger los mensajes en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="4c131-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="4c131-113">Seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="4c131-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="4c131-114">Resume las razones para usar seguridad de nivel de mensaje en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4c131-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="4c131-115">Sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="4c131-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="4c131-116">Una explicación de las consideraciones necesarias para proteger una sesión WCF.</span><span class="sxs-lookup"><span data-stu-id="4c131-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="4c131-117">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="4c131-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="4c131-118">Explicación de algunas de las tareas comunes necesarias para la utilización de los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="4c131-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4c131-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="4c131-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="4c131-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4c131-120">Related Sections</span></span>  
 [<span data-ttu-id="4c131-121">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="4c131-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="4c131-122">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="4c131-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="4c131-123">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="4c131-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="4c131-124">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="4c131-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="4c131-125">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="4c131-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="4c131-126">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="4c131-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="4c131-127">Autorización</span><span class="sxs-lookup"><span data-stu-id="4c131-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="4c131-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c131-128">See Also</span></span>  
 [<span data-ttu-id="4c131-129">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="4c131-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="4c131-130">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="4c131-130">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
