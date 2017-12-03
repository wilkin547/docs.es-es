---
title: "Cómo: Crear una identidad de entidad de seguridad personalizada"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IPrincipal
- IAuthorizationPolicy
- PrincipalPermissionMode
- PrincipalPermissionAttribute
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 90dbd173293a91ab4c2fb1aa34c0aefc5e4ffefa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-principal-identity"></a><span data-ttu-id="416a4-102">Cómo: Crear una identidad de entidad de seguridad personalizada</span><span class="sxs-lookup"><span data-stu-id="416a4-102">How to: Create a Custom Principal Identity</span></span>
<span data-ttu-id="416a4-103"><xref:System.Security.Permissions.PrincipalPermissionAttribute> es un medio declarativo para controlar el acceso a los métodos de servicio.</span><span class="sxs-lookup"><span data-stu-id="416a4-103">The <xref:System.Security.Permissions.PrincipalPermissionAttribute> is a declarative means of controlling access to service methods.</span></span> <span data-ttu-id="416a4-104">Al utilizar este atributo, la enumeración <xref:System.ServiceModel.Description.PrincipalPermissionMode> especifica el modo para realizar las comprobaciones de la autorización.</span><span class="sxs-lookup"><span data-stu-id="416a4-104">When using this attribute, the <xref:System.ServiceModel.Description.PrincipalPermissionMode> enumeration specifies the mode for performing authorization checks.</span></span> <span data-ttu-id="416a4-105">Cuando este modo está establecido en <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, permite al usuario especificar una clase <xref:System.Security.Principal.IPrincipal> personalizada devuelta por la propiedad <xref:System.Threading.Thread.CurrentPrincipal%2A>.</span><span class="sxs-lookup"><span data-stu-id="416a4-105">When this mode is set to <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom>, it enables the user to specify a custom <xref:System.Security.Principal.IPrincipal> class returned by the <xref:System.Threading.Thread.CurrentPrincipal%2A> property.</span></span> <span data-ttu-id="416a4-106">Este tema muestra el escenario cuando <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> se utiliza en combinación con una directiva de autorización personalizada y una entidad de seguridad personalizada.</span><span class="sxs-lookup"><span data-stu-id="416a4-106">This topic illustrates the scenario when <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> is used in combination with a custom authorization policy and a custom principal.</span></span>  
  
 <span data-ttu-id="416a4-107">Para obtener más información sobre el uso de la <xref:System.Security.Permissions.PrincipalPermissionAttribute>, consulte [Cómo: restringir el acceso con la clase PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="416a4-107">For more information about using the <xref:System.Security.Permissions.PrincipalPermissionAttribute>, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="416a4-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="416a4-108">Example</span></span>  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="416a4-109">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="416a4-109">Compiling the Code</span></span>  
 <span data-ttu-id="416a4-110">Hace referencia a los siguientes espacios de nombres necesarios para compilar el código:</span><span class="sxs-lookup"><span data-stu-id="416a4-110">References to the following namespaces are needed to compile the code:</span></span>  
  
-   <xref:System>  
  
-   <xref:System.Collections.Generic>  
  
-   <xref:System.Security.Permissions>  
  
-   <xref:System.Security.Principal>  
  
-   <xref:System.Threading>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Description>  
  
-   <xref:System.IdentityModel.Claims>  
  
-   <xref:System.IdentityModel.Policy>  
  
## <a name="see-also"></a><span data-ttu-id="416a4-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="416a4-111">See Also</span></span>  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
 [<span data-ttu-id="416a4-112">Cómo: utilizar el proveedor de funciones de ASP.NET con un servicio</span><span class="sxs-lookup"><span data-stu-id="416a4-112">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [<span data-ttu-id="416a4-113">Cómo restringir el acceso con la clase PrincipalPermissionAttribute Class</span><span class="sxs-lookup"><span data-stu-id="416a4-113">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)
