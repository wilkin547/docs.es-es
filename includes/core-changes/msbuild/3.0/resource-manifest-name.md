---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206228"
---
### <a name="resource-manifest-file-name-change"></a><span data-ttu-id="d923a-101">Cambio de nombre de archivo de manifiesto del recurso</span><span class="sxs-lookup"><span data-stu-id="d923a-101">Resource manifest file name change</span></span>

<span data-ttu-id="d923a-102">A partir de .NET Core 3.0, en el caso predeterminado, MSBuild genera un nombre de archivo de manifiesto diferente para los archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="d923a-102">Starting in .NET Core 3.0, in the default case, MSBuild generates a different manifest file name for resource files.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d923a-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d923a-103">Version introduced</span></span>

<span data-ttu-id="d923a-104">3.0</span><span class="sxs-lookup"><span data-stu-id="d923a-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="d923a-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d923a-105">Change description</span></span>

<span data-ttu-id="d923a-106">Antes de .NET Core 3.0, si no se especificaban los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento de `EmbeddedResource` del archivo del proyecto, MSBuild generaba un nombre de archivo de manifiesto con el patrón `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources`.</span><span class="sxs-lookup"><span data-stu-id="d923a-106">Prior to .NET Core 3.0, if no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata was specified for an `EmbeddedResource` item in the project file, MSBuild generated a manifest file name in the pattern `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources`.</span></span> <span data-ttu-id="d923a-107">Si `RootNamespace` no está definido en el archivo del proyecto, se toma como valor predeterminado el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d923a-107">If `RootNamespace` is not defined in the project file, it defaults to the project name.</span></span> <span data-ttu-id="d923a-108">Por ejemplo, el nombre de manifiesto generado para un archivo de recursos denominado *Form1.resx* en el directorio raíz del proyecto era *suproject.Form1.Resources*.</span><span class="sxs-lookup"><span data-stu-id="d923a-108">For example, the generated manifest name for a resource file named *Form1.resx* in the root project directory was *MyProject.Form1.resources*.</span></span>

<span data-ttu-id="d923a-109">A partir de .NET Core 3.0, si un archivo de recursos está ubicado conjuntamente con un archivo de código fuente del mismo nombre (por ejemplo, *Form1.resx* y *Form1.cs*), MSBuild usa la información de tipo del archivo de código fuente para generar el nombre del archivo de manifiesto con el patrón `<Namespace>.<ClassName>.resources`.</span><span class="sxs-lookup"><span data-stu-id="d923a-109">Starting in .NET Core 3.0, if a resource file is colocated with a source file of the same name (for example, *Form1.resx* and *Form1.cs*), MSBuild uses type information from the source file to generate the manifest file name in the pattern `<Namespace>.<ClassName>.resources`.</span></span> <span data-ttu-id="d923a-110">El espacio de nombres y el nombre de clase se extraen del primer tipo del archivo de código fuente ubicado conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="d923a-110">The namespace and class name are extracted from the first type in the colocated source file.</span></span> <span data-ttu-id="d923a-111">Por ejemplo, el nombre de manifiesto generado para un archivo de recursos denominado *Form1.resx* que se ubica conjuntamente con un archivo de código fuente denominado *Form1.cs* es *myNameSpace.Form1.Resources*.</span><span class="sxs-lookup"><span data-stu-id="d923a-111">For example, the generated manifest name for a resource file named *Form1.resx* that's colocated with a source file named *Form1.cs* is *MyNamespace.Form1.resources*.</span></span> <span data-ttu-id="d923a-112">Lo más importante que hay que tener en cuenta es que la primera parte del nombre de archivo es diferente en versiones anteriores de .NET Core (*myNameSpace* en lugar de *MyProject*).</span><span class="sxs-lookup"><span data-stu-id="d923a-112">The key thing to note is that the first part of the file name is different to prior versions of .NET Core (*MyNamespace* instead of *MyProject*).</span></span>

> [!NOTE]
> <span data-ttu-id="d923a-113">Si tiene los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` especificados en un elemento `EmbeddedResource` del archivo del proyecto, este cambio no afecta a ese archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="d923a-113">If you have `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata specified on an `EmbeddedResource` item in the project file, then this change does not affect that resource file.</span></span>

<span data-ttu-id="d923a-114">Este cambio importante se presentó con la incorporación de la propiedad `EmbeddedResourceUseDependentUponConvention` a los proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d923a-114">This breaking change was introduced with the addition of the `EmbeddedResourceUseDependentUponConvention` property to .NET Core projects.</span></span> <span data-ttu-id="d923a-115">De forma predeterminada, los archivos de recursos no se enumeran explícitamente en un archivo de proyecto de .NET Core, por lo que no tienen metadatos `DependentUpon` para especificar cómo nombrar el archivo *.resources* generado.</span><span class="sxs-lookup"><span data-stu-id="d923a-115">By default, resource files aren't explicitly listed in a .NET Core project file, so they have no `DependentUpon` metadata to specify how to name the generated *.resources* file.</span></span> <span data-ttu-id="d923a-116">Cuando `EmbeddedResourceUseDependentUponConvention` se establece en `true`, que es el valor predeterminado, MSBuild busca un archivo de código fuente ubicado conjuntamente y extrae un espacio de nombres y un nombre de clase de ese archivo.</span><span class="sxs-lookup"><span data-stu-id="d923a-116">When `EmbeddedResourceUseDependentUponConvention` is set to `true`, which is the default, MSBuild looks for a colocated source file and extracts a namespace and class name from that file.</span></span> <span data-ttu-id="d923a-117">Si establece `EmbeddedResourceUseDependentUponConvention` en `false`, MSBuild genera el nombre del manifiesto según el comportamiento anterior, que combina `RootNamespace` y la ruta de acceso relativa del archivo.</span><span class="sxs-lookup"><span data-stu-id="d923a-117">If you set `EmbeddedResourceUseDependentUponConvention` to `false`, MSBuild generates the manifest name according to the previous behavior, which combines `RootNamespace` and the relative file path.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d923a-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d923a-118">Recommended action</span></span>

<span data-ttu-id="d923a-119">En la mayoría de los casos, no se requiere ninguna acción por parte del desarrollador y la aplicación seguirá funcionando.</span><span class="sxs-lookup"><span data-stu-id="d923a-119">In most cases, no action is required on the part of the developer, and your app should continue to work.</span></span> <span data-ttu-id="d923a-120">Sin embargo, si este cambio invalida la aplicación, puede:</span><span class="sxs-lookup"><span data-stu-id="d923a-120">However, if this change breaks your app, you can either:</span></span>

- <span data-ttu-id="d923a-121">Cambiar el código para que espere el nuevo nombre de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="d923a-121">Change your code to expect the new manifest name.</span></span>

- <span data-ttu-id="d923a-122">Rechazar la nueva convención de nomenclatura mediante el establecimiento de `EmbeddedResourceUseDependentUponConvention` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d923a-122">Opt out of the new naming convention by setting `EmbeddedResourceUseDependentUponConvention` to `false` in your project file.</span></span>

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="d923a-123">Categoría</span><span class="sxs-lookup"><span data-stu-id="d923a-123">Category</span></span>

<span data-ttu-id="d923a-124">MSBuild</span><span class="sxs-lookup"><span data-stu-id="d923a-124">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d923a-125">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d923a-125">Affected APIs</span></span>

<span data-ttu-id="d923a-126">N/D</span><span class="sxs-lookup"><span data-stu-id="d923a-126">N/A</span></span>
