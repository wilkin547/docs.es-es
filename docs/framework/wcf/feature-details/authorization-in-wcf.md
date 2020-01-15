---
title: Autorización en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 0097adc3d9677d9ce5595a3ac632b51d94d53f6f
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964683"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="c5ade-102">Autorización en WCF</span><span class="sxs-lookup"><span data-stu-id="c5ade-102">Authorization in WCF</span></span>
<span data-ttu-id="c5ade-103">La autorización es el proceso para controlar el acceso y los derechos a los recursos, como servicios o archivos.</span><span class="sxs-lookup"><span data-stu-id="c5ade-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="c5ade-104">En los temas de esta sección se muestra cómo realizar esta tarea básica en Windows Communication Foundation (WCF) de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="c5ade-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c5ade-105">Esta sección</span><span class="sxs-lookup"><span data-stu-id="c5ade-105">In This Section</span></span>  
 [<span data-ttu-id="c5ade-106">Mecanismos de control de acceso</span><span class="sxs-lookup"><span data-stu-id="c5ade-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="c5ade-107">Proporciona una breve descripción de los mecanismos de autorización en WCF y los usos sugeridos.</span><span class="sxs-lookup"><span data-stu-id="c5ade-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="c5ade-108">Cómo restringir el acceso con la clase PrincipalPermissionAttribute Class</span><span class="sxs-lookup"><span data-stu-id="c5ade-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="c5ade-109">Muestra el proceso de restringir el acceso a un servicio con <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c5ade-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="c5ade-110">Uso del proveedor de funciones ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="c5ade-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="c5ade-111">Le guía a través de la configuración de un servicio para que pueda usar la característica de proveedor de roles de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c5ade-111">Walks through the configuration of a service to enable it to use the role provider feature of ASP.NET.</span></span>  
  
 [<span data-ttu-id="c5ade-112">Uso del proveedor de funciones del administrador de autorización de ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="c5ade-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 <span data-ttu-id="c5ade-113">ASP.NET puede usar el administrador de autorización para administrar la autorización de un sitio Web.</span><span class="sxs-lookup"><span data-stu-id="c5ade-113">ASP.NET can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="c5ade-114">WCF puede aprovechar de forma similar la combinación de ASP.NET/Authorization Manager para la autorización de clientes.</span><span class="sxs-lookup"><span data-stu-id="c5ade-114">WCF can similarly leverage the ASP.NET/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="c5ade-115">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="c5ade-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="c5ade-116">Explica los fundamentos para utilizar la infraestructura del modelo de identidad para la autorización basada en demandas.</span><span class="sxs-lookup"><span data-stu-id="c5ade-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="c5ade-117">Delegación y suplantación</span><span class="sxs-lookup"><span data-stu-id="c5ade-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="c5ade-118">Explica la diferencia entre la delegación y la suplantación.</span><span class="sxs-lookup"><span data-stu-id="c5ade-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c5ade-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="c5ade-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="c5ade-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c5ade-120">Related Sections</span></span>  
 [<span data-ttu-id="c5ade-121">Autenticación</span><span class="sxs-lookup"><span data-stu-id="c5ade-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="c5ade-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5ade-122">See also</span></span>

- [<span data-ttu-id="c5ade-123">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="c5ade-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="c5ade-124">[Modelo de seguridad para Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c5ade-124">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
