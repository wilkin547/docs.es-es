---
title: Reemplazar un objeto Principal
ms.date: 07/15/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET], replacing principal objects
- security [.NET], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
ms.openlocfilehash: fced91aef991bc228e65128d5e8d69e6a46588e5
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557104"
---
# <a name="replacing-a-principal-object"></a><span data-ttu-id="991e0-102">Reemplazar un objeto Principal</span><span class="sxs-lookup"><span data-stu-id="991e0-102">Replacing a Principal Object</span></span>

<span data-ttu-id="991e0-103">Las aplicaciones que ofrecen servicios de autenticación deben poder reemplazar el objeto **Principal** (<xref:System.Security.Principal.IPrincipal>) de un subproceso determinado.</span><span class="sxs-lookup"><span data-stu-id="991e0-103">Applications that provide authentication services must be able to replace the **Principal** object (<xref:System.Security.Principal.IPrincipal>) for a given thread.</span></span> <span data-ttu-id="991e0-104">Además, el sistema de seguridad debe ayudar a proteger la capacidad de reemplazar objetos **Principal** , porque un objeto **Principal** incorrecto asociado de forma malintencionada pone en peligro la seguridad de la aplicación mediante la notificación de una identidad o un rol falsos.</span><span class="sxs-lookup"><span data-stu-id="991e0-104">Furthermore, the security system must help protect the ability to replace **Principal** objects because a maliciously attached, incorrect **Principal** compromises the security of your application by claiming an untrue identity or role.</span></span> <span data-ttu-id="991e0-105">Por lo tanto, las aplicaciones que requieren la capacidad de reemplazar objetos **Principal** necesitan que se les conceda el objeto <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> para el control de la entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="991e0-105">Therefore, applications that require the ability to replace **Principal** objects must be granted the <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> object for principal control.</span></span> <span data-ttu-id="991e0-106">(Tenga en cuenta que este permiso no se requiere para realizar comprobaciones de seguridad basada en roles o para crear objetos **Principal** ).</span><span class="sxs-lookup"><span data-stu-id="991e0-106">(Note that this permission is not required for performing role-based security checks or for creating **Principal** objects.)</span></span>  
  
<span data-ttu-id="991e0-107">El objeto **Principal** actual se puede reemplazar realizando las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="991e0-107">The current **Principal** object can be replaced by performing the following tasks:</span></span>  
  
1. <span data-ttu-id="991e0-108">Cree el objeto **Principal** de reemplazo y el objeto **Identity** asociado.</span><span class="sxs-lookup"><span data-stu-id="991e0-108">Create the replacement **Principal** object and associated **Identity** object.</span></span>  
  
2. <span data-ttu-id="991e0-109">Adjunte el nuevo objeto **Principal** al contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="991e0-109">Attach the new **Principal** object to the call context.</span></span>  
  
## <a name="example"></a><span data-ttu-id="991e0-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="991e0-110">Example</span></span>

<span data-ttu-id="991e0-111">En el ejemplo siguiente se muestra cómo se crea un objeto de entidad de seguridad genérico y cómo usarlo para establecer la entidad de seguridad de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="991e0-111">The following example shows how to create a generic principal object and use it to set the principal of a thread.</span></span>  
  
[!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
[!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="991e0-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="991e0-112">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [<span data-ttu-id="991e0-113">Objetos Principal e Identity</span><span class="sxs-lookup"><span data-stu-id="991e0-113">Principal and Identity Objects</span></span>](principal-and-identity-objects.md)
- [<span data-ttu-id="991e0-114">Seguridad de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="991e0-114">ASP.NET Core Security</span></span>](/aspnet/core/security/)
