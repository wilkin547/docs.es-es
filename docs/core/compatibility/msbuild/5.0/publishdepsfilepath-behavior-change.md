---
title: 'Cambio importante: Cambio de comportamiento de PublishDepsFilePath'
description: Obtenga información sobre el cambio importante en .NET 5 en el que la propiedad PublishDepsFilePath de MSBuild está vacía para las aplicaciones de un solo archivo.
ms.date: 09/17/2020
ms.openlocfilehash: 845073e73ec6bdf820f28ace487d9ae4d04d0790
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104872930"
---
# <a name="publishdepsfilepath-behavior-change"></a><span data-ttu-id="f9d76-103">Cambio de comportamiento de PublishDepsFilePath</span><span class="sxs-lookup"><span data-stu-id="f9d76-103">PublishDepsFilePath behavior change</span></span>

<span data-ttu-id="f9d76-104">La propiedad `PublishDepsFilePath` de MSBuild está vacía para las aplicaciones de archivo único.</span><span class="sxs-lookup"><span data-stu-id="f9d76-104">The `PublishDepsFilePath` MSBuild property is empty for single-file applications.</span></span> <span data-ttu-id="f9d76-105">Además, en el caso de las aplicaciones que no son de archivo único, es posible que el archivo *deps.json* no se copie en el directorio de salida hasta después en la compilación.</span><span class="sxs-lookup"><span data-stu-id="f9d76-105">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory until later in the build.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f9d76-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f9d76-106">Version introduced</span></span>

<span data-ttu-id="f9d76-107">5.0</span><span class="sxs-lookup"><span data-stu-id="f9d76-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="f9d76-108">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f9d76-108">Change description</span></span>

<span data-ttu-id="f9d76-109">En versiones anteriores de .NET, la propiedad `PublishDepsFilePath` de MSBuild es la ruta de acceso al archivo *deps.json* de la aplicación en el directorio de salida para las aplicaciones que no son de archivo único, y una ruta de acceso en el directorio intermedio para las aplicaciones de archivo único.</span><span class="sxs-lookup"><span data-stu-id="f9d76-109">In previous .NET versions, the `PublishDepsFilePath` MSBuild property is the path to the app's *deps.json* file in the output directory for non single-file applications, and a path in the intermediate directory for single-file apps.</span></span>

<span data-ttu-id="f9d76-110">A partir de .NET 5, `PublishDepsFilePath` está vacío para las aplicaciones de archivo único y una nueva propiedad `IntermediateDepsFilePath` especifica la ubicación de *deps.json* en el directorio intermedio.</span><span class="sxs-lookup"><span data-stu-id="f9d76-110">Starting in .NET 5, `PublishDepsFilePath` is empty for single-file applications and a new `IntermediateDepsFilePath` property specifies the *deps.json* location in the intermediate directory.</span></span> <span data-ttu-id="f9d76-111">Además, en el caso de las aplicaciones que no son de archivo único, es posible que el archivo *deps.json* no se copie en el directorio de salida (es decir, la ruta de acceso especificada por `PublishDepsFilePath`) hasta después en la compilación.</span><span class="sxs-lookup"><span data-stu-id="f9d76-111">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory (that is, the path specified by `PublishDepsFilePath`) until later in the build.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="f9d76-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="f9d76-112">Reason for change</span></span>

<span data-ttu-id="f9d76-113">Este cambio se ha realizado por dos motivos:</span><span class="sxs-lookup"><span data-stu-id="f9d76-113">This change was made for a couple of reasons:</span></span>

- <span data-ttu-id="f9d76-114">Debido a la refactorización de la lógica de publicación para admitir [aplicaciones de archivo único mejoradas](https://github.com/dotnet/designs/blob/main/accepted/2020/single-file/design.md) en .NET 5.</span><span class="sxs-lookup"><span data-stu-id="f9d76-114">Due to a refactoring of the publish logic in order to support [improved single-file apps](https://github.com/dotnet/designs/blob/main/accepted/2020/single-file/design.md) in .NET 5.</span></span>

- <span data-ttu-id="f9d76-115">En las aplicaciones de archivo único, para protegerse de los destinos que intentan volver a escribir el archivo *deps.json* después de que *deps.json* ya se haya agrupado, por lo que no afecta a la aplicación de forma silenciosa.</span><span class="sxs-lookup"><span data-stu-id="f9d76-115">In single-file apps, to help guard against targets that try to rewrite the *deps.json* file after *deps.json* has already been bundled, thus silently not affecting the app.</span></span> <span data-ttu-id="f9d76-116">Por este motivo, `PublishDepsFilePath` está vacía para las aplicaciones de archivo único.</span><span class="sxs-lookup"><span data-stu-id="f9d76-116">For this reason, `PublishDepsFilePath` is empty for single-file applications.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f9d76-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f9d76-117">Recommended action</span></span>

<span data-ttu-id="f9d76-118">Los destinos que reescriben el archivo *deps.json* deberían hacerlo por lo general mediante la propiedad `IntermediateDepsFilePath`.</span><span class="sxs-lookup"><span data-stu-id="f9d76-118">Targets that rewrite the *deps.json* file should generally do so using the `IntermediateDepsFilePath` property.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f9d76-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f9d76-119">Affected APIs</span></span>

<span data-ttu-id="f9d76-120">N/D</span><span class="sxs-lookup"><span data-stu-id="f9d76-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
