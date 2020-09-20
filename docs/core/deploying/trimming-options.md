---
title: Opciones de recorte
description: Obtenga información sobre cómo controlar el recorte de aplicaciones autocontenidas.
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: 89bd195a97c2f1bbbba9199fea51c917c4e4836b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515837"
---
# <a name="trimming-options"></a><span data-ttu-id="54ba6-103">Opciones de recorte</span><span class="sxs-lookup"><span data-stu-id="54ba6-103">Trimming options</span></span>

<span data-ttu-id="54ba6-104">Los siguientes elementos y propiedades de MSBuild influyen en el comportamiento de [implementaciones autocontenidas recortadas](trim-self-contained.md).</span><span class="sxs-lookup"><span data-stu-id="54ba6-104">The following MSBuild properties and items influence the behavior of [trimmed self-contained deployments](trim-self-contained.md).</span></span> <span data-ttu-id="54ba6-105">Algunas de las opciones mencionan `ILLink`, que es el nombre de la herramienta subyacente que implementa el recorte.</span><span class="sxs-lookup"><span data-stu-id="54ba6-105">Some of the options mention `ILLink`, which is the name of the underlying tool that implements trimming.</span></span> <span data-ttu-id="54ba6-106">Puede encontrar más información sobre la herramienta subyacente en la [documentación del enlazador](https://github.com/mono/linker/tree/master/docs).</span><span class="sxs-lookup"><span data-stu-id="54ba6-106">More information about the underlying tool can be found at the [Linker documentation](https://github.com/mono/linker/tree/master/docs).</span></span>

## <a name="enable-trimming"></a><span data-ttu-id="54ba6-107">Habilitación del recorte</span><span class="sxs-lookup"><span data-stu-id="54ba6-107">Enable trimming</span></span>

- `<PublishTrimmed>true</PublishTrimmed>`

   <span data-ttu-id="54ba6-108">Habilite el recorte durante la publicación, con la configuración predeterminada definida por el SDK.</span><span class="sxs-lookup"><span data-stu-id="54ba6-108">Enable trimming during publish, with the default settings defined by the SDK.</span></span>

<span data-ttu-id="54ba6-109">Al usar `Microsoft.NET.Sdk`, se realizará un recorte en el nivel de ensamblado de los ensamblados de marco en el paquete del entorno de ejecución de netcoreapp.</span><span class="sxs-lookup"><span data-stu-id="54ba6-109">When using `Microsoft.NET.Sdk`, this will perform assembly-level trimming of the framework assemblies from the netcoreapp runtime pack.</span></span> <span data-ttu-id="54ba6-110">El código de aplicación y las bibliotecas que no son del marco no se recortan.</span><span class="sxs-lookup"><span data-stu-id="54ba6-110">Application code and non-framework libraries are not trimmed.</span></span> <span data-ttu-id="54ba6-111">Otros SDK pueden definir diferentes valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="54ba6-111">Other SDKs may define different defaults.</span></span>

## <a name="trimming-granularity"></a><span data-ttu-id="54ba6-112">Granularidad del recorte</span><span class="sxs-lookup"><span data-stu-id="54ba6-112">Trimming granularity</span></span>

<span data-ttu-id="54ba6-113">La siguiente configuración de granularidad controla la agresividad con la que se descarta el IL sin usar.</span><span class="sxs-lookup"><span data-stu-id="54ba6-113">The following granularity settings control how aggressively unused IL is discarded.</span></span> <span data-ttu-id="54ba6-114">Se puede establecer como una propiedad o como metadatos en un [ensamblado individual](#trimmed-assemblies).</span><span class="sxs-lookup"><span data-stu-id="54ba6-114">This can be set as a property, or as metadata on an [individual assembly](#trimmed-assemblies).</span></span>

- `<TrimMode>copyused</TrimMode>`

   <span data-ttu-id="54ba6-115">Habilite el recorte en el nivel de ensamblado, lo que mantendrá un ensamblado completo si se usa cualquier parte de este (de manera estática).</span><span class="sxs-lookup"><span data-stu-id="54ba6-115">Enable assembly-level trimming, which will keep an entire assembly if any part of it is used (in a statically understood way).</span></span>

- `<TrimMode>link</TrimMode>`

    <span data-ttu-id="54ba6-116">Habilite el recorte a nivel de miembro, lo que quita los miembros sin usar de los tipos.</span><span class="sxs-lookup"><span data-stu-id="54ba6-116">Enable member-level trimming, which removes unused members from types.</span></span>

<span data-ttu-id="54ba6-117">Los ensamblados con metadatos de `<IsTrimmable>true</IsTrimmable>`, pero sin un valor de `TrimMode` explícito, usarán el valor global de `TrimMode`.</span><span class="sxs-lookup"><span data-stu-id="54ba6-117">Assemblies with `<IsTrimmable>true</IsTrimmable>` metadata but no explicit `TrimMode` will use the global `TrimMode`.</span></span> <span data-ttu-id="54ba6-118">El valor predeterminado de `TrimMode` para `Microsoft.NET.Sdk` es `copyused`.</span><span class="sxs-lookup"><span data-stu-id="54ba6-118">The default `TrimMode` for `Microsoft.NET.Sdk` is `copyused`.</span></span>

## <a name="trimmed-assemblies"></a><span data-ttu-id="54ba6-119">Ensamblados recortados</span><span class="sxs-lookup"><span data-stu-id="54ba6-119">Trimmed assemblies</span></span>

<span data-ttu-id="54ba6-120">Al publicar una aplicación recortada, el SDK calcula un elemento `ItemGroup` llamado `ManagedAssemblyToLink` que representa el conjunto de archivos que se va a procesar para el recorte.</span><span class="sxs-lookup"><span data-stu-id="54ba6-120">When publishing a trimmed app, the SDK computes an `ItemGroup` called `ManagedAssemblyToLink` that represents the set of files to be processed for trimming.</span></span> <span data-ttu-id="54ba6-121">`ManagedAssemblyToLink` puede tener metadatos que controlan el comportamiento de recorte por ensamblado.</span><span class="sxs-lookup"><span data-stu-id="54ba6-121">`ManagedAssemblyToLink` may have metadata that controls the trimming behavior per assembly.</span></span> <span data-ttu-id="54ba6-122">Para establecer estos metadatos, cree un destino que se ejecute antes del destino `PrepareForILLink` integrado.</span><span class="sxs-lookup"><span data-stu-id="54ba6-122">To set this metadata, create a target that runs before the built-in `PrepareForILLink` target.</span></span> <span data-ttu-id="54ba6-123">En el ejemplo siguiente se muestra cómo habilitar el recorte de `MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="54ba6-123">The following example shows how to enable trimming of `MyAssembly`.</span></span>

```xml
<Target Name="ConfigureTrimming"
        BeforeTargets="PrepareForILLink">
  <ItemGroup>
    <ManagedAssemblyToLink Condition="'%(Filename)' == 'MyAssembly'">
      <IsTrimmable>true</IsTrimmable>
    </ManagedAssemblyToLink>
  </ItemGroup>
</Target>
```

<span data-ttu-id="54ba6-124">No agregue ni quite elementos de `ManagedAssemblyToLink`, porque el SDK procesa este conjunto durante la publicación y espera que no cambie.</span><span class="sxs-lookup"><span data-stu-id="54ba6-124">Do not add or remove items to/from `ManagedAssemblyToLink`, because the SDK computes this set during publish and expects it not to change.</span></span> <span data-ttu-id="54ba6-125">Los metadatos admitidos son:</span><span class="sxs-lookup"><span data-stu-id="54ba6-125">The supported metadata is:</span></span>

- `<IsTrimmable>true</IsTrimmable>`

  <span data-ttu-id="54ba6-126">Controle si se ha recortado el ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="54ba6-126">Control whether the given assembly is trimmed.</span></span>

- <span data-ttu-id="54ba6-127">`<TrimMode>copyused</TrimMode>` o `<TrimMode>link</TrimMode>`</span><span class="sxs-lookup"><span data-stu-id="54ba6-127">`<TrimMode>copyused</TrimMode>` or `<TrimMode>link</TrimMode>`</span></span>

  <span data-ttu-id="54ba6-128">Controle la [granularidad del recorte](#trimming-granularity) de este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="54ba6-128">Control the [trimming granularity](#trimming-granularity) of this assembly.</span></span> <span data-ttu-id="54ba6-129">Esto tiene prioridad sobre el valor global de `TrimMode`.</span><span class="sxs-lookup"><span data-stu-id="54ba6-129">This takes precedence over the global `TrimMode`.</span></span> <span data-ttu-id="54ba6-130">La configuración del valor `TrimMode` en un ensamblado implica `<IsTrimmable>true</IsTrimmable>`.</span><span class="sxs-lookup"><span data-stu-id="54ba6-130">Setting `TrimMode` on an assembly implies `<IsTrimmable>true</IsTrimmable>`.</span></span>

## <a name="root-assemblies"></a><span data-ttu-id="54ba6-131">Ensamblados raíz</span><span class="sxs-lookup"><span data-stu-id="54ba6-131">Root assemblies</span></span>

<span data-ttu-id="54ba6-132">Todos los ensamblados que no tienen `<IsTrimmable>true</IsTrimmable>` se consideran raíces para el análisis, lo que significa que se conservarán todas sus dependencias estáticas.</span><span class="sxs-lookup"><span data-stu-id="54ba6-132">All assemblies that do not have `<IsTrimmable>true</IsTrimmable>` are considered roots for the analysis, which means that they and all of their statically understood dependencies will be kept.</span></span> <span data-ttu-id="54ba6-133">Se pueden "enraizar" ensamblados adicionales por nombre (sin la extensión `.dll`):</span><span class="sxs-lookup"><span data-stu-id="54ba6-133">Additional assemblies may be "rooted" by name (without the `.dll` extension):</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a><span data-ttu-id="54ba6-134">Descriptores raíz</span><span class="sxs-lookup"><span data-stu-id="54ba6-134">Root descriptors</span></span>

<span data-ttu-id="54ba6-135">Otra manera de especificar las raíces para el análisis consiste en usar un archivo XML que use el [formato de descriptor](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format) del enlazador.</span><span class="sxs-lookup"><span data-stu-id="54ba6-135">Another way to specify roots for analysis is using an XML file that uses the linker [descriptor format](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format).</span></span> <span data-ttu-id="54ba6-136">Esto le permite enraizar miembros específicos en lugar de un ensamblado completo.</span><span class="sxs-lookup"><span data-stu-id="54ba6-136">This lets you root specific members instead of a whole assembly.</span></span>

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

<span data-ttu-id="54ba6-137">Por ejemplo, `MyRoots.xml` podría enraizar un método específico al que la aplicación tiene acceso dinámicamente:</span><span class="sxs-lookup"><span data-stu-id="54ba6-137">For example, `MyRoots.xml` might root a specific method that is dynamically accessed by the application:</span></span>

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a><span data-ttu-id="54ba6-138">Advertencias de análisis</span><span class="sxs-lookup"><span data-stu-id="54ba6-138">Analysis warnings</span></span>

<span data-ttu-id="54ba6-139">El recorte quitará el IL que no es accesible estáticamente.</span><span class="sxs-lookup"><span data-stu-id="54ba6-139">Trimming will remove IL that is not statically reachable.</span></span> <span data-ttu-id="54ba6-140">Las aplicaciones que usan reflexión u otros patrones que crean dependencias dinámicas pueden romperse mediante el recorte.</span><span class="sxs-lookup"><span data-stu-id="54ba6-140">Apps that use reflection or other patterns that create dynamic dependencies may be broken by trimming.</span></span> <span data-ttu-id="54ba6-141">Para advertir sobre tales patrones:</span><span class="sxs-lookup"><span data-stu-id="54ba6-141">To warn about such patterns:</span></span>

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    <span data-ttu-id="54ba6-142">Habilite las advertencias de análisis de recorte.</span><span class="sxs-lookup"><span data-stu-id="54ba6-142">Enable trim analysis warnings.</span></span>

<span data-ttu-id="54ba6-143">Esto incluirá advertencias sobre toda la aplicación, incluidas las de su propio código, del código de la biblioteca y del código del marco.</span><span class="sxs-lookup"><span data-stu-id="54ba6-143">This will include warnings about the entire app, including your own code, library code, and framework code.</span></span>

## <a name="warning-versions"></a><span data-ttu-id="54ba6-144">Versiones de advertencias</span><span class="sxs-lookup"><span data-stu-id="54ba6-144">Warning versions</span></span>

<span data-ttu-id="54ba6-145">El análisis de recorte respeta la propiedad [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) que controla la versión de las advertencias de análisis en el SDK.</span><span class="sxs-lookup"><span data-stu-id="54ba6-145">Trim analysis respects the [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel) property that controls the version of analysis warnings across the SDK.</span></span> <span data-ttu-id="54ba6-146">Hay otra propiedad que controla la versión de las advertencias de análisis de recorte de forma independiente (similar a `WarningLevel` para el compilador):</span><span class="sxs-lookup"><span data-stu-id="54ba6-146">There is another property that controls the version of trim analysis warnings independently (similar to `WarningLevel` for the compiler):</span></span>

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    <span data-ttu-id="54ba6-147">Emita solo advertencias del nivel especificado o de uno inferior.</span><span class="sxs-lookup"><span data-stu-id="54ba6-147">Emit only warnings of the given level or lower.</span></span> <span data-ttu-id="54ba6-148">Puede ser `9999` para incluir todas las versiones de advertencias.</span><span class="sxs-lookup"><span data-stu-id="54ba6-148">This can be `9999` to include all warning versions.</span></span>

## <a name="suppressing-warnings"></a><span data-ttu-id="54ba6-149">Supresión de advertencias</span><span class="sxs-lookup"><span data-stu-id="54ba6-149">Suppressing warnings</span></span>

<span data-ttu-id="54ba6-150">Los [códigos de advertencia](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) individuales se pueden suprimir mediante las propiedades de MSBuild habituales que respeta la cadena de herramientas, incluidas `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors` y `TreatWarningsAsErrors`.</span><span class="sxs-lookup"><span data-stu-id="54ba6-150">Individual [warning codes](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) can be suppressed using the usual MSBuild properties respected by the toolchain, including `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors`, and `TreatWarningsAsErrors`.</span></span> <span data-ttu-id="54ba6-151">Existe una opción adicional que controla el comportamiento de advertencia como error de ILLink de forma independiente:</span><span class="sxs-lookup"><span data-stu-id="54ba6-151">There is an additional option that controls the ILLink warn-as-error behavior independently:</span></span>

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    <span data-ttu-id="54ba6-152">No trate las advertencias de ILLink como errores.</span><span class="sxs-lookup"><span data-stu-id="54ba6-152">Don't treat ILLink warnings as errors.</span></span> <span data-ttu-id="54ba6-153">Esto puede ser útil para evitar convertir advertencias de análisis de recorte en errores cuando se tratan las advertencias del compilador como errores globalmente.</span><span class="sxs-lookup"><span data-stu-id="54ba6-153">This may be useful to avoid turning trim analysis warnings into errors when treating compiler warnings as errors globally.</span></span>

## <a name="removing-symbols"></a><span data-ttu-id="54ba6-154">Eliminación de símbolos</span><span class="sxs-lookup"><span data-stu-id="54ba6-154">Removing symbols</span></span>

<span data-ttu-id="54ba6-155">Normalmente, los símbolos se recortan para que coincidan con los ensamblados recortados.</span><span class="sxs-lookup"><span data-stu-id="54ba6-155">Symbols will normally be trimmed to match the trimmed assemblies.</span></span> <span data-ttu-id="54ba6-156">También puede quitar todos los símbolos:</span><span class="sxs-lookup"><span data-stu-id="54ba6-156">You can also remove all symbols:</span></span>

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    <span data-ttu-id="54ba6-157">Quite los símbolos de la aplicación recortada, incluidos los archivos PDB incrustados y los archivos PDB independientes.</span><span class="sxs-lookup"><span data-stu-id="54ba6-157">Remove symbols from the trimmed application, including embedded PDBs and separate PDB files.</span></span> <span data-ttu-id="54ba6-158">Esto se aplica tanto al código de la aplicación como a las dependencias de los símbolos.</span><span class="sxs-lookup"><span data-stu-id="54ba6-158">This applies to both the application code and any dependencies that come with symbols.</span></span>

<span data-ttu-id="54ba6-159">El SDK también permite deshabilitar la compatibilidad del depurador con la propiedad `DebuggerSupport`.</span><span class="sxs-lookup"><span data-stu-id="54ba6-159">The SDK also makes it possible to disable debugger support using the property `DebuggerSupport`.</span></span> <span data-ttu-id="54ba6-160">Cuando la compatibilidad con el depurador está deshabilitada, el recorte quitará los símbolos automáticamente (el valor predeterminado de `TrimmerRemoveSymbols` se establece en "true").</span><span class="sxs-lookup"><span data-stu-id="54ba6-160">When debugger support is disabled, trimming will remove symbols automatically (`TrimmerRemoveSymbols` will default to true).</span></span>

## <a name="trimming-framework-library-features"></a><span data-ttu-id="54ba6-161">Características de recorte de las bibliotecas de marco</span><span class="sxs-lookup"><span data-stu-id="54ba6-161">Trimming framework library features</span></span>

<span data-ttu-id="54ba6-162">Varias áreas de características de las bibliotecas de marco incluyen directivas de enlazador que permiten eliminar el código de las características deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="54ba6-162">Several feature areas of the framework libraries come with linker directives that make it possible to remove the code for disabled features.</span></span>

- `<DebuggerSupport>false</DebuggerSupport>`

    <span data-ttu-id="54ba6-163">Elimina código que permite mejores experiencias de depuración.</span><span class="sxs-lookup"><span data-stu-id="54ba6-163">Remove code that enables better debugging experiences.</span></span> <span data-ttu-id="54ba6-164">También [elimina los símbolos](#removing-symbols).</span><span class="sxs-lookup"><span data-stu-id="54ba6-164">This will also [remove symbols](#removing-symbols).</span></span>

- `<EnableUnsafeBinaryFormatterSerialization>false</EnableUnsafeBinaryFormatterSerialization>`

    <span data-ttu-id="54ba6-165">Elimina la compatibilidad con la serialización BinaryFormatter.</span><span class="sxs-lookup"><span data-stu-id="54ba6-165">Remove BinaryFormatter serialization support.</span></span> <span data-ttu-id="54ba6-166">Para obtener más información, consulte la sección [Métodos de serialización BinaryFormatter obsoletos](../compatibility/corefx.md#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps).</span><span class="sxs-lookup"><span data-stu-id="54ba6-166">For more information, see [BinaryFormatter serialization methods are obsolete](../compatibility/corefx.md#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps).</span></span>

- `<EnableUnsafeUTF7Encoding>false</EnableUnsafeUTF7Encoding>`

    <span data-ttu-id="54ba6-167">Elimina el código de codificación UTF-7 poco seguro.</span><span class="sxs-lookup"><span data-stu-id="54ba6-167">Remove insecure UTF-7 encoding code.</span></span> <span data-ttu-id="54ba6-168">Para obtener más información, vea la sección [Rutas de acceso al código UTF-7 obsoletas](../compatibility/corefx.md#utf-7-code-paths-are-obsolete).</span><span class="sxs-lookup"><span data-stu-id="54ba6-168">For more information, see [UTF-7 code paths are obsolete](../compatibility/corefx.md#utf-7-code-paths-are-obsolete).</span></span>

- `<EventSourceSupport>false</EventSourceSupport>`

    <span data-ttu-id="54ba6-169">Elimina el código o la lógica relacionados con EventSource.</span><span class="sxs-lookup"><span data-stu-id="54ba6-169">Remove EventSource related code or logic.</span></span>

- `<HttpActivityPropagationSupport>false</HttpActivityPropagationSupport>`

    <span data-ttu-id="54ba6-170">Elimina el código relacionado con la compatibilidad de diagnóstico para System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="54ba6-170">Remove code related to diagnostics support for System.Net.Http.</span></span>

- `<InvariantGlobalization>true</InvariantGlobalization>`

    <span data-ttu-id="54ba6-171">Elimina el código y los datos específicos de la globalización.</span><span class="sxs-lookup"><span data-stu-id="54ba6-171">Remove globalization specific code and data.</span></span> <span data-ttu-id="54ba6-172">Para obtener más información, consulte [Modo invariable](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="54ba6-172">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

- `<UseSystemResourceKeys>true</UseSystemResourceKeys>`

    <span data-ttu-id="54ba6-173">Elimina los mensajes de excepción para los ensamblados de `System.*`.</span><span class="sxs-lookup"><span data-stu-id="54ba6-173">Strip exception messages for `System.*` assemblies.</span></span> <span data-ttu-id="54ba6-174">Cuando un ensamblado de `System.*` produzca una excepción, el mensaje será un identificador de recurso simplificado en lugar del mensaje completo.</span><span class="sxs-lookup"><span data-stu-id="54ba6-174">When an exception is thrown from a `System.*` assembly, the message will be a simplified resource ID instead of the full message.</span></span>

 <span data-ttu-id="54ba6-175">Estas propiedades harán que el código relacionado se recorte y también deshabilitarán las características a través del archivo [runtimeconfig](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="54ba6-175">These properties will cause the related code to be trimmed and will also disable features via the [runtimeconfig](../run-time-config/index.md) file.</span></span> <span data-ttu-id="54ba6-176">Para obtener más información sobre estas propiedades, incluidas las opciones de runtimeconfig correspondientes, vea la página sobre [modificadores de características](https://github.com/dotnet/runtime/blob/master/docs/workflow/trimming/feature-switches.md).</span><span class="sxs-lookup"><span data-stu-id="54ba6-176">For more information about these properties, including the corresponding runtimeconfig options, see [feature switches](https://github.com/dotnet/runtime/blob/master/docs/workflow/trimming/feature-switches.md).</span></span> <span data-ttu-id="54ba6-177">Algunos SDK pueden tener valores predeterminados para estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="54ba6-177">Some SDKs may have default values for these properties.</span></span>
