---
title: Protección de servicios y clientes
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: e455c7a48e1484d5acdcc5f6cdc9098997a3ba83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61990943"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="cf7af-102">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="cf7af-102">Securing Services and Clients</span></span>
<span data-ttu-id="cf7af-103">La información de esta sección se centra en programar la seguridad en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cf7af-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="cf7af-104">Generalmente, esto incluye la selección de un enlace proporcionado por el sistema adecuado, el establecimiento de las propiedades del elemento de seguridad y, a continuación, el establecimiento de las propiedades de los comportamientos del servicio que rigen la recuperación de las credenciales utilizadas por el servicio o el cliente.</span><span class="sxs-lookup"><span data-stu-id="cf7af-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="cf7af-105">Estas técnicas abarcan los requisitos de seguridad de la mayoría de los usuarios para la mayoría de los escenarios, como se muestra en [escenarios comunes de seguridad](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="cf7af-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="cf7af-106">Si su escenario requiere más capacidades, consulte primero [capacidades de seguridad con enlaces personalizados](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); si una solución no es evidente, consulte [extender seguridad](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="cf7af-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="cf7af-107">Si está creando (o interopera con) un sistema que utiliza notificaciones enriquecidas, vea los temas de [autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="cf7af-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cf7af-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="cf7af-108">In This Section</span></span>  
 [<span data-ttu-id="cf7af-109">Programación de la seguridad de WCF</span><span class="sxs-lookup"><span data-stu-id="cf7af-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="cf7af-110">Información general del modelo de programación utilizado para proteger los mensajes.</span><span class="sxs-lookup"><span data-stu-id="cf7af-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="cf7af-111">Información general de la seguridad del transporte</span><span class="sxs-lookup"><span data-stu-id="cf7af-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="cf7af-112">Información general de cómo proteger los mensajes en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="cf7af-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="cf7af-113">Seguridad de los mensajes</span><span class="sxs-lookup"><span data-stu-id="cf7af-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="cf7af-114">Se resumen las razones para usar seguridad de nivel de mensaje en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cf7af-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="cf7af-115">Sesiones seguras</span><span class="sxs-lookup"><span data-stu-id="cf7af-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="cf7af-116">Una explicación de las consideraciones necesarias para proteger una sesión WCF.</span><span class="sxs-lookup"><span data-stu-id="cf7af-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="cf7af-117">Trabajo con certificados</span><span class="sxs-lookup"><span data-stu-id="cf7af-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="cf7af-118">Explicación de algunas de las tareas comunes necesarias para la utilización de los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="cf7af-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cf7af-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="cf7af-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="cf7af-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="cf7af-120">Related Sections</span></span>  
 [<span data-ttu-id="cf7af-121">Conceptos de seguridad</span><span class="sxs-lookup"><span data-stu-id="cf7af-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="cf7af-122">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="cf7af-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="cf7af-123">Escenarios de seguridad comunes</span><span class="sxs-lookup"><span data-stu-id="cf7af-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="cf7af-124">Enlaces y seguridad</span><span class="sxs-lookup"><span data-stu-id="cf7af-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="cf7af-125">Funcionalidades de seguridad con enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="cf7af-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="cf7af-126">Extensión de la seguridad</span><span class="sxs-lookup"><span data-stu-id="cf7af-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="cf7af-127">Autorización</span><span class="sxs-lookup"><span data-stu-id="cf7af-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="cf7af-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf7af-128">See also</span></span>

- [<span data-ttu-id="cf7af-129">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="cf7af-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="cf7af-130">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="cf7af-130">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
