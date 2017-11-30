---
title: "Autorización en WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0c2afafa1d645ec0e95b7b41ff8389873969c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="2d76f-102">Autorización en WCF</span><span class="sxs-lookup"><span data-stu-id="2d76f-102">Authorization in WCF</span></span>
<span data-ttu-id="2d76f-103">La autorización es el proceso para controlar el acceso y los derechos a los recursos, como servicios o archivos.</span><span class="sxs-lookup"><span data-stu-id="2d76f-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="2d76f-104">Los temas en esta presentación de la sección le muestran cómo realizar esta tarea básica en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en una gran variedad de maneras.</span><span class="sxs-lookup"><span data-stu-id="2d76f-104">The topics in this section show you how to perform this basic task in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2d76f-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="2d76f-105">In This Section</span></span>  
 [<span data-ttu-id="2d76f-106">Mecanismos de Control de acceso</span><span class="sxs-lookup"><span data-stu-id="2d76f-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="2d76f-107">Proporciona un esquema breve de los mecanismos de la autorización en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]y los usos sugeridos.</span><span class="sxs-lookup"><span data-stu-id="2d76f-107">Provides a brief outline of the authorization mechanisms in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and suggested uses.</span></span>  
  
 [<span data-ttu-id="2d76f-108">Cómo restringir el acceso con la clase PrincipalPermissionAttribute Class</span><span class="sxs-lookup"><span data-stu-id="2d76f-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="2d76f-109">Muestra el proceso de restringir el acceso a un servicio con <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2d76f-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="2d76f-110">Cómo: utilizar el proveedor de funciones de ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="2d76f-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="2d76f-111">Abarca la configuración de un servicio para permitirle utilizar la característica de proveedor de funciones de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d76f-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="2d76f-112">Cómo: utilizar el proveedor de funciones de administrador de autorización de ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="2d76f-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="2d76f-113"> puede usar el Administrador de autorización para administrar la autorización para un sitio web.</span><span class="sxs-lookup"><span data-stu-id="2d76f-113"> can use the Authorization Manager to manage authorization for a Web site.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="2d76f-114"> puede aprovechar igualmente la combinación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Administrador de autorización para la autorización de clientes.</span><span class="sxs-lookup"><span data-stu-id="2d76f-114"> can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="2d76f-115">Administración de notificaciones y autorización con el modelo de identidad</span><span class="sxs-lookup"><span data-stu-id="2d76f-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="2d76f-116">Explica los fundamentos para utilizar la infraestructura del modelo de identidad para la autorización basada en demandas.</span><span class="sxs-lookup"><span data-stu-id="2d76f-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="2d76f-117">Delegación y suplantación</span><span class="sxs-lookup"><span data-stu-id="2d76f-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="2d76f-118">Explica la diferencia entre la delegación y la suplantación.</span><span class="sxs-lookup"><span data-stu-id="2d76f-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2d76f-119">Referencia</span><span class="sxs-lookup"><span data-stu-id="2d76f-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="2d76f-120">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="2d76f-120">Related Sections</span></span>  
 [<span data-ttu-id="2d76f-121">Autenticación</span><span class="sxs-lookup"><span data-stu-id="2d76f-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="2d76f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d76f-122">See Also</span></span>  
 [<span data-ttu-id="2d76f-123">Información general sobre seguridad</span><span class="sxs-lookup"><span data-stu-id="2d76f-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="2d76f-124">Modelo de seguridad de Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="2d76f-124">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
