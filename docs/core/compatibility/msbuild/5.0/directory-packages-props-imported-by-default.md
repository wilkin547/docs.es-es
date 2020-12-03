---
title: 'Cambio importante: Los archivos Directory.Packages.props se importan de forma predeterminada'
description: Obtenga información sobre el cambio importante de .NET 5.0 por el que los archivos .props de NuGet importan de forma automática un archivo denominado Directory.Packages.props si se encuentra en la carpeta del proyecto o en cualquiera de sus antecesores.
ms.date: 09/17/2020
ms.openlocfilehash: ee8a2999b801e81750d96a0bc985e3c8169224a9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760153"
---
# <a name="directorypackagesprops-files-is-imported-by-default"></a><span data-ttu-id="ca398-103">Los archivos Directory.Packages.props se importan de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="ca398-103">Directory.Packages.props files is imported by default</span></span>

<span data-ttu-id="ca398-104">Los archivos *.props* de NuGet importan de forma automática un archivo denominado *Directory.Packages.props* si se encuentra en la carpeta del proyecto o en cualquiera de sus antecesores.</span><span class="sxs-lookup"><span data-stu-id="ca398-104">NuGet's *.props* files automatically import a file named *Directory.Packages.props* if it's found in the project folder or any of its ancestors.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ca398-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ca398-105">Version introduced</span></span>

<span data-ttu-id="ca398-106">5.0</span><span class="sxs-lookup"><span data-stu-id="ca398-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="ca398-107">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="ca398-107">Change description</span></span>

<span data-ttu-id="ca398-108">En versiones anteriores de .NET, podía tener un archivo con el nombre *Directory.Packages.props* en el archivo del proyecto y el archivo *.props* de NuGet no lo importaría de forma automática en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="ca398-108">In previous .NET versions, you could have a file named *Directory.Packages.props* in your project file and it wouldn't be automatically imported by NuGet's *.props* file at build time.</span></span>

<span data-ttu-id="ca398-109">A partir de .NET 5.0, este tipo de archivo *se importa* automáticamente si existe en la carpeta del proyecto o en cualquiera de sus antecesores.</span><span class="sxs-lookup"><span data-stu-id="ca398-109">Starting in .NET 5.0, such a file *is* automatically imported if it exists in the project folder or any of its ancestors.</span></span> <span data-ttu-id="ca398-110">Si tiene un archivo con este nombre en la carpeta del proyecto, esta importación automática podría cambiar el comportamiento de la compilación.</span><span class="sxs-lookup"><span data-stu-id="ca398-110">If you have a file with this name in your project folder, this automatic import could change behavior of the build.</span></span> <span data-ttu-id="ca398-111">Por ejemplo, el archivo no se importaba y ahora se importará, o bien el orden del momento de la importación se podría cambiar si lo importa de forma específica.</span><span class="sxs-lookup"><span data-stu-id="ca398-111">For example, the file will be imported but it wasn't before, or the order of when it's imported could change if you specifically import it.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ca398-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="ca398-112">Reason for change</span></span>

<span data-ttu-id="ca398-113">Este cambio se ha realizado para admitir el [control de versiones de paquetes centrales](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) para NuGet.</span><span class="sxs-lookup"><span data-stu-id="ca398-113">This change was made in order to support [central package versioning](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) for NuGet.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ca398-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ca398-114">Recommended action</span></span>

<span data-ttu-id="ca398-115">Cambie el nombre del archivo *Directory.Packages.props* existente si no se debe importar de forma automática.</span><span class="sxs-lookup"><span data-stu-id="ca398-115">Rename the existing *Directory.Packages.props* file if it should not be imported automatically.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ca398-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ca398-116">Affected APIs</span></span>

<span data-ttu-id="ca398-117">N/D</span><span class="sxs-lookup"><span data-stu-id="ca398-117">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
