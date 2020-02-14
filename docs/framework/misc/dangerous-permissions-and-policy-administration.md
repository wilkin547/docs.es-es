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
ms.openlocfilehash: 026697feec7afe950628639c5e595ba0a0220b97
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217142"
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="f09e1-102">Permisos peligrosos y administración de directivas</span><span class="sxs-lookup"><span data-stu-id="f09e1-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="f09e1-103">Varias de las operaciones protegidas para las que .NET Framework proporciona permisos pueden permitir potencialmente burlar el sistema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f09e1-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="f09e1-104">Estos peligrosos permisos solo se deben conceder a código de confianza y únicamente cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f09e1-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="f09e1-105">No suele haber ninguna defensa contra código malintencionado si se le conceden estos permisos.</span><span class="sxs-lookup"><span data-stu-id="f09e1-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f09e1-106">En el .NET Framework 4, ha habido cambios importantes en el modelo de seguridad .NET Framework y la terminología.</span><span class="sxs-lookup"><span data-stu-id="f09e1-106">In the .NET Framework 4, there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="f09e1-107">Para obtener más información sobre estos cambios, consulte [cambios de seguridad](../security/security-changes.md).</span><span class="sxs-lookup"><span data-stu-id="f09e1-107">For more information about these changes, see [Security Changes](../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="f09e1-108">Estos permisos peligrosos se explican en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f09e1-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="f09e1-109">Permiso</span><span class="sxs-lookup"><span data-stu-id="f09e1-109">Permission</span></span>|<span data-ttu-id="f09e1-110">Riesgo potencial</span><span class="sxs-lookup"><span data-stu-id="f09e1-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="f09e1-111">Permite que el código administrado llame a código no administrado, lo que a menudo es peligroso.</span><span class="sxs-lookup"><span data-stu-id="f09e1-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="f09e1-112">Sin esta comprobación, el código puede hacer cualquier cosa.</span><span class="sxs-lookup"><span data-stu-id="f09e1-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="f09e1-113">La evidencia no validada puede burlar la directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f09e1-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="f09e1-114">La capacidad de modificar la directiva de seguridad puede deshabilitar la seguridad.</span><span class="sxs-lookup"><span data-stu-id="f09e1-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="f09e1-115">El uso de serialización puede eludir los mecanismos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="f09e1-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="f09e1-116">Para obtener información más detallada, vea [Seguridad y serialización](security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="f09e1-116">For details, see [Security and Serialization](security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="f09e1-117">La capacidad de establecer la entidad de seguridad actual puede engañar a la seguridad basada en roles.</span><span class="sxs-lookup"><span data-stu-id="f09e1-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="f09e1-118">La manipulación de subprocesos es peligrosa debido al estado de seguridad asociado a ellos.</span><span class="sxs-lookup"><span data-stu-id="f09e1-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="f09e1-119">Puede utilizar miembros privados para anular los mecanismos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="f09e1-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f09e1-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f09e1-120">See also</span></span>

- [<span data-ttu-id="f09e1-121">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="f09e1-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
