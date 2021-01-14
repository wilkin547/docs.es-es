---
title: Cómo genera MSBuild los nombres de archivo de manifiesto
description: Describe los factores que influyen en el nombre de un archivo de manifiesto de recurso generado por MSBuild en tiempo de compilación.
ms.date: 05/08/2020
ms.topic: conceptual
ms.openlocfilehash: 383bf6a077b0631e70ddaa4721b20e992127a73c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "97866394"
---
# <a name="how-resource-manifest-files-are-named"></a><span data-ttu-id="b0fe4-103">Cómo se asigna un nombre a los archivos de manifiesto del recurso</span><span class="sxs-lookup"><span data-stu-id="b0fe4-103">How resource manifest files are named</span></span>

<span data-ttu-id="b0fe4-104">Cuando MSBuild compila un proyecto de .NET Core, los archivos de recursos XML, que tienen la extensión de archivo *.resx*, se convierten en archivos *.resources* binarios.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-104">When MSBuild compiles a .NET Core project, XML resource files, which have the *.resx* file extension, are converted into binary *.resources* files.</span></span> <span data-ttu-id="b0fe4-105">Los archivos binarios se insertan en la salida del compilador y los puede leer el <xref:System.Resources.ResourceManager>.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-105">The binary files are embedded into the output of the compiler and can be read by the <xref:System.Resources.ResourceManager>.</span></span> <span data-ttu-id="b0fe4-106">En este artículo se describe cómo MSBuild elige un nombre para cada archivo *.resources*.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-106">This article describes how MSBuild chooses a name for each *.resources* file.</span></span>

> [!TIP]
> <span data-ttu-id="b0fe4-107">Si agrega explícitamente un elemento de recurso al archivo de proyecto y también se [incluye con los patrones globales de inclusión predeterminados para .NET Core](../project-sdk/overview.md#default-compilation-includes), obtendrá un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-107">If you explicitly add a resource item to your project file, and it's also [included with the default include globs for .NET Core](../project-sdk/overview.md#default-compilation-includes), you will get a build error.</span></span> <span data-ttu-id="b0fe4-108">Para incluir manualmente los archivos de recursos como elementos `EmbeddedResource`, establezca la propiedad `EnableDefaultEmbeddedResourceItems` en false.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-108">To manually include resource files as `EmbeddedResource` items, set the `EnableDefaultEmbeddedResourceItems` property to false.</span></span>

## <a name="default-name"></a><span data-ttu-id="b0fe4-109">Nombre predeterminado</span><span class="sxs-lookup"><span data-stu-id="b0fe4-109">Default name</span></span>

<span data-ttu-id="b0fe4-110">En .NET Core 3.0 y versiones posteriores, se usa el nombre predeterminado de un manifiesto del recurso cuando se cumplen las dos condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0fe4-110">In .NET Core 3.0 and later, the default name for a resource manifest is used when both of the following conditions are met:</span></span>

- <span data-ttu-id="b0fe4-111">El archivo de recursos no se incluye de forma explícita en el archivo de proyecto como un elemento `EmbeddedResource` con metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon`.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-111">The resource file is not explicitly included in the project file as an `EmbeddedResource` item with `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata.</span></span>
- <span data-ttu-id="b0fe4-112">La propiedad `EmbeddedResourceUseDependentUponConvention` no se ha establecido en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-112">The `EmbeddedResourceUseDependentUponConvention` property is not set to `false` in the project file.</span></span> <span data-ttu-id="b0fe4-113">De manera predeterminada, esta propiedad está establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-113">By default, this property is set to `true`.</span></span> <span data-ttu-id="b0fe4-114">Para obtener más información, vea [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).</span><span class="sxs-lookup"><span data-stu-id="b0fe4-114">For more information, see [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).</span></span>

<span data-ttu-id="b0fe4-115">Si el archivo de recursos está ubicado con un archivo de origen ( *.cs* o *.vb*) del mismo nombre de archivo raíz, se usa el nombre completo del primer tipo que se define en el archivo de origen para el nombre de archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-115">If the resource file is colocated with a source file (*.cs* or *.vb*) of the same root file name, the full name of the first type that's defined in the source file is used for the manifest file name.</span></span> <span data-ttu-id="b0fe4-116">Por ejemplo, si `MyNamespace.Form1` es el primer tipo definido en *Form1.cs*, y *Form1.cs* se ubica conjuntamente con *Form1.resx*, el nombre de manifiesto generado para ese archivo de recursos es *MyNameSpace.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-116">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, and *Form1.cs* is colocated with *Form1.resx*, the generated manifest name for that resource file is *MyNamespace.Form1.resources*.</span></span>

## <a name="logicalname-metadata"></a><span data-ttu-id="b0fe4-117">Metadatos LogicalName</span><span class="sxs-lookup"><span data-stu-id="b0fe4-117">LogicalName metadata</span></span>

<span data-ttu-id="b0fe4-118">Si un archivo de recursos se incluye explícitamente en el archivo de proyecto como un elemento `EmbeddedResource` con metadatos `LogicalName`, se usa el valor `LogicalName` como nombre de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-118">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `LogicalName` metadata, the `LogicalName` value is used as the manifest name.</span></span> <span data-ttu-id="b0fe4-119">`LogicalName` tiene prioridad sobre cualquier otro metadato o configuración.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-119">`LogicalName` takes precedence over any other metadata or setting.</span></span>

<span data-ttu-id="b0fe4-120">Por ejemplo, el nombre de manifiesto del archivo de recursos que se define en el siguiente fragmento de archivo de proyecto es *SomeName.resources*.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-120">For example, the manifest name for the resource file that's defined in the following project file snippet is *SomeName.resources*.</span></span>

```xml
<EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
```

<span data-ttu-id="b0fe4-121">O bien</span><span class="sxs-lookup"><span data-stu-id="b0fe4-121">-or-</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
```

## <a name="manifestresourcename-metadata"></a><span data-ttu-id="b0fe4-122">Metadatos ManifestResourceName</span><span class="sxs-lookup"><span data-stu-id="b0fe4-122">ManifestResourceName metadata</span></span>

<span data-ttu-id="b0fe4-123">Si un archivo de recursos se incluye explícitamente en el archivo de proyecto como un elemento `EmbeddedResource` con metadatos `ManifestResourceName` (y `LogicalName` no está presente), se usa el valor `ManifestResourceName` combinado con la extensión de archivo *.resources* como nombre de archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-123">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `ManifestResourceName` metadata (and `LogicalName` is absent), the `ManifestResourceName` value, combined with the file extension *.resources*, is used as the manifest file name.</span></span>

<span data-ttu-id="b0fe4-124">Por ejemplo, el nombre de manifiesto del archivo de recursos que se define en el siguiente fragmento de archivo de proyecto es *SomeName.resources*.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-124">For example, the manifest name for the resource file that's defined in the following project file snippet is *SomeName.resources*.</span></span>

```xml
<EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
```

<span data-ttu-id="b0fe4-125">El nombre de manifiesto del archivo de recursos que se define en el siguiente fragmento de archivo de proyecto es *SomeName.fr-FR.resources*.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-125">The manifest name for the resource file that's defined in the following project file snippet is *SomeName.fr-FR.resources*.</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
```

## <a name="dependentupon-metadata"></a><span data-ttu-id="b0fe4-126">Metadatos DependentUpon</span><span class="sxs-lookup"><span data-stu-id="b0fe4-126">DependentUpon metadata</span></span>

<span data-ttu-id="b0fe4-127">Si un archivo de recursos se incluye explícitamente en el archivo de proyecto como un elemento `EmbeddedResource` con metadatos `DependentUpon` (y `LogicalName` y `ManifestResourceName` no están presentes), se usa la información del archivo de origen definido por `DependentUpon` para el nombre de archivo de manifiesto del recurso.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-127">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `DependentUpon` metadata (and `LogicalName` and `ManifestResourceName` are absent), information from the source file defined by `DependentUpon` is used for the resource manifest file name.</span></span> <span data-ttu-id="b0fe4-128">Específicamente, el nombre del primer tipo que se define en el archivo de código fuente se usa en el nombre del manifiesto como se indica a continuación: *Namespace.Classname\[.Culture].resources*.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-128">Specifically, the name of the first type that's defined in the source file is used in the manifest name as follows: *Namespace.Classname\[.Culture].resources*.</span></span>

<span data-ttu-id="b0fe4-129">Por ejemplo, el nombre de manifiesto del archivo de recursos que se define en el siguiente fragmento de archivo de proyecto es *Namespace.Classname.resources* (donde `Namespace.Classname` es la primera clase que se define en *MyTypes.cs*).</span><span class="sxs-lookup"><span data-stu-id="b0fe4-129">For example, the manifest name for the resource file that's defined in the following project file snippet is *Namespace.Classname.resources* (where `Namespace.Classname` is the first class that's defined in *MyTypes.cs*).</span></span>

```xml
<EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
```

<span data-ttu-id="b0fe4-130">El nombre de manifiesto del archivo de recursos que se define en el siguiente fragmento de archivo de proyecto es *Namespace.Classname.fr-FR.resources* (donde `Namespace.Classname` es la primera clase que se define en *MyTypes.cs*).</span><span class="sxs-lookup"><span data-stu-id="b0fe4-130">The manifest name for the resource file that's defined in the following project file snippet is *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the first class that's defined in *MyTypes.cs*).</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
```

## <a name="embeddedresourceusedependentuponconvention-property"></a><span data-ttu-id="b0fe4-131">EmbeddedResourceUseDependentUponConvention property</span><span class="sxs-lookup"><span data-stu-id="b0fe4-131">EmbeddedResourceUseDependentUponConvention property</span></span>

<span data-ttu-id="b0fe4-132">Si `EmbeddedResourceUseDependentUponConvention` se establece en`false` en el archivo de proyecto, cada nombre del archivo de manifiesto del recurso se basa en el espacio de nombres raíz del proyecto y en la ruta de acceso relativa desde la raíz del proyecto al archivo *.resx*.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-132">If `EmbeddedResourceUseDependentUponConvention` is set to `false` in the project file, each resource manifest file name is based off the root namespace for the project and the relative path from the project root to the *.resx* file.</span></span> <span data-ttu-id="b0fe4-133">Más específicamente, el nombre de archivo de manifiesto del recurso generado es *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-133">More specifically, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="b0fe4-134">Esta es también la lógica que se usa para generar nombres de manifiesto en versiones de .NET Core anteriores a la 3.0.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-134">This is also the logic used to generate manifest names in .NET Core versions prior to 3.0.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b0fe4-135">Si `RootNamespace` no está definido, se toma como valor predeterminado el nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-135">If `RootNamespace` is not defined, it defaults to the project name.</span></span>
> - <span data-ttu-id="b0fe4-136">Si se especifican metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento `EmbeddedResource` del archivo de proyecto, esta regla de nomenclatura no se aplica a ese archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="b0fe4-136">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item in the project file, this naming rule does not apply to that resource file.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0fe4-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0fe4-137">See also</span></span>

- [<span data-ttu-id="b0fe4-138">Funcionamiento de la nomenclatura del recurso del manifiesto</span><span class="sxs-lookup"><span data-stu-id="b0fe4-138">How Manifest Resource Naming Works</span></span>](https://gist.github.com/BenVillalobos/041673b9a73bec60fdc3bf0f86fae62a)
- [<span data-ttu-id="b0fe4-139">Propiedades de MSBuild para proyectos del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="b0fe4-139">MSBuild properties for .NET Core SDK projects</span></span>](../project-sdk/msbuild-props.md)
- [<span data-ttu-id="b0fe4-140">Cambios importantes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="b0fe4-140">MSBuild breaking changes</span></span>](../compatibility/msbuild.md)
