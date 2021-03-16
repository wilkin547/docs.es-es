---
title: 'Cambio importante: Cambios de comportamiento de API relacionados con ensamblados para el formato de publicación de un solo archivo'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde varias API relacionadas con la ubicación de archivos de un ensamblado tienen cambios de comportamiento cuando se invocan en un formato de publicación de un solo archivo.
ms.date: 11/01/2020
ms.openlocfilehash: 3810a71fac481a42ccf2c8e64149d171f31c6821
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257692"
---
# <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a><span data-ttu-id="88ff1-103">Cambios de comportamiento de API relacionados con ensamblados para el formato de publicación de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="88ff1-103">Assembly-related API behavior changes for single-file publishing format</span></span>

<span data-ttu-id="88ff1-104">Varias API relacionadas con la ubicación de archivos de un ensamblado tienen cambios de comportamiento cuando se invocan en un formato de publicación de un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="88ff1-104">Multiple APIs related to an assembly's file location have behavior changes when they're invoked in a single-file publishing format.</span></span>

## <a name="change-description"></a><span data-ttu-id="88ff1-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="88ff1-105">Change description</span></span>

<span data-ttu-id="88ff1-106">En la publicación de un solo archivo para .NET 5 y versiones posteriores, los ensamblados empaquetados se cargan desde la memoria en lugar de extraerse en el disco.</span><span class="sxs-lookup"><span data-stu-id="88ff1-106">In single-file publishing for .NET 5 and later versions, bundled assemblies are loaded from memory instead of extracted to disk.</span></span> <span data-ttu-id="88ff1-107">En el caso de las aplicaciones publicadas de un solo archivo, esto significa que ciertas API relacionadas con la ubicación devuelven valores diferentes en .NET 5 y versiones posteriores que en versiones anteriores de .NET.</span><span class="sxs-lookup"><span data-stu-id="88ff1-107">For single-file published apps, this means that certain location-related APIs return different values on .NET 5 and later than on previous versions of .NET.</span></span> <span data-ttu-id="88ff1-108">Los cambios son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="88ff1-108">The changes are as follows:</span></span>

| <span data-ttu-id="88ff1-109">API</span><span class="sxs-lookup"><span data-stu-id="88ff1-109">API</span></span> | <span data-ttu-id="88ff1-110">Versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="88ff1-110">Previous versions</span></span> | <span data-ttu-id="88ff1-111">.NET 5 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="88ff1-111">.NET 5 and later</span></span> |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | <span data-ttu-id="88ff1-112">Devuelve la ruta de acceso del archivo DLL extraído</span><span class="sxs-lookup"><span data-stu-id="88ff1-112">Returns extracted DLL file path</span></span> | <span data-ttu-id="88ff1-113">Devuelve una cadena vacía para los ensamblados agrupados</span><span class="sxs-lookup"><span data-stu-id="88ff1-113">Returns empty string for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | <span data-ttu-id="88ff1-114">Devuelve la ruta de acceso del archivo DLL extraído</span><span class="sxs-lookup"><span data-stu-id="88ff1-114">Returns extracted DLL file path</span></span> | <span data-ttu-id="88ff1-115">Inicia una excepción para los ensamblados agrupados</span><span class="sxs-lookup"><span data-stu-id="88ff1-115">Throws exception for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | <span data-ttu-id="88ff1-116">Devuelve `null` para los ensamblados agrupados</span><span class="sxs-lookup"><span data-stu-id="88ff1-116">Returns `null` for bundled assemblies</span></span> | <span data-ttu-id="88ff1-117">Inicia una excepción para los ensamblados agrupados</span><span class="sxs-lookup"><span data-stu-id="88ff1-117">Throws exception for bundled assemblies</span></span> |
| `Environment.GetCommandLineArgs()[0]` | <span data-ttu-id="88ff1-118">El valor es el nombre del punto de entrada del archivo DLL</span><span class="sxs-lookup"><span data-stu-id="88ff1-118">Value is the name of the entry point DLL</span></span> | <span data-ttu-id="88ff1-119">El valor es el nombre del archivo ejecutable del host</span><span class="sxs-lookup"><span data-stu-id="88ff1-119">Value is the name of the host executable</span></span> |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | <span data-ttu-id="88ff1-120">El valor es el directorio de extracción temporal</span><span class="sxs-lookup"><span data-stu-id="88ff1-120">Value is the temporary extraction directory</span></span> | <span data-ttu-id="88ff1-121">El valor es el directorio contenedor del archivo ejecutable del host</span><span class="sxs-lookup"><span data-stu-id="88ff1-121">Value is the containing directory of the host executable</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="88ff1-122">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="88ff1-122">Version introduced</span></span>

<span data-ttu-id="88ff1-123">5.0</span><span class="sxs-lookup"><span data-stu-id="88ff1-123">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="88ff1-124">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="88ff1-124">Recommended action</span></span>

<span data-ttu-id="88ff1-125">Evite las dependencias de la ubicación de archivo de los ensamblados al publicarlos como un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="88ff1-125">Avoid dependencies on the file location of assemblies when publishing as a single file.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="88ff1-126">API afectadas</span><span class="sxs-lookup"><span data-stu-id="88ff1-126">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
