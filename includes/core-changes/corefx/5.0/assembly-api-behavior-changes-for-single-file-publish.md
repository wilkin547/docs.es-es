---
ms.openlocfilehash: 0d6847b7a937094f36efae70ae450cc37824221d
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955567"
---
### <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a><span data-ttu-id="98742-101">Cambios de comportamiento de API relacionados con ensamblados para el formato de publicación de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="98742-101">Assembly-related API behavior changes for single-file publishing format</span></span>

<span data-ttu-id="98742-102">Varias API relacionadas con la ubicación de archivos de un ensamblado tienen cambios de comportamiento cuando se invocan en un formato de publicación de un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="98742-102">Multiple APIs related to an assembly's file location have behavior changes when they're invoked in a single-file publishing format.</span></span>

#### <a name="change-description"></a><span data-ttu-id="98742-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="98742-103">Change description</span></span>

<span data-ttu-id="98742-104">En la publicación de un solo archivo para .NET 5.0 y versiones posteriores, los ensamblados empaquetados se cargan desde la memoria en lugar de extraerse en el disco.</span><span class="sxs-lookup"><span data-stu-id="98742-104">In single-file publishing for .NET 5.0 and later versions, bundled assemblies are loaded from memory instead of extracted to disk.</span></span> <span data-ttu-id="98742-105">En el caso de las aplicaciones publicadas de un solo archivo, esto significa que ciertas API relacionadas con la ubicación devuelven valores diferentes en .NET 5.0 y versiones posteriores que en versiones anteriores de .NET.</span><span class="sxs-lookup"><span data-stu-id="98742-105">For single-file published apps, this means that certain location-related APIs return different values on .NET 5.0 and later than on previous versions of .NET.</span></span> <span data-ttu-id="98742-106">Los cambios son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="98742-106">The changes are as follows:</span></span>

| <span data-ttu-id="98742-107">API</span><span class="sxs-lookup"><span data-stu-id="98742-107">API</span></span> | <span data-ttu-id="98742-108">Versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="98742-108">Previous versions</span></span> | <span data-ttu-id="98742-109">.NET 5.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="98742-109">.NET 5.0 and later</span></span> |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | <span data-ttu-id="98742-110">Devuelve la ruta de acceso del archivo DLL extraído</span><span class="sxs-lookup"><span data-stu-id="98742-110">Returns extracted DLL file path</span></span> | <span data-ttu-id="98742-111">Devuelve una cadena vacía para los ensamblados agrupados</span><span class="sxs-lookup"><span data-stu-id="98742-111">Returns empty string for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | <span data-ttu-id="98742-112">Devuelve la ruta de acceso del archivo DLL extraído</span><span class="sxs-lookup"><span data-stu-id="98742-112">Returns extracted DLL file path</span></span> | <span data-ttu-id="98742-113">Inicia una excepción para los ensamblados agrupados</span><span class="sxs-lookup"><span data-stu-id="98742-113">Throws exception for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | <span data-ttu-id="98742-114">Devuelve `null` para los ensamblados agrupados</span><span class="sxs-lookup"><span data-stu-id="98742-114">Returns `null` for bundled assemblies</span></span> | <span data-ttu-id="98742-115">Inicia una excepción para los ensamblados agrupados</span><span class="sxs-lookup"><span data-stu-id="98742-115">Throws exception for bundled assemblies</span></span> |
| `Environment.GetCommandLineArgs()[0]` | <span data-ttu-id="98742-116">El valor es el nombre del punto de entrada del archivo DLL</span><span class="sxs-lookup"><span data-stu-id="98742-116">Value is the name of the entry point DLL</span></span> | <span data-ttu-id="98742-117">El valor es el nombre del archivo ejecutable del host</span><span class="sxs-lookup"><span data-stu-id="98742-117">Value is the name of the host executable</span></span> |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | <span data-ttu-id="98742-118">El valor es el directorio de extracción temporal</span><span class="sxs-lookup"><span data-stu-id="98742-118">Value is the temporary extraction directory</span></span> | <span data-ttu-id="98742-119">El valor es el directorio contenedor del archivo ejecutable del host</span><span class="sxs-lookup"><span data-stu-id="98742-119">Value is the containing directory of the host executable</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="98742-120">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="98742-120">Version introduced</span></span>

<span data-ttu-id="98742-121">5.0</span><span class="sxs-lookup"><span data-stu-id="98742-121">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="98742-122">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="98742-122">Recommended action</span></span>

<span data-ttu-id="98742-123">Evite las dependencias de la ubicación de archivo de los ensamblados al publicarlos como un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="98742-123">Avoid dependencies on the file location of assemblies when publishing as a single file.</span></span>

#### <a name="category"></a><span data-ttu-id="98742-124">Categoría</span><span class="sxs-lookup"><span data-stu-id="98742-124">Category</span></span>

- <span data-ttu-id="98742-125">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="98742-125">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="98742-126">API afectadas</span><span class="sxs-lookup"><span data-stu-id="98742-126">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
