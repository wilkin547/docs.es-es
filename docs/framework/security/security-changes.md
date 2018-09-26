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
ms.openlocfilehash: c62a469b3e31283e5790c747092a8fe504ef8c2a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200560"
---
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="4e3bd-102">Cambios de seguridad en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4e3bd-102">Security Changes in the .NET Framework</span></span>
<span data-ttu-id="4e3bd-103">El cambio más importante en la seguridad de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] es la adopción de nombres seguros.</span><span class="sxs-lookup"><span data-stu-id="4e3bd-103">The most important change to security in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is in strong naming.</span></span> <span data-ttu-id="4e3bd-104">Consulte [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) para obtener una descripción de estos cambios.</span><span class="sxs-lookup"><span data-stu-id="4e3bd-104">See [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
 <span data-ttu-id="4e3bd-105">.NET Framework proporciona un modelo de seguridad de dos niveles para las aplicaciones administradas.</span><span class="sxs-lookup"><span data-stu-id="4e3bd-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> <span data-ttu-id="4e3bd-106">Las aplicaciones de la[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] se ejecutan en un contenedor de seguridad de Windows que restringe el acceso a los recursos.</span><span class="sxs-lookup"><span data-stu-id="4e3bd-106">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="4e3bd-107">Dentro de ese contenedor, la ejecución de las aplicaciones administradas es de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="4e3bd-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="4e3bd-108">Desde la perspectiva de la seguridad de acceso del código (CAS), no hay nada que un desarrollador pueda hacer para elevar los privilegios.</span><span class="sxs-lookup"><span data-stu-id="4e3bd-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="4e3bd-109">Para obtener información sobre los privilegios concedidos por Windows, consulte [Declaraciones de funcionalidades de las aplicaciones (aplicaciones de la Tienda Windows)](https://go.microsoft.com/fwlink/?LinkId=230436) en el Centro de desarrollo de Windows.</span><span class="sxs-lookup"><span data-stu-id="4e3bd-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="4e3bd-110">Para obtener información sobre cómo crear una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] , consulte [Crear la primera aplicación de la Tienda Windows con C# o Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span><span class="sxs-lookup"><span data-stu-id="4e3bd-110">For information about creating a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span></span>
