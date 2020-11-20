---
title: 'NETSDK1079: El paquete Microsoft.AspNetCore.All no se admite cuando el destino es .NET Core 3.0 o posterior.'
description: Procedimiento para resolver la migración fuera de Microsoft.AspNetCore.App
author: dsplaisted
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1079
ms.openlocfilehash: e0b7aba909dbd2931f755238a2de2418d294751d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445707"
---
# <a name="netsdk1079-the-microsoftaspnetcoreall-package-is-not-supported-when-targeting-net-core-30-or-higher"></a><span data-ttu-id="e2d1b-103">NETSDK1079: El paquete Microsoft.AspNetCore.All no se admite cuando el destino es .NET Core 3.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="e2d1b-103">NETSDK1079: The Microsoft.AspNetCore.All package is not supported when targeting .NET Core 3.0 or higher.</span></span>

<span data-ttu-id="e2d1b-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.100 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="e2d1b-104">**This article applies to:** ✔️ .NET Core SDK 3.1.100 and later versions</span></span>

<span data-ttu-id="e2d1b-105">Es posible que reciba este mensaje de error en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="e2d1b-105">You may receive this error message when:</span></span>

- <span data-ttu-id="e2d1b-106">Puede redestinar un proyecto de ASP.NET Core de .NET Core 2.2 o anterior a .NET Core 3.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="e2d1b-106">You retarget an ASP.NET Core project from .NET Core 2.2 or earlier to .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="e2d1b-107">El proyecto usa el paquete Microsoft.AspNetCore.All.</span><span class="sxs-lookup"><span data-stu-id="e2d1b-107">The project uses the Microsoft.AspNetCore.All package.</span></span>

<span data-ttu-id="e2d1b-108">Quite `PackageReference` para Microsoft.AspNetCore.All.</span><span class="sxs-lookup"><span data-stu-id="e2d1b-108">Remove the `PackageReference` for Microsoft.AspNetCore.All.</span></span>  <span data-ttu-id="e2d1b-109">También es posible que deba agregar referencias para los paquetes a los que se hace referencia desde Microsoft.AspNetCore.All, pero que no se incluyen en el marco compartido de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2d1b-109">You may also need to add package references for packages that were referenced from Microsoft.AspNetCore.All but are not included in the ASP.NET Core shared framework.</span></span>  <span data-ttu-id="e2d1b-110">Estos paquetes se enumeran aquí: [Migración desde Microsoft.AspNetCore.All a Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).</span><span class="sxs-lookup"><span data-stu-id="e2d1b-110">These packages are listed here: [Migrating from Microsoft.AspNetCore.All to Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).</span></span>

<span data-ttu-id="e2d1b-111">Vea también [Migración desde ASP.NET Core 2.2 a 3.0](/aspnet/core/migration/22-to-30)</span><span class="sxs-lookup"><span data-stu-id="e2d1b-111">See also [Migrate from ASP.NET Core 2.2 to 3.0](/aspnet/core/migration/22-to-30)</span></span>
