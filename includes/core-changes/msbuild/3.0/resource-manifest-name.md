---
ms.openlocfilehash: 276268d31670b5e7dcd0ae9c0b7a61c3c38ca663
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451904"
---
### <a name="resource-manifest-file-names"></a><span data-ttu-id="2b116-101">Nombres de archivo de manifiesto del recurso</span><span class="sxs-lookup"><span data-stu-id="2b116-101">Resource manifest file names</span></span>

<span data-ttu-id="2b116-102">A partir de .NET Core 3.0, ha cambiado el nombre del archivo de manifiesto del recurso generado.</span><span class="sxs-lookup"><span data-stu-id="2b116-102">Starting in .NET Core 3.0, the generated resource manifest file name has changed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2b116-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="2b116-103">Version introduced</span></span>

<span data-ttu-id="2b116-104">3.0</span><span class="sxs-lookup"><span data-stu-id="2b116-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="2b116-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="2b116-105">Change description</span></span>

<span data-ttu-id="2b116-106">Antes de .NET Core 3.0, cuando se establecían los metadatos [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) de un archivo de recursos ( *.resx*) en el archivo del proyecto de MSBuild, el nombre generado del manifiesto era *Namespace.ClassName.Resources*.</span><span class="sxs-lookup"><span data-stu-id="2b116-106">Prior to .NET Core 3.0, when [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) metadata was set for a resource (*.resx*) file in the MSBuild project file, the generated manifest name was *Namespace.Classname.resources*.</span></span> <span data-ttu-id="2b116-107">Si no se establecía [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile), el nombre generado del manifiesto era *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span><span class="sxs-lookup"><span data-stu-id="2b116-107">When [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) was not set, the generated manifest name was *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span></span>

<span data-ttu-id="2b116-108">A partir de .NET Core 3.0, si un archivo *.resx* está en la misma ubicación que un archivo de origen que tiene el mismo nombre (por ejemplo, en las aplicaciones de Windows Forms), el nombre de manifiesto del recurso se genera a partir del nombre completo del primer tipo del archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="2b116-108">Starting in .NET Core 3.0, when a *.resx* file is colocated with a source file of the same name, for example, in Windows Forms apps, the resource manifest name is generated from the full name of the first type in the source file.</span></span> <span data-ttu-id="2b116-109">Por ejemplo, si *Type.cs* está en la misma ubicación que *Type.resx*, el nombre generado del manifiesto es *Namespace.Classname.resources*.</span><span class="sxs-lookup"><span data-stu-id="2b116-109">For example, if *Type.cs* is colocated with *Type.resx*, the generated manifest name is *Namespace.Classname.resources*.</span></span> <span data-ttu-id="2b116-110">Con todo, si modifica cualquiera de los atributos de la propiedad `EmbeddedResource` del archivo *.resx*, el nombre de archivo de manifiesto generado puede ser diferente:</span><span class="sxs-lookup"><span data-stu-id="2b116-110">However, if you modify any of the attributes on the `EmbeddedResource` property for the *.resx* file, the generated manifest file name may be different:</span></span>

- <span data-ttu-id="2b116-111">Si se establece el atributo `LogicalName` en la propiedad `EmbeddedResource`, ese valor se usa como nombre de archivo de manifiesto del recurso.</span><span class="sxs-lookup"><span data-stu-id="2b116-111">If the `LogicalName` attribute on the `EmbeddedResource` property is set, that value is used as the resource manifest file name.</span></span>

  <span data-ttu-id="2b116-112">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="2b116-112">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  <span data-ttu-id="2b116-113">**Nombre de archivo de manifiesto del recurso generado**: *SomeName.resources* (independientemente del nombre del archivo *.resx*, de la referencia cultural o de cualquier otro metadato).</span><span class="sxs-lookup"><span data-stu-id="2b116-113">**Generated resource manifest file name**: *SomeName.resources* (regardless of the *.resx* file name or culture or any other metadata).</span></span>

- <span data-ttu-id="2b116-114">Si no se establece `LogicalName`, pero el atributo `ManifestResourceName` se establece en la propiedad `EmbeddedResource`, se usa su valor, combinado con la extensión de archivo *.resources*, como nombre de archivo de manifiesto del recurso.</span><span class="sxs-lookup"><span data-stu-id="2b116-114">If `LogicalName` is not set, but the `ManifestResourceName` attribute on the `EmbeddedResource` property is set, its value, combined with the file extension *.resources*, is used as the resource manifest file name.</span></span>

  <span data-ttu-id="2b116-115">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="2b116-115">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  <span data-ttu-id="2b116-116">**Nombre de archivo de manifiesto del recurso generado**: *SomeName.resources* o *SomeName.fr-FR.resources*.</span><span class="sxs-lookup"><span data-stu-id="2b116-116">**Generated resource manifest file name**: *SomeName.resources* or *SomeName.fr-FR.resources*.</span></span>

- <span data-ttu-id="2b116-117">Si no se aplican las reglas anteriores y el atributo `DependentUpon` del elemento `EmbeddedResource` se establece en un archivo de origen, el nombre del tipo de la primera clase del archivo de origen se usa en el nombre de archivo de manifiesto del recurso.</span><span class="sxs-lookup"><span data-stu-id="2b116-117">If the previous rules don't apply, and the `DependentUpon` attribute on the `EmbeddedResource` element is set to a source file, the type name of the first class in the source file is used in the resource manifest file name.</span></span> <span data-ttu-id="2b116-118">Más concretamente, el nombre de archivo generado es *Namespace.Classname\[.Culture].resources*.</span><span class="sxs-lookup"><span data-stu-id="2b116-118">More specifically, the generated file name is *Namespace.Classname\[.Culture].resources*.</span></span>

  <span data-ttu-id="2b116-119">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="2b116-119">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  <span data-ttu-id="2b116-120">**Nombre de archivo de manifiesto del recurso generado**: *Namespace.Classname.resources* o *Namespace.Classname.fr-FR.resources* (donde `Namespace.Classname` es el nombre de la primera clase de *MyTypes.cs*).</span><span class="sxs-lookup"><span data-stu-id="2b116-120">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="2b116-121">Si no se aplican las reglas anteriores, `EmbeddedResourceUseDependentUponConvention` es `true` (el valor predeterminado de .NET Core) y hay un archivo de origen en la misma ubicación que un archivo *.resx* que tiene el mismo nombre de archivo base, el archivo *.resx* se hace dependiente del archivo de origen correspondiente y el nombre generado es el mismo que en la regla anterior.</span><span class="sxs-lookup"><span data-stu-id="2b116-121">If the previous rules don't apply, `EmbeddedResourceUseDependentUponConvention` is `true` (the default for .NET Core), and there's a source file colocated with a *.resx* file that has the same base file name, the *.resx* file is made dependent upon the matching source file, and the generated name is the same as in the previous rule.</span></span> <span data-ttu-id="2b116-122">Esta es la regla de "configuración predeterminada" de los proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2b116-122">This is the "default settings" rule for .NET Core projects.</span></span>
  
  <span data-ttu-id="2b116-123">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="2b116-123">Examples:</span></span>
  
  <span data-ttu-id="2b116-124">Los archivos *MyTypes.cs* y *MyTypes.resx* o *MyTypes.fr-FR.resx* existen en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="2b116-124">Files *MyTypes.cs* and *MyTypes.resx* or *MyTypes.fr-FR.resx* exist in the same folder.</span></span>
  
  <span data-ttu-id="2b116-125">**Nombre de archivo de manifiesto del recurso generado**: *Namespace.Classname.resources* o *Namespace.Classname.fr-FR.resources* (donde `Namespace.Classname` es el nombre de la primera clase de *MyTypes.cs*).</span><span class="sxs-lookup"><span data-stu-id="2b116-125">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>
    
- <span data-ttu-id="2b116-126">Si no se aplica ninguna de las reglas anteriores, el nombre de archivo de manifiesto del recurso generado es *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span><span class="sxs-lookup"><span data-stu-id="2b116-126">If none of the previous rules apply, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="2b116-127">La ruta de acceso relativa es el valor del atributo `Link` del elemento `EmbeddedResource` si se ha establecido.</span><span class="sxs-lookup"><span data-stu-id="2b116-127">The relative path is the value of the `Link` attribute of the `EmbeddedResource` element if it's set.</span></span> <span data-ttu-id="2b116-128">En caso contrario, la ruta de acceso relativa es el valor del atributo `Identity` del elemento `EmbeddedResource`.</span><span class="sxs-lookup"><span data-stu-id="2b116-128">Otherwise, the relative path is the value of the `Identity` attribute of the `EmbeddedResource` element.</span></span> <span data-ttu-id="2b116-129">En Visual Studio, esta es la ruta de acceso de la raíz del proyecto al archivo en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="2b116-129">In Visual Studio, this is the path from the project root to the file in Solution Explorer.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2b116-130">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="2b116-130">Recommended action</span></span>

<span data-ttu-id="2b116-131">Si no le satisfacen los nombres de manifiesto generados, puede:</span><span class="sxs-lookup"><span data-stu-id="2b116-131">If you're unsatisfied with the generated manifest names, you can:</span></span>

- <span data-ttu-id="2b116-132">Modificar los metadatos del archivo de recursos según una de las reglas de nomenclatura descritas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2b116-132">Modify your resource file metadata according to one of the previously described naming rules.</span></span>

- <span data-ttu-id="2b116-133">Establecer `EmbeddedResourceUseDependentUponConvention` en `false` en el archivo del proyecto para rechazar la nueva convención por completo:</span><span class="sxs-lookup"><span data-stu-id="2b116-133">Set `EmbeddedResourceUseDependentUponConvention` to `false` in your project file to opt out of the new convention entirely:</span></span>

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > <span data-ttu-id="2b116-134">Si los atributos `LogicalName` o `ManifestResourceName` están presentes, se seguirán usando sus valores en el nombre del archivo generado.</span><span class="sxs-lookup"><span data-stu-id="2b116-134">If the `LogicalName` or `ManifestResourceName` attributes are present, their values will still be used for the generated file name.</span></span>

#### <a name="category"></a><span data-ttu-id="2b116-135">Categoría</span><span class="sxs-lookup"><span data-stu-id="2b116-135">Category</span></span>

<span data-ttu-id="2b116-136">MSBuild</span><span class="sxs-lookup"><span data-stu-id="2b116-136">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2b116-137">API afectadas</span><span class="sxs-lookup"><span data-stu-id="2b116-137">Affected APIs</span></span>

<span data-ttu-id="2b116-138">N/D</span><span class="sxs-lookup"><span data-stu-id="2b116-138">N/A</span></span>
