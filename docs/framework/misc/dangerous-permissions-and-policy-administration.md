---
title: Permisos peligrosos y administración de directivas
description: Vea vínculos a los distintos permisos peligrosos en .NET. Estos permisos solo se deben proporcionar a código de confianza y solo cuando sea necesario.
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
ms.openlocfilehash: 1d3fb53775a4d88f9372b582189a38e18376761a
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855821"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="a4c7e-104">Permisos peligrosos y administración de directivas</span><span class="sxs-lookup"><span data-stu-id="a4c7e-104">Dangerous Permissions and Policy Administration</span></span>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="a4c7e-105">Varias de las operaciones protegidas para las que .NET Framework proporciona permisos pueden permitir potencialmente burlar el sistema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-105">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="a4c7e-106">Estos peligrosos permisos solo se deben conceder a código de confianza y únicamente cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-106">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="a4c7e-107">No suele haber ninguna defensa contra código malintencionado si se le conceden estos permisos.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-107">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a4c7e-108">En el .NET Framework 4, ha habido cambios importantes en el modelo de seguridad .NET Framework y la terminología.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-108">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="a4c7e-109">Para obtener más información sobre estos cambios, consulte [cambios de seguridad](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span><span class="sxs-lookup"><span data-stu-id="a4c7e-109">For more information about these changes, see [Security Changes](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).</span></span>  
  
 <span data-ttu-id="a4c7e-110">Estos permisos peligrosos se explican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-110">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="a4c7e-111">Permiso</span><span class="sxs-lookup"><span data-stu-id="a4c7e-111">Permission</span></span>|<span data-ttu-id="a4c7e-112">Riesgo potencial</span><span class="sxs-lookup"><span data-stu-id="a4c7e-112">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="a4c7e-113">Permite que el código administrado llame a código no administrado, lo que a menudo es peligroso.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-113">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="a4c7e-114">Sin esta comprobación, el código puede hacer cualquier cosa.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-114">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="a4c7e-115">La evidencia no validada puede burlar la directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-115">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="a4c7e-116">La capacidad de modificar la directiva de seguridad puede deshabilitar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-116">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="a4c7e-117">El uso de serialización puede eludir los mecanismos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-117">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="a4c7e-118">Para obtener información más detallada, vea [Seguridad y serialización](security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="a4c7e-118">For details, see [Security and Serialization](security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="a4c7e-119">La capacidad de establecer la entidad de seguridad actual puede engañar a la seguridad basada en roles.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-119">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="a4c7e-120">La manipulación de subprocesos es peligrosa debido al estado de seguridad asociado a ellos.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-120">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="a4c7e-121">Puede utilizar miembros privados para anular los mecanismos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="a4c7e-121">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4c7e-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a4c7e-122">See also</span></span>

- [<span data-ttu-id="a4c7e-123">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="a4c7e-123">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
