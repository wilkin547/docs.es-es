---
title: Cambios de seguridad en .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: af2869e5ca3b41778c094b7a78a9493e74868811
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204503"
---
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="12b9a-102">Cambios de seguridad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="12b9a-102">Security Changes in the .NET Framework</span></span>

<span data-ttu-id="12b9a-103">El cambio más importante en la seguridad de la .NET Framework 4,5 es con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="12b9a-103">The most important change to security in the .NET Framework 4.5 is in strong naming.</span></span> <span data-ttu-id="12b9a-104">Consulte [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) para obtener una descripción de estos cambios.</span><span class="sxs-lookup"><span data-stu-id="12b9a-104">See [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
<span data-ttu-id="12b9a-105">.NET Framework proporciona un modelo de seguridad de dos niveles para las aplicaciones administradas.</span><span class="sxs-lookup"><span data-stu-id="12b9a-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> <span data-ttu-id="12b9a-106">Las aplicaciones de la tienda Windows 8. x se ejecutan en un contenedor de seguridad de Windows que limita el acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="12b9a-106">Windows 8.x Store apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="12b9a-107">Dentro de ese contenedor, la ejecución de las aplicaciones administradas es de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="12b9a-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="12b9a-108">Desde la perspectiva de la seguridad de acceso del código (CAS), no hay nada que un desarrollador pueda hacer para elevar los privilegios.</span><span class="sxs-lookup"><span data-stu-id="12b9a-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="12b9a-109">Para obtener información sobre los privilegios concedidos por Windows, consulte [Declaraciones de funcionalidades de las aplicaciones (aplicaciones de la Tienda Windows)](https://go.microsoft.com/fwlink/?LinkId=230436) en el Centro de desarrollo de Windows.</span><span class="sxs-lookup"><span data-stu-id="12b9a-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="12b9a-110">Para obtener información sobre cómo crear una aplicación de la tienda Windows 8. x, consulte [crear la primera C# aplicación de la tienda windows con o Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span><span class="sxs-lookup"><span data-stu-id="12b9a-110">For information about creating a Windows 8.x Store app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span></span>
