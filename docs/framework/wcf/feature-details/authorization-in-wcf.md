---
title: Autorización en WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 8e7632dda1a1bd2b60b71c385ad58c23e4207534
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532108"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="ff4d3-102">Autorización en WCF</span><span class="sxs-lookup"><span data-stu-id="ff4d3-102">Authorization in WCF</span></span>
<span data-ttu-id="ff4d3-103">La autorización es el proceso para controlar el acceso y los derechos a los recursos, como servicios o archivos.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="ff4d3-104">Los temas de esta sección muestran cómo realizar esta tarea básica en Windows Communication Foundation (WCF) en una variedad de formas.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff4d3-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ff4d3-105">In This Section</span></span>  
 [<span data-ttu-id="ff4d3-106">Mecanismos de control de acceso</span><span class="sxs-lookup"><span data-stu-id="ff4d3-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="ff4d3-107">Proporciona una descripción breve de los mecanismos de autorización en WCF y usos sugeridos.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="ff4d3-108">Cómo restringir el acceso con la clase PrincipalPermissionAttribute Class</span><span class="sxs-lookup"><span data-stu-id="ff4d3-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="ff4d3-109">Muestra el proceso de restringir el acceso a un servicio con <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="ff4d3-110">Uso del proveedor de funciones ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="ff4d3-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="ff4d3-111">Abarca la configuración de un servicio para permitirle utilizar la característica de proveedor de funciones de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff4d3-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="ff4d3-112">Uso del proveedor de funciones del administrador de autorización de ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="ff4d3-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="ff4d3-113"> puede usar el Administrador de autorización para administrar la autorización para un sitio web.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-113"> can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="ff4d3-114">WCF de forma similar puede aprovechar el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]combinación /Authorization Manager para la autorización de clientes.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-114">WCF can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="ff4d3-115">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="ff4d3-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="ff4d3-116">Explica los fundamentos para utilizar la infraestructura del modelo de identidad para la autorización basada en demandas.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="ff4d3-117">Delegación y suplantación</span><span class="sxs-lookup"><span data-stu-id="ff4d3-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="ff4d3-118">Explica la diferencia entre la delegación y la suplantación.</span><span class="sxs-lookup"><span data-stu-id="ff4d3-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ff4d3-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="ff4d3-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="ff4d3-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="ff4d3-120">Related Sections</span></span>  
 [<span data-ttu-id="ff4d3-121">Autenticación</span><span class="sxs-lookup"><span data-stu-id="ff4d3-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="ff4d3-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff4d3-122">See Also</span></span>  
 [<span data-ttu-id="ff4d3-123">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="ff4d3-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="ff4d3-124">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="ff4d3-124">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
