---
title: Seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: a3debf487b9b2a04277d9ce3007f28662fa4899e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734490"
---
# <a name="windows-forms-security"></a><span data-ttu-id="afb84-102">Seguridad en los formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="afb84-102">Windows Forms Security</span></span>
<span data-ttu-id="afb84-103">Windows Forms incluye un modelo de seguridad basado en código (los niveles de seguridad se establecen para el código, independientemente del usuario que ejecute el código).</span><span class="sxs-lookup"><span data-stu-id="afb84-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="afb84-104">Esto se suma a cualquier esquema de seguridad que ya exista en el sistema del equipo.</span><span class="sxs-lookup"><span data-stu-id="afb84-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="afb84-105">Pueden incluirse en el explorador (como la seguridad basada en zonas disponible en Internet Explorer) o en el sistema operativo (por ejemplo, la seguridad basada en credenciales de Windows NT).</span><span class="sxs-lookup"><span data-stu-id="afb84-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="afb84-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="afb84-106">In This Section</span></span>  
 [<span data-ttu-id="afb84-107">Información general sobre la seguridad en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="afb84-107">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)  
 <span data-ttu-id="afb84-108">Explica brevemente el modelo de seguridad de .NET Framework y los pasos básicos necesarios para asegurarse de que los Windows Forms de la aplicación sean seguros.</span><span class="sxs-lookup"><span data-stu-id="afb84-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="afb84-109">Acceso más seguro a archivos y datos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="afb84-109">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="afb84-110">Describe cómo obtener acceso a archivos y datos en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="afb84-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="afb84-111">Impresión más segura en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="afb84-111">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="afb84-112">Describe cómo obtener acceso a las características de impresión en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="afb84-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="afb84-113">Consideraciones de seguridad adicionales en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="afb84-113">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="afb84-114">Describe cómo manipular ventanas, usar el portapapeles y realizar llamadas a código no administrado en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="afb84-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="afb84-115">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="afb84-115">Related Sections</span></span>  
 <span data-ttu-id="afb84-116">[Directiva de seguridad predeterminada](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="afb84-116">[Default Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span></span>  
 <span data-ttu-id="afb84-117">Enumera los permisos predeterminados concedidos en los conjuntos de permisos plena confianza, Intranet local e Internet.</span><span class="sxs-lookup"><span data-stu-id="afb84-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 <span data-ttu-id="afb84-118">[Administración de directivas de seguridad general](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="afb84-118">[General Security Policy Administration](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span></span>  
 <span data-ttu-id="afb84-119">Proporciona información sobre la administración de la Directiva de seguridad de .NET Framework y la elevación de permisos.</span><span class="sxs-lookup"><span data-stu-id="afb84-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="afb84-120">Permisos peligrosos y administración de directivas</span><span class="sxs-lookup"><span data-stu-id="afb84-120">Dangerous Permissions and Policy Administration</span></span>](../misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="afb84-121">Describe algunos de los permisos de the.NET Framework que pueden permitir el elusión del sistema de seguridad.</span><span class="sxs-lookup"><span data-stu-id="afb84-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="afb84-122">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="afb84-122">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="afb84-123">Vínculos a temas que explican los procedimientos recomendados para escribir código de forma segura en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="afb84-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 <span data-ttu-id="afb84-124">[Solicitar permisos](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="afb84-124">[Requesting Permissions](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span></span>  
 <span data-ttu-id="afb84-125">Describe el uso de atributos para permitir que el tiempo de ejecución sepa qué permisos necesita ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="afb84-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="afb84-126">Conceptos clave de seguridad</span><span class="sxs-lookup"><span data-stu-id="afb84-126">Key Security Concepts</span></span>](../../standard/security/key-security-concepts.md)  
 <span data-ttu-id="afb84-127">Vínculos a temas que cubren los aspectos básicos de la seguridad de código.</span><span class="sxs-lookup"><span data-stu-id="afb84-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 <span data-ttu-id="afb84-128">[Code Access Security Basics](../misc/code-access-security-basics.md) (Conceptos básicos sobre la seguridad de acceso del código)</span><span class="sxs-lookup"><span data-stu-id="afb84-128">[Code Access Security Basics](../misc/code-access-security-basics.md)</span></span>  
 <span data-ttu-id="afb84-129">Describe los conceptos básicos de cómo trabajar con la Directiva de seguridad en tiempo de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="afb84-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 <span data-ttu-id="afb84-130">[Determinar cuándo se debe modificar la Directiva de seguridad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="afb84-130">[Determining When to Modify Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span></span>  
 <span data-ttu-id="afb84-131">Explica cómo determinar cuándo es necesario que las aplicaciones divergen de la Directiva de seguridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="afb84-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 <span data-ttu-id="afb84-132">[Implementación de la Directiva de seguridad](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="afb84-132">[Deploying Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span></span>  
 <span data-ttu-id="afb84-133">Describe la mejor manera de implementar los cambios de la Directiva de seguridad.</span><span class="sxs-lookup"><span data-stu-id="afb84-133">Discusses the best manner for deploying security policy changes.</span></span>
