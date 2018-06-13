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
ms.openlocfilehash: 3dc4397319d42760a1886a96377a949da6ae63be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542241"
---
# <a name="windows-forms-security"></a><span data-ttu-id="7b319-102">Seguridad en los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7b319-102">Windows Forms Security</span></span>
<span data-ttu-id="7b319-103">Windows Forms incluye un modelo de seguridad que está basada en código (niveles de seguridad se establecen para el código, sin tener en cuenta el usuario que ejecuta el código).</span><span class="sxs-lookup"><span data-stu-id="7b319-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="7b319-104">Esto es además de los esquemas de seguridad que pueden estar en su lugar ya en el sistema del equipo.</span><span class="sxs-lookup"><span data-stu-id="7b319-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="7b319-105">Estos pueden incluirlos en el explorador (por ejemplo, la seguridad basada en la zona en Internet Explorer) o el sistema operativo (por ejemplo, la seguridad basada en la credencial de Windows NT).</span><span class="sxs-lookup"><span data-stu-id="7b319-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b319-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7b319-106">In This Section</span></span>  
 [<span data-ttu-id="7b319-107">Información general sobre la seguridad en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7b319-107">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 <span data-ttu-id="7b319-108">Se explican brevemente el modelo de seguridad de .NET Framework y los pasos básicos necesarios para asegurarse de los formularios de Windows en la aplicación sean seguros.</span><span class="sxs-lookup"><span data-stu-id="7b319-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="7b319-109">Acceso más seguro a archivos y datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7b319-109">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="7b319-110">Describe cómo obtener acceso a archivos y datos en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="7b319-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="7b319-111">Impresión más segura en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7b319-111">More Secure Printing in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="7b319-112">Describe cómo obtener acceso a características de impresión en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="7b319-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="7b319-113">Consideraciones de seguridad adicionales en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7b319-113">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="7b319-114">Describe cómo manipular ventanas, usar el Portapapeles y realizar llamadas a código no administrado en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="7b319-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7b319-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7b319-115">Related Sections</span></span>  
 [<span data-ttu-id="7b319-116">NIB: Directiva de seguridad predeterminada</span><span class="sxs-lookup"><span data-stu-id="7b319-116">NIB: Default Security Policy</span></span>](http://msdn.microsoft.com/library/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 <span data-ttu-id="7b319-117">Se enumeran los permisos concedidos en los conjuntos de permisos de plena confianza, Intranet Local e Internet.</span><span class="sxs-lookup"><span data-stu-id="7b319-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 [<span data-ttu-id="7b319-118">NIB: Administración de directiva de seguridad General</span><span class="sxs-lookup"><span data-stu-id="7b319-118">NIB: General Security Policy Administration</span></span>](http://msdn.microsoft.com/library/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 <span data-ttu-id="7b319-119">Proporciona información sobre la administración de la directiva de seguridad de .NET Framework y la concesión de permisos.</span><span class="sxs-lookup"><span data-stu-id="7b319-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="7b319-120">Permisos peligrosos y administración de directivas</span><span class="sxs-lookup"><span data-stu-id="7b319-120">Dangerous Permissions and Policy Administration</span></span>](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="7b319-121">Describe algunos de los permisos de.NET Framework que pueden permitir potencialmente burlar el sistema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7b319-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="7b319-122">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="7b319-122">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="7b319-123">Vínculos a temas que explican los procedimientos recomendados para escribir código seguro para .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b319-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 [<span data-ttu-id="7b319-124">NIB: Solicitud de permisos</span><span class="sxs-lookup"><span data-stu-id="7b319-124">NIB: Requesting Permissions</span></span>](http://msdn.microsoft.com/library/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 <span data-ttu-id="7b319-125">Describe el uso de atributos para permitir que el tiempo de ejecución saber qué permisos necesita ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="7b319-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="7b319-126">Conceptos clave de seguridad</span><span class="sxs-lookup"><span data-stu-id="7b319-126">Key Security Concepts</span></span>](../../../docs/standard/security/key-security-concepts.md)  
 <span data-ttu-id="7b319-127">Vínculos a temas que tratan los aspectos básicos de seguridad del código.</span><span class="sxs-lookup"><span data-stu-id="7b319-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 <span data-ttu-id="7b319-128">[Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md) (Conceptos básicos sobre la seguridad de acceso del código)</span><span class="sxs-lookup"><span data-stu-id="7b319-128">[Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md)</span></span>  
 <span data-ttu-id="7b319-129">Describe los conceptos básicos sobre cómo trabajar con la directiva de seguridad de tiempo de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7b319-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 [<span data-ttu-id="7b319-130">NIB: Determinar cuándo se modifica la directiva de seguridad</span><span class="sxs-lookup"><span data-stu-id="7b319-130">NIB: Determining When to Modify Security Policy</span></span>](http://msdn.microsoft.com/library/af749b17-e461-409d-84b9-a3d44789db16)  
 <span data-ttu-id="7b319-131">Explica cómo determinar cuándo las aplicaciones deben divergir de la directiva de seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7b319-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 [<span data-ttu-id="7b319-132">NIB: Implementación de la directiva de seguridad</span><span class="sxs-lookup"><span data-stu-id="7b319-132">NIB: Deploying Security Policy</span></span>](http://msdn.microsoft.com/library/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 <span data-ttu-id="7b319-133">Describe la manera recomendada para implementar los cambios de directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7b319-133">Discusses the best manner for deploying security policy changes.</span></span>
