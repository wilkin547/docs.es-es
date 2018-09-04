---
title: Seguridad en los formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: 75016e9e04cf47782add18c87f7c677931743a4e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556183"
---
# <a name="windows-forms-security"></a><span data-ttu-id="e49a9-102">Seguridad en los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e49a9-102">Windows Forms Security</span></span>
<span data-ttu-id="e49a9-103">Windows Forms incluye un modelo de seguridad que está basado en código (niveles de seguridad se establecen para el código, independientemente del usuario que ejecuta el código).</span><span class="sxs-lookup"><span data-stu-id="e49a9-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="e49a9-104">Esto es además de cualquier esquema de seguridad que pueda estar aplicada ya en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e49a9-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="e49a9-105">Estos pueden incluir en el explorador (por ejemplo, la seguridad basada en la zona de Internet Explorer) o el sistema operativo (por ejemplo, la seguridad basada en credenciales de Windows NT).</span><span class="sxs-lookup"><span data-stu-id="e49a9-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e49a9-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e49a9-106">In This Section</span></span>  
 [<span data-ttu-id="e49a9-107">Información general sobre la seguridad en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e49a9-107">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 <span data-ttu-id="e49a9-108">Explica brevemente el modelo de seguridad de .NET Framework y los pasos básicos necesarios para asegurarse de los formularios de Windows en la aplicación son seguros.</span><span class="sxs-lookup"><span data-stu-id="e49a9-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="e49a9-109">Acceso más seguro a archivos y datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e49a9-109">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="e49a9-110">Describe cómo tener acceso a archivos y datos en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="e49a9-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="e49a9-111">Impresión más segura en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e49a9-111">More Secure Printing in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="e49a9-112">Describe cómo tener acceso a características de impresión en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="e49a9-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="e49a9-113">Consideraciones de seguridad adicionales en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e49a9-113">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="e49a9-114">Describe cómo manipular ventanas, usando el Portapapeles y realizar llamadas a código no administrado en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="e49a9-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e49a9-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e49a9-115">Related Sections</span></span>  
 [<span data-ttu-id="e49a9-116">NIB: Directiva de seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="e49a9-116">NIB: Default Security Policy</span></span>](https://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 <span data-ttu-id="e49a9-117">Enumera los permisos concedidos en los conjuntos de permisos de plena confianza, Intranet Local e Internet.</span><span class="sxs-lookup"><span data-stu-id="e49a9-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 [<span data-ttu-id="e49a9-118">NIB: Administración de directiva de seguridad General</span><span class="sxs-lookup"><span data-stu-id="e49a9-118">NIB: General Security Policy Administration</span></span>](https://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 <span data-ttu-id="e49a9-119">Proporciona información sobre la administración de la directiva de seguridad de .NET Framework y la concesión de permisos.</span><span class="sxs-lookup"><span data-stu-id="e49a9-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="e49a9-120">Permisos peligrosos y administración de directivas</span><span class="sxs-lookup"><span data-stu-id="e49a9-120">Dangerous Permissions and Policy Administration</span></span>](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="e49a9-121">Se describen algunos de los permisos de.NET Framework que pueden permitir potencialmente burlar el sistema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e49a9-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="e49a9-122">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="e49a9-122">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="e49a9-123">Vínculos a temas que explican los procedimientos recomendados para escribir código seguro para .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e49a9-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 [<span data-ttu-id="e49a9-124">NIB: Solicitud de permisos</span><span class="sxs-lookup"><span data-stu-id="e49a9-124">NIB: Requesting Permissions</span></span>](https://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 <span data-ttu-id="e49a9-125">Describe el uso de atributos para que el tiempo de ejecución sepa qué permisos necesita ejecutar su código.</span><span class="sxs-lookup"><span data-stu-id="e49a9-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="e49a9-126">Conceptos clave de seguridad</span><span class="sxs-lookup"><span data-stu-id="e49a9-126">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="e49a9-127">Vínculos a temas que tratan los aspectos básicos de seguridad del código.</span><span class="sxs-lookup"><span data-stu-id="e49a9-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 <span data-ttu-id="e49a9-128">[Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md) (Conceptos básicos sobre la seguridad de acceso del código)</span><span class="sxs-lookup"><span data-stu-id="e49a9-128">[Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md)</span></span>  
 <span data-ttu-id="e49a9-129">Explica los fundamentos de trabajar con la directiva de seguridad de tiempo de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e49a9-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 [<span data-ttu-id="e49a9-130">NIB: Determinar cuándo se debe modificar la directiva de seguridad</span><span class="sxs-lookup"><span data-stu-id="e49a9-130">NIB: Determining When to Modify Security Policy</span></span>](https://msdn.microsoft.com/library/af749b17-e461-409d-84b9-a3d44789db16)  
 <span data-ttu-id="e49a9-131">Explica cómo determinar cuándo las aplicaciones necesitan desviarse de la directiva de seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e49a9-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 [<span data-ttu-id="e49a9-132">NIB: Implementación de la directiva de seguridad</span><span class="sxs-lookup"><span data-stu-id="e49a9-132">NIB: Deploying Security Policy</span></span>](https://msdn.microsoft.com/library/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 <span data-ttu-id="e49a9-133">Describe la mejor manera de implementar cambios de directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="e49a9-133">Discusses the best manner for deploying security policy changes.</span></span>
