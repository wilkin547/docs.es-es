---
title: Permisos peligrosos y administración de directivas
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b89792f9579da2d72c0a7f90a983308b172093fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33390726"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="6e2b0-102">Permisos peligrosos y administración de directivas</span><span class="sxs-lookup"><span data-stu-id="6e2b0-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="6e2b0-103">Varias de las operaciones protegidas para las que .NET Framework proporciona permisos pueden permitir potencialmente burlar el sistema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="6e2b0-104">Estos peligrosos permisos solo se deben conceder a código de confianza y únicamente cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="6e2b0-105">No suele haber ninguna defensa contra código malintencionado si se le conceden estos permisos.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e2b0-106">En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]se introdujeron cambios importantes tanto en el modelo de seguridad de .NET Framework como en la terminología.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="6e2b0-107">Para obtener más información sobre estos cambios, consulte [cambios de seguridad](../../../docs/framework/security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="6e2b0-107">For more information about these changes, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="6e2b0-108">Estos permisos peligrosos se explican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="6e2b0-109">Permiso</span><span class="sxs-lookup"><span data-stu-id="6e2b0-109">Permission</span></span>|<span data-ttu-id="6e2b0-110">Riesgo potencial</span><span class="sxs-lookup"><span data-stu-id="6e2b0-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="6e2b0-111">Permite que el código administrado llame a código no administrado, lo que a menudo es peligroso.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="6e2b0-112">Sin esta comprobación, el código puede hacer cualquier cosa.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="6e2b0-113">La evidencia no validada puede burlar la directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="6e2b0-114">La capacidad de modificar la directiva de seguridad puede deshabilitar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="6e2b0-115">El uso de serialización puede eludir los mecanismos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="6e2b0-116">Para obtener información más detallada, vea [Seguridad y serialización](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="6e2b0-116">For details, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="6e2b0-117">La capacidad de establecer la entidad de seguridad actual puede engañar a la seguridad basada en roles.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="6e2b0-118">La manipulación de subprocesos es peligrosa debido al estado de seguridad asociado a ellos.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="6e2b0-119">Puede utilizar miembros privados para anular los mecanismos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="6e2b0-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e2b0-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e2b0-120">See Also</span></span>  
 [<span data-ttu-id="6e2b0-121">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="6e2b0-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
