---
title: Globalización e ICU
ms.date: 05/21/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- globalization [.NET], about globalization
- global applications, globalization
- international applications [.NET], globalization
- world-ready applications, globalization
- application development [.NET], globalization
- culture, globalization
- icu, icu on windows, ms-icu
ms.openlocfilehash: ca579e837b801de237859963ede0e5a9a4bfbcbf
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439474"
---
# <a name="net-globalization-and-icu"></a><span data-ttu-id="4edc8-102">Globalización de .NET e ICU</span><span class="sxs-lookup"><span data-stu-id="4edc8-102">.NET globalization and ICU</span></span>

<span data-ttu-id="4edc8-103">Antes, las API de globalización de .NET usaban diferentes bibliotecas subyacentes en distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="4edc8-103">In the past, the .NET globalization APIs used different underlying libraries on different platforms.</span></span> <span data-ttu-id="4edc8-104">En UNIX, las API usaban [Componentes internacionales para Unicode (ICU)](http://site.icu-project.org/home) y, en Windows, usaban [Compatibilidad con el idioma nacional (NLS)](/windows/win32/intl/national-language-support).</span><span class="sxs-lookup"><span data-stu-id="4edc8-104">On Unix, the APIs used [International Components for Unicode (ICU)](http://site.icu-project.org/home), and on Windows, they used [National Language Support (NLS)](/windows/win32/intl/national-language-support).</span></span> <span data-ttu-id="4edc8-105">Esto producía algunas diferencias de comportamiento en varias API de globalización al ejecutar aplicaciones en distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="4edc8-105">This resulted in some behavioral differences in a handful of globalization APIs when running applications on different platforms.</span></span> <span data-ttu-id="4edc8-106">Las diferencias de comportamiento eran evidentes en estas áreas:</span><span class="sxs-lookup"><span data-stu-id="4edc8-106">Behavior differences were evident in these areas:</span></span>

- <span data-ttu-id="4edc8-107">Referencias culturales y datos culturales</span><span class="sxs-lookup"><span data-stu-id="4edc8-107">Cultures and culture data</span></span>
- <span data-ttu-id="4edc8-108">Uso de mayúsculas y minúsculas en cadenas</span><span class="sxs-lookup"><span data-stu-id="4edc8-108">String casing</span></span>
- <span data-ttu-id="4edc8-109">Ordenación y búsqueda de cadenas</span><span class="sxs-lookup"><span data-stu-id="4edc8-109">String sorting and searching</span></span>
- <span data-ttu-id="4edc8-110">Criterios de ordenación</span><span class="sxs-lookup"><span data-stu-id="4edc8-110">Sort keys</span></span>
- <span data-ttu-id="4edc8-111">Normalización de cadenas</span><span class="sxs-lookup"><span data-stu-id="4edc8-111">String normalization</span></span>
- <span data-ttu-id="4edc8-112">Compatibilidad con nombres de dominio internacionalizados (IDN)</span><span class="sxs-lookup"><span data-stu-id="4edc8-112">Internationalized Domain Names (IDN) support</span></span>
- <span data-ttu-id="4edc8-113">Nombre para mostrar de la zona horaria en Linux</span><span class="sxs-lookup"><span data-stu-id="4edc8-113">Time zone display name on Linux</span></span>

<span data-ttu-id="4edc8-114">A partir de .NET 5.0, los desarrolladores tienen más control sobre la biblioteca subyacente que se usa, lo que permite a las aplicaciones evitar diferencias entre plataformas.</span><span class="sxs-lookup"><span data-stu-id="4edc8-114">Starting with .NET 5.0, developers have more control over which underlying library is used, enabling applications to avoid differences across platforms.</span></span>

## <a name="icu-on-windows"></a><span data-ttu-id="4edc8-115">ICU en Windows</span><span class="sxs-lookup"><span data-stu-id="4edc8-115">ICU on Windows</span></span>

<span data-ttu-id="4edc8-116">La actualización de mayo de 2019 de Windows 10 y las versiones posteriores incluyen [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) como parte del sistema operativo, y .NET 5.0 y las versiones posteriores usan ICU de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4edc8-116">Windows 10 May 2019 Update and later versions include [icu.dll](/windows/win32/intl/international-components-for-unicode--icu-) as part of the OS, and .NET 5.0 and later versions use ICU by default.</span></span> <span data-ttu-id="4edc8-117">Cuando se ejecuta en Windows, .NET 5.0 y las versiones posteriores intentan cargar `icu.dll` y, si está disponible, se usa para la implementación de globalización.</span><span class="sxs-lookup"><span data-stu-id="4edc8-117">When running on Windows, .NET 5.0 and later versions try to load `icu.dll` and, if it's available, use it for the globalization implementation.</span></span> <span data-ttu-id="4edc8-118">Si no se puede encontrar o cargar la biblioteca de ICU, como cuando se ejecuta en versiones anteriores de Windows, .NET 5.0 y las versiones posteriores se revierten a la implementación basada en NLS.</span><span class="sxs-lookup"><span data-stu-id="4edc8-118">If the ICU library can't be found or loaded, such as when running on older versions of Windows, .NET 5.0 and later versions fall back to the NLS-based implementation.</span></span>

> [!NOTE]
> <span data-ttu-id="4edc8-119">Incluso cuando se usa ICU, los miembros de `CurrentCulture`, `CurrentUICulture` y `CurrentRegion` siguen usando las API del sistema operativo Windows para respetar la configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="4edc8-119">Even when using ICU, the `CurrentCulture`, `CurrentUICulture`, and `CurrentRegion` members still use Windows operating system APIs to honor user settings.</span></span>

### <a name="behavioral-differences"></a><span data-ttu-id="4edc8-120">Diferencias de comportamiento</span><span class="sxs-lookup"><span data-stu-id="4edc8-120">Behavioral differences</span></span>

<span data-ttu-id="4edc8-121">Si actualiza la aplicación para que tenga como destino .NET 5, es posible que vea cambios en ella aunque no sea consciente de usar las instalaciones de globalización.</span><span class="sxs-lookup"><span data-stu-id="4edc8-121">If you upgrade your app to target .NET 5, you might see changes in your app even if you don't realize you're using globalization facilities.</span></span> <span data-ttu-id="4edc8-122">En esta sección se enumera uno de los cambios de comportamiento que podría ver, pero también hay otros.</span><span class="sxs-lookup"><span data-stu-id="4edc8-122">This section lists one of the behavioral changes you might see, but there are others too.</span></span>

##### <a name="stringindexof"></a><span data-ttu-id="4edc8-123">String.IndexOf</span><span class="sxs-lookup"><span data-stu-id="4edc8-123">String.IndexOf</span></span>

<span data-ttu-id="4edc8-124">Considere el código siguiente que llama a <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> para buscar el índice del carácter de nueva línea en una cadena.</span><span class="sxs-lookup"><span data-stu-id="4edc8-124">Consider the following code that calls <xref:System.String.IndexOf(System.String)?displayProperty=nameWithType> to find the index of the newline character in a string.</span></span>

```csharp
string s = "Hello\r\nworld!";
int idx = s.IndexOf("\n");
Console.WriteLine(idx);
```

- <span data-ttu-id="4edc8-125">En versiones anteriores de .NET en Windows, el fragmento de código imprime `6`.</span><span class="sxs-lookup"><span data-stu-id="4edc8-125">In previous versions of .NET on Windows, the snippet prints `6`.</span></span>
- <span data-ttu-id="4edc8-126">En .NET 5.0 y versiones posteriores en la actualización del 10 de mayo de 2019 de Windows, el fragmento de código imprime `-1`.</span><span class="sxs-lookup"><span data-stu-id="4edc8-126">In .NET 5.0 and later versions on Windows 10 May 2019 Update and later versions, the snippet prints `-1`.</span></span>

<span data-ttu-id="4edc8-127">Para corregir este código mediante la realización de una búsqueda ordinal en lugar de una búsqueda según la referencia cultural, llame a la sobrecarga <xref:System.String.IndexOf(System.String,System.StringComparison)> y pase <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> como argumento.</span><span class="sxs-lookup"><span data-stu-id="4edc8-127">To fix this code by conducting an ordinal search instead of a culture-sensitive search, call the <xref:System.String.IndexOf(System.String,System.StringComparison)> overload and pass in <xref:System.StringComparison.Ordinal?displayProperty=nameWithType> as an argument.</span></span>

<span data-ttu-id="4edc8-128">Puede ejecutar las reglas de análisis de código [CA1307: Especificar StringComparison para mayor claridad](../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) y [CA1309: Usar StringComparison ordinal](../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) para buscar estos sitios de llamada en el código.</span><span class="sxs-lookup"><span data-stu-id="4edc8-128">You can run code analysis rules [CA1307: Specify StringComparison for clarity](../../../docs/fundamentals/code-analysis/quality-rules/ca1307.md) and [CA1309: Use ordinal StringComparison](../../../docs/fundamentals/code-analysis/quality-rules/ca1309.md) to find these call sites in your code.</span></span>

<span data-ttu-id="4edc8-129">Para más información, consulte [Cambios de comportamiento al comparar cadenas en .NET 5 +](../base-types/string-comparison-net-5-plus.md).</span><span class="sxs-lookup"><span data-stu-id="4edc8-129">For more information, see [Behavior changes when comparing strings on .NET 5+](../base-types/string-comparison-net-5-plus.md).</span></span>

### <a name="use-nls-instead-of-icu"></a><span data-ttu-id="4edc8-130">Uso de NLS en lugar de ICU</span><span class="sxs-lookup"><span data-stu-id="4edc8-130">Use NLS instead of ICU</span></span>

<span data-ttu-id="4edc8-131">Si se usa ICU en lugar de NLS, se pueden producir diferencias de comportamiento con algunas operaciones relacionadas con la globalización.</span><span class="sxs-lookup"><span data-stu-id="4edc8-131">Using ICU instead of NLS may result in behavioral differences with some globalization-related operations.</span></span> <span data-ttu-id="4edc8-132">Para revertir al uso de NLS, los desarrolladores pueden rechazar la implementación de ICU.</span><span class="sxs-lookup"><span data-stu-id="4edc8-132">To revert back to using NLS, a developer can opt out of the ICU implementation.</span></span> <span data-ttu-id="4edc8-133">Las aplicaciones pueden habilitar el modo NLS de cualquiera de estas maneras:</span><span class="sxs-lookup"><span data-stu-id="4edc8-133">Applications can enable NLS mode in any of the following ways:</span></span>

- <span data-ttu-id="4edc8-134">El archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="4edc8-134">In the project file:</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.UseNls" Value="true" />
  </ItemGroup>
  ```

- <span data-ttu-id="4edc8-135">En el archivo `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="4edc8-135">In the `runtimeconfig.json` file:</span></span>

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.UseNls": true
        }
    }
  }
  ```

- <span data-ttu-id="4edc8-136">Al establecer la variable de entorno `DOTNET_SYSTEM_GLOBALIZATION_USENLS` en el valor `true` o `1`.</span><span class="sxs-lookup"><span data-stu-id="4edc8-136">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_USENLS` to the value `true` or `1`.</span></span>

> [!NOTE]
> <span data-ttu-id="4edc8-137">Un valor establecido en el proyecto o en el archivo `runtimeconfig.json` tiene prioridad sobre la variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="4edc8-137">A value set in the project or in the `runtimeconfig.json` file takes precedence over the environment variable.</span></span>

<span data-ttu-id="4edc8-138">Para más información, vea [Valores de configuración de tiempo de ejecución](../../core/run-time-config/globalization.md#nls).</span><span class="sxs-lookup"><span data-stu-id="4edc8-138">For more information, see [Run-time config settings](../../core/run-time-config/globalization.md#nls).</span></span>

## <a name="app-local-icu"></a><span data-ttu-id="4edc8-139">ICU local de la aplicación</span><span class="sxs-lookup"><span data-stu-id="4edc8-139">App-local ICU</span></span>

<span data-ttu-id="4edc8-140">Cada versión de ICU puede tener incorporadas correcciones de errores, así como datos del Repositorio de datos comunes de configuración regional (CLDR) que describen los idiomas del mundo.</span><span class="sxs-lookup"><span data-stu-id="4edc8-140">Each release of ICU may bring with it bug fixes as well as updated Common Locale Data Repository (CLDR) data that describes the world's languages.</span></span> <span data-ttu-id="4edc8-141">El cambio entre las versiones de ICU puede afectar sutilmente al comportamiento de la aplicación cuando se trata de operaciones relacionadas con la globalización.</span><span class="sxs-lookup"><span data-stu-id="4edc8-141">Moving between versions of ICU can subtly impact app behavior when it comes to globalization-related operations.</span></span> <span data-ttu-id="4edc8-142">Para que los desarrolladores de aplicaciones puedan garantizar la coherencia entre todas las implementaciones, .NET 5.0 y las versiones posteriores permiten que las aplicaciones de Windows y UNIX transporten y usen su propia copia de ICU.</span><span class="sxs-lookup"><span data-stu-id="4edc8-142">To help application developers ensure consistency across all deployments, .NET 5.0 and later versions enable apps on both Windows and Unix to carry and use their own copy of ICU.</span></span>

<span data-ttu-id="4edc8-143">Las aplicaciones pueden participar en un modo de implementación de ICU local de la aplicación de cualquiera de estas maneras:</span><span class="sxs-lookup"><span data-stu-id="4edc8-143">Applications can opt in to an app-local ICU implementation mode in any of the following ways:</span></span>

- <span data-ttu-id="4edc8-144">En el archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="4edc8-144">In  the project file:</span></span>

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Globalization.AppLocalIcu" Value="<suffix>:<version> or <version>" />
  </ItemGroup>
  ```

- <span data-ttu-id="4edc8-145">En el archivo `runtimeconfig.json`:</span><span class="sxs-lookup"><span data-stu-id="4edc8-145">In the `runtimeconfig.json` file:</span></span>

  ```json
  {
    "runtimeOptions": {
       "configProperties": {
         "System.Globalization.AppLocalIcu": "<suffix>:<version> or <version>"
       }
    }
  }
  ```

- <span data-ttu-id="4edc8-146">Al establecer la variable de entorno `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` en el valor `<suffix>:<version>` o `<version>`.</span><span class="sxs-lookup"><span data-stu-id="4edc8-146">By setting the environment variable `DOTNET_SYSTEM_GLOBALIZATION_APPLOCALICU` to the value `<suffix>:<version>` or `<version>`.</span></span>

  <span data-ttu-id="4edc8-147">`<suffix>`: sufijo opcional de menos de 36 caracteres de longitud, según las convenciones de empaquetado públicas de ICU.</span><span class="sxs-lookup"><span data-stu-id="4edc8-147">`<suffix>`: Optional suffix of fewer than 36 characters in length, following the public ICU packaging conventions.</span></span> <span data-ttu-id="4edc8-148">Al compilar un ICU personalizado, puede personalizarlo para generar los nombres de lib y los nombres de símbolos exportados para que contengan un sufijo, por ejemplo, `libicuucmyapp`, donde `myapp` es el sufijo.</span><span class="sxs-lookup"><span data-stu-id="4edc8-148">When building a custom ICU, you can customize it to produce the lib names and exported symbol names to contain a suffix, for example, `libicuucmyapp`, where `myapp` is the suffix.</span></span>

  <span data-ttu-id="4edc8-149">`<version>`: versión de ICU válida, por ejemplo, 67.1.</span><span class="sxs-lookup"><span data-stu-id="4edc8-149">`<version>`: A valid ICU version, for example, 67.1.</span></span> <span data-ttu-id="4edc8-150">Esta versión se usa para cargar los archivos binarios y obtener los símbolos exportados.</span><span class="sxs-lookup"><span data-stu-id="4edc8-150">This version is used to load the binaries and to get the exported symbols.</span></span>

<span data-ttu-id="4edc8-151">Para cargar el ICU cuando se establece el modificador local de la aplicación, .NET usa el método <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType>, que sondea varias rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="4edc8-151">To load ICU when the app-local switch is set, .NET uses the <xref:System.Runtime.InteropServices.NativeLibrary.TryLoad%2A?displayProperty=nameWithType> method, which probes multiple paths.</span></span> <span data-ttu-id="4edc8-152">El método intenta buscar primero la biblioteca en la propiedad `NATIVE_DLL_SEARCH_DIRECTORIES`, que la crea el host dotnet basándose en el archivo `deps.json` de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4edc8-152">The method first tries to find the library in the `NATIVE_DLL_SEARCH_DIRECTORIES` property, which is created by the dotnet host based on the `deps.json` file for the app.</span></span> <span data-ttu-id="4edc8-153">Para más información, vea [Sondeo predeterminado](../../core/dependency-loading/default-probing.md).</span><span class="sxs-lookup"><span data-stu-id="4edc8-153">For more information, see [Default probing](../../core/dependency-loading/default-probing.md).</span></span>

<span data-ttu-id="4edc8-154">En el caso de las aplicaciones independientes, el usuario no tiene que hacer ninguna acción especial, aparte de asegurarse de que ICU está en el directorio de la aplicación (para las aplicaciones independientes, el directorio de trabajo tiene como valor predeterminado `NATIVE_DLL_SEARCH_DIRECTORIES`).</span><span class="sxs-lookup"><span data-stu-id="4edc8-154">For self-contained apps, no special action is required by the user, other than making sure ICU is in the app directory (for self-contained apps, the working directory defaults to `NATIVE_DLL_SEARCH_DIRECTORIES`).</span></span>

<span data-ttu-id="4edc8-155">Si está usando ICU a través de un paquete NuGet, esto funciona en aplicaciones dependientes del marco.</span><span class="sxs-lookup"><span data-stu-id="4edc8-155">If you're consuming ICU via a NuGet package, this works in framework-dependent applications.</span></span> <span data-ttu-id="4edc8-156">NuGet resuelve los recursos nativos y los incluye en el archivo `deps.json` y en el directorio de salida de la aplicación en el directorio `runtimes`.</span><span class="sxs-lookup"><span data-stu-id="4edc8-156">NuGet resolves the native assets and includes them in the `deps.json` file and in the output directory for the application under the `runtimes` directory.</span></span> <span data-ttu-id="4edc8-157">.NET lo carga desde allí.</span><span class="sxs-lookup"><span data-stu-id="4edc8-157">.NET loads it from there.</span></span>

<span data-ttu-id="4edc8-158">En el caso de las aplicaciones dependientes del marco (no independientes) en las que se usa ICU desde una compilación local, debe realizar unos cuantos pasos más.</span><span class="sxs-lookup"><span data-stu-id="4edc8-158">For framework-dependent apps (not self contained) where ICU is consumed from a local build, you must take additional steps.</span></span> <span data-ttu-id="4edc8-159">El SDK de .NET todavía no tiene una característica para que los binarios nativos "sueltos" se incorporen en `deps.json` (vea [este problema del SDK](https://github.com/dotnet/sdk/issues/11373)).</span><span class="sxs-lookup"><span data-stu-id="4edc8-159">The .NET SDK doesn't yet have a feature for "loose" native binaries to be incorporated into `deps.json` (see [this SDK issue](https://github.com/dotnet/sdk/issues/11373)).</span></span> <span data-ttu-id="4edc8-160">En su lugar, puede habilitarlo si agrega información adicional en el archivo de proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4edc8-160">Instead, you can enable this by adding additional information into the application's project file.</span></span> <span data-ttu-id="4edc8-161">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4edc8-161">For example:</span></span>

```xml
<ItemGroup>
  <IcuAssemblies Include="icu\*.so*" />
  <RuntimeTargetsCopyLocalItems Include="@(IcuAssemblies)" AssetType="native" CopyLocal="true" DestinationSubDirectory="runtimes/linux-x64/native/" DestinationSubPath="%(FileName)%(Extension)" RuntimeIdentifier="linux-x64" NuGetPackageId="System.Private.Runtime.UnicodeData" />
</ItemGroup>
```

<span data-ttu-id="4edc8-162">Debe realizar esto en todos los archivos binarios de ICU de los entornos de ejecución admitidos.</span><span class="sxs-lookup"><span data-stu-id="4edc8-162">This must be done for all the ICU binaries for the supported runtimes.</span></span> <span data-ttu-id="4edc8-163">Además, los metadatos de `NuGetPackageId` del grupo de elementos `RuntimeTargetsCopyLocalItems` deben coincidir con un paquete NuGet al que realmente hace referencia el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4edc8-163">Also, the `NuGetPackageId` metadata in the `RuntimeTargetsCopyLocalItems` item group needs to match a NuGet package that the project actually references.</span></span>

### <a name="macos-behavior"></a><span data-ttu-id="4edc8-164">Comportamiento de macOS</span><span class="sxs-lookup"><span data-stu-id="4edc8-164">macOS behavior</span></span>

<span data-ttu-id="4edc8-165">El comportamiento que tiene `macOS` para resolver bibliotecas dinámicas dependientes a partir de los comandos de carga especificados en el archivo `match-o` es diferente al del cargador de Linux.</span><span class="sxs-lookup"><span data-stu-id="4edc8-165">`macOS` has a different behavior for resolving dependent dynamic libraries from the load commands specified in the `match-o` file than the Linux loader.</span></span> <span data-ttu-id="4edc8-166">En el cargador de Linux, .NET puede intentar `libicudata`, `libicuuc` y `libicui18n` (en ese orden) para satisfacer el gráfico de dependencias de ICU.</span><span class="sxs-lookup"><span data-stu-id="4edc8-166">In the Linux loader, .NET can try `libicudata`, `libicuuc`, and `libicui18n` (in that order) to satisfy ICU dependency graph.</span></span> <span data-ttu-id="4edc8-167">Pero esto no funciona en macOS.</span><span class="sxs-lookup"><span data-stu-id="4edc8-167">However, on macOS, this doesn't work.</span></span> <span data-ttu-id="4edc8-168">Al crear ICU en macOS, se obtiene de forma predeterminada una biblioteca dinámica con estos comandos de carga en `libicuuc`.</span><span class="sxs-lookup"><span data-stu-id="4edc8-168">When building ICU on macOS, you, by default, get a dynamic library with these load commands in `libicuuc`.</span></span> <span data-ttu-id="4edc8-169">En el fragmento de código siguiente se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4edc8-169">The following snippet shows an example.</span></span>

```sh
~/ % otool -L /Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib
/Users/santifdezm/repos/icu-build/icu/install/lib/libicuuc.67.1.dylib:
 libicuuc.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 libicudata.67.dylib (compatibility version 67.0.0, current version 67.1.0)
 /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1281.100.1)
 /usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 902.1.0)
```

<span data-ttu-id="4edc8-170">Estos comandos simplemente hacen referencia al nombre de las bibliotecas dependientes para los demás componentes de ICU.</span><span class="sxs-lookup"><span data-stu-id="4edc8-170">These commands just reference the name of the dependent libraries for the other components of ICU.</span></span> <span data-ttu-id="4edc8-171">El cargador realiza la búsqueda según las convenciones de `dlopen`, lo que implica tener estas bibliotecas en los directorios del sistema o configurar env vars de `LD_LIBRARY_PATH` o tener ICU en el directorio de nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4edc8-171">The loader performs the search following the `dlopen` conventions, which involves having these libraries in the system directories or setting the `LD_LIBRARY_PATH` env vars, or having ICU at the app-level directory.</span></span> <span data-ttu-id="4edc8-172">Si no puede establecer `LD_LIBRARY_PATH` o asegurarse de que los binarios de ICU se encuentran en el directorio de nivel de aplicación, deberá realizar algún trabajo adicional.</span><span class="sxs-lookup"><span data-stu-id="4edc8-172">If you can't set `LD_LIBRARY_PATH` or ensure that ICU binaries are at the app-level directory, you will need to do some extra work.</span></span>

<span data-ttu-id="4edc8-173">Hay algunas directivas para el cargador, como `@loader_path`, que indican al cargador que busque esa dependencia en el mismo directorio que el binario con ese comando de carga.</span><span class="sxs-lookup"><span data-stu-id="4edc8-173">There are some directives for the loader, like `@loader_path`, which tell the loader to search for that dependency in the same directory as the binary with that load command.</span></span> <span data-ttu-id="4edc8-174">Hay dos formas de lograrlo:</span><span class="sxs-lookup"><span data-stu-id="4edc8-174">There are two ways to achieve this:</span></span>

- `install_name_tool -change`

  <span data-ttu-id="4edc8-175">Ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4edc8-175">Run the following commands:</span></span>

  ```bash
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicuuc.67.1.dylib
  install_name_tool -change "libicudata.67.dylib" "@loader_path/libicudata.67.dylib" /path/to/libicui18n.67.1.dylib
  install_name_tool -change "libicuuc.67.dylib" "@loader_path/libicuuc.67.dylib" /path/to/libicui18n.67.1.dylib
  ```

- <span data-ttu-id="4edc8-176">Revisión de ICU para generar los nombres de instalación con `@loader_path`</span><span class="sxs-lookup"><span data-stu-id="4edc8-176">Patch ICU to produce the install names with `@loader_path`</span></span>

  <span data-ttu-id="4edc8-177">Antes de ejecutar autoconf (`./runConfigureICU`), cambie [estas líneas](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) a:</span><span class="sxs-lookup"><span data-stu-id="4edc8-177">Before running autoconf (`./runConfigureICU`), change [these lines](https://github.com/unicode-org/icu/blob/ef91cc3673d69a5e00407cda94f39fcda3131451/icu4c/source/config/mh-darwin#L32-L37) to:</span></span>

  ```
  LD_SONAME = -Wl,-compatibility_version -Wl,$(SO_TARGET_VERSION_MAJOR) -Wl,-current_version -Wl,$(SO_TARGET_VERSION) -install_name @loader_path/$(notdir $(MIDDLE_SO_TARGET))
  ```

## <a name="icu-on-webassembly"></a><span data-ttu-id="4edc8-178">ICU en WebAssembly</span><span class="sxs-lookup"><span data-stu-id="4edc8-178">ICU on WebAssembly</span></span>

<span data-ttu-id="4edc8-179">Hay disponible una versión de ICU que es específicamente para cargas de trabajo de WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="4edc8-179">A version of ICU is available that's specifically for WebAssembly workloads.</span></span> <span data-ttu-id="4edc8-180">Esta versión proporciona compatibilidad de globalización con los perfiles de escritorio.</span><span class="sxs-lookup"><span data-stu-id="4edc8-180">This version provides globalization compatibility with desktop profiles.</span></span> <span data-ttu-id="4edc8-181">Para reducir el tamaño del archivo de datos de ICU de 24 MB a 1,4 MB (o ~ 0,3 MB si está comprimido con Brotli), esta carga de trabajo tiene una serie de limitaciones.</span><span class="sxs-lookup"><span data-stu-id="4edc8-181">To reduce the ICU data file size from 24 MB to 1.4 MB (or ~0.3 MB if compressed with Brotli), this workload has a handful of limitations.</span></span>

<span data-ttu-id="4edc8-182">No se admiten las siguientes API:</span><span class="sxs-lookup"><span data-stu-id="4edc8-182">The following APIs are not supported:</span></span>

- <xref:System.Globalization.CultureInfo.EnglishName?displayProperty=nameWithType>
- <xref:System.Globalization.CultureInfo.NativeName?displayProperty=nameWithType>
- <xref:System.Globalization.DateTimeFormatInfo.NativeCalendarName?displayProperty=nameWithType>
- <xref:System.Globalization.RegionInfo.NativeName?displayProperty=nameWithType>

<span data-ttu-id="4edc8-183">Las siguientes API se admiten con limitaciones:</span><span class="sxs-lookup"><span data-stu-id="4edc8-183">The following APIs are supported with limitations:</span></span>

- <span data-ttu-id="4edc8-184"><xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> y <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> no admiten los formularios <xref:System.Text.NormalizationForm.FormKC> y <xref:System.Text.NormalizationForm.FormKD> poco usados.</span><span class="sxs-lookup"><span data-stu-id="4edc8-184"><xref:System.String.Normalize(System.Text.NormalizationForm)?displayProperty=nameWithType> and <xref:System.String.IsNormalized(System.Text.NormalizationForm)?displayProperty=nameWithType> don't support the rarely used <xref:System.Text.NormalizationForm.FormKC> and <xref:System.Text.NormalizationForm.FormKD> forms.</span></span>
- <span data-ttu-id="4edc8-185"><xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> devuelve el mismo valor que <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4edc8-185"><xref:System.Globalization.RegionInfo.CurrencyNativeName?displayProperty=nameWithType> returns the same value as <xref:System.Globalization.RegionInfo.CurrencyEnglishName?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="4edc8-186">Además, puede encontrar una lista de configuraciones regionales admitidas en el repositorio [dotnet/ICU](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).</span><span class="sxs-lookup"><span data-stu-id="4edc8-186">In addition, a list of supported locales can be found on the [dotnet/icu repo](https://github.com/dotnet/icu/blob/0f49268ddfd3331ca090f1c51d2baa2f75f6c6c0/icu-filters/optimal.json#L6-L54).</span></span>
