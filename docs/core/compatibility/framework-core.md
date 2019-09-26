---
title: Cambios importantes, de .NET Framework a .NET Core 3.0 (.NET Core)
description: Enumera los cambios importantes de .NET Framework a .NET Core 3.0 para Windows Forms y Windows Presentation Foundation.
ms.date: 09/10/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c658c5bce7a2554bba83f2779a73d9d6af01a342
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2019
ms.locfileid: "71151532"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a><span data-ttu-id="da71c-103">Cambios importantes para la migración desde .NET Framework a .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="da71c-103">Breaking changes for migration from .NET Framework to .NET Core 3.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da71c-104">Este artículo está en construcción.</span><span class="sxs-lookup"><span data-stu-id="da71c-104">This article is under construction.</span></span> <span data-ttu-id="da71c-105">Esta no es una lista completa de todos los cambios importantes en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="da71c-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="da71c-106">Para obtener más información sobre los cambios importantes en .NET Core, puede consultar las [propuestas de cambios importantes](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) individuales en el repositorio dotnet/docs de GitHub.</span><span class="sxs-lookup"><span data-stu-id="da71c-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="da71c-107">Si va a migrar una aplicación de Windows Forms o Windows Presentation Foundation desde .NET Framework a .NET Core 3.0, revise los temas siguientes para ver los cambios importantes que pueden afectar a la aplicación:</span><span class="sxs-lookup"><span data-stu-id="da71c-107">If you are migrating a Windows Forms or Windows Presentation Foundation application from .NET Framework to .NET Core 3.0, review the following topics for breaking changes that may affect your app:</span></span>

## <a name="windows-forms"></a><span data-ttu-id="da71c-108">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da71c-108">Windows Forms</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]
