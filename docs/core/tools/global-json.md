---
title: Información general de global.json
description: Obtenga información sobre cómo usar el archivo global.json para establecer la versión del SDK de .NET Core al ejecutar comandos de la CLI de .NET Core.
ms.date: 12/03/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 4da703266e98b209cdd031f4ea856b4d7c83930c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714168"
---
# <a name="globaljson-overview"></a><span data-ttu-id="f7385-103">Información general de global.json</span><span class="sxs-lookup"><span data-stu-id="f7385-103">global.json overview</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

<span data-ttu-id="f7385-104">El archivo *global.json* permite definir qué versión del SDK de .NET Core se usa al ejecutar comandos de la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f7385-104">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="f7385-105">La selección del SDK de .NET Core es independiente de especificar el runtime al que está destinado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7385-105">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="f7385-106">La versión del SDK de .NET Core indica qué versiones de las herramientas de la CLI de .NET Core se usan.</span><span class="sxs-lookup"><span data-stu-id="f7385-106">The .NET Core SDK version indicates which versions of the .NET Core CLI tools are used.</span></span> <span data-ttu-id="f7385-107">En general, le interesa usar la versión más reciente de las herramientas, por lo que no es necesario ningún archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="f7385-107">In general, you want to use the latest version of the tools, so no *global.json* file is needed.</span></span>

<span data-ttu-id="f7385-108">Para obtener más información sobre cómo especificar el runtime en su lugar, vea [Plataformas de destino](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="f7385-108">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="f7385-109">El SDK de .NET Core busca un archivo *global.json* en el directorio de trabajo actual (que no es necesariamente el mismo que el directorio del proyecto) o en uno de sus directorios principales.</span><span class="sxs-lookup"><span data-stu-id="f7385-109">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="f7385-110">Esquema de global.JSON</span><span class="sxs-lookup"><span data-stu-id="f7385-110">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="f7385-111">sdk</span><span class="sxs-lookup"><span data-stu-id="f7385-111">sdk</span></span>

<span data-ttu-id="f7385-112">Tipo: Object</span><span class="sxs-lookup"><span data-stu-id="f7385-112">Type: Object</span></span>

<span data-ttu-id="f7385-113">Especifica información sobre el SDK de .NET Core que se va a seleccionar.</span><span class="sxs-lookup"><span data-stu-id="f7385-113">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="f7385-114">version</span><span class="sxs-lookup"><span data-stu-id="f7385-114">version</span></span>

<span data-ttu-id="f7385-115">Tipo: String</span><span class="sxs-lookup"><span data-stu-id="f7385-115">Type: String</span></span>

<span data-ttu-id="f7385-116">La versión del SDK de .NET Core que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="f7385-116">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="f7385-117">Tenga en cuenta que este campo:</span><span class="sxs-lookup"><span data-stu-id="f7385-117">Note that this field:</span></span>

- <span data-ttu-id="f7385-118">No admite comodines, es decir, se debe especificar el número de versión completo.</span><span class="sxs-lookup"><span data-stu-id="f7385-118">Doesn't have globbing support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="f7385-119">No admite intervalos de versiones.</span><span class="sxs-lookup"><span data-stu-id="f7385-119">Doesn't support version ranges.</span></span>

<span data-ttu-id="f7385-120">En el ejemplo siguiente se muestra el contenido de un archivo *global.json*:</span><span class="sxs-lookup"><span data-stu-id="f7385-120">The following example shows the contents of a *global.json* file:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="f7385-121">global.json y la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f7385-121">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="f7385-122">Resulta útil saber qué versiones están disponibles con el fin de establecer una en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="f7385-122">It's helpful to know which versions are available in order to set one in the *global.json* file.</span></span> <span data-ttu-id="f7385-123">Puede encontrar la lista completa de los SDK disponibles admitidos en la página de [descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="f7385-123">You can find the full list of supported available SDKs at the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span> <span data-ttu-id="f7385-124">A partir del SDK de .NET Core SDK 2.1, puede ejecutar el comando siguiente para comprobar qué versiones del SDK ya están instaladas en el equipo:</span><span class="sxs-lookup"><span data-stu-id="f7385-124">Starting with .NET Core 2.1 SDK, you can run the following command to verify which SDK versions are already installed on your machine:</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="f7385-125">Para instalar otras versiones del SDK de .NET Core en el equipo, visite la página de [descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="f7385-125">To install additional .NET Core SDK versions on your machine, visit the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>

<span data-ttu-id="f7385-126">Puede crear un archivo *global.json* en el directorio actual mediante la ejecución del comando [dotnet new](dotnet-new.md), similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7385-126">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 2.2.100
```

## <a name="matching-rules"></a><span data-ttu-id="f7385-127">Reglas de coincidencia</span><span class="sxs-lookup"><span data-stu-id="f7385-127">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="f7385-128">Las reglas de coincidencia se rigen por el host de aplicaciones, que forma parte del runtime de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f7385-128">The matching rules are governed by the apphost, which is part of the .NET Core runtime.</span></span>
> <span data-ttu-id="f7385-129">Cuando hay varios runtimes instalados en paralelo, se usa la versión más reciente del host.</span><span class="sxs-lookup"><span data-stu-id="f7385-129">The latest version of the host is used when you have multiple runtimes installed side-by-side.</span></span>

<span data-ttu-id="f7385-130">A partir de .NET Core 2.0, se aplican las reglas siguientes al determinar qué versión del SDK se va a usar:</span><span class="sxs-lookup"><span data-stu-id="f7385-130">Starting with .NET Core 2.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="f7385-131">Si no se encuentra ningún archivo *global.json* o en *global.json* no se especifica una versión del SDK, se usa la versión instalada del SDK más reciente.</span><span class="sxs-lookup"><span data-stu-id="f7385-131">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="f7385-132">La versión del SDK más reciente puede ser la versión o la versión preliminar: prevalece el número de versión más alto.</span><span class="sxs-lookup"><span data-stu-id="f7385-132">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>
- <span data-ttu-id="f7385-133">Si *global.json* especifica una versión del SDK:</span><span class="sxs-lookup"><span data-stu-id="f7385-133">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="f7385-134">Si la versión del SDK especificada se encuentra en el equipo, se usa esa versión exacta.</span><span class="sxs-lookup"><span data-stu-id="f7385-134">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="f7385-135">Si la versión del SDK especificada no se encuentra en el equipo, se usa la **versión de revisión** del SDK instalada más reciente de esa versión.</span><span class="sxs-lookup"><span data-stu-id="f7385-135">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="f7385-136">La **versión de revisión** del SDK instalada más reciente puede ser la versión o la versión preliminar: prevalece el número de versión más alto.</span><span class="sxs-lookup"><span data-stu-id="f7385-136">Latest installed SDK **patch version** can be either release or pre-release - the highest version number wins.</span></span> <span data-ttu-id="f7385-137">En .NET Core 2.1 y versiones posteriores, las **versiones de revisión** inferiores a la **versión de revisión** especificada se omiten en la selección del SDK.</span><span class="sxs-lookup"><span data-stu-id="f7385-137">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="f7385-138">Si no se encuentra la versión del SDK especificada y una **versión de revisión** adecuada del SDK, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="f7385-138">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="f7385-139">Actualmente, la versión del SDK se compone de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f7385-139">The SDK version is currently composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="f7385-140">La **versión de características** del SDK de .NET Core se representa por medio del primer dígito (`x`) de la última parte del número (`xyz`) para las versiones 2.1.100 del SDK y posteriores.</span><span class="sxs-lookup"><span data-stu-id="f7385-140">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="f7385-141">En general, el SDK de .NET Core tiene un ciclo de versiones más rápido que .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f7385-141">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="f7385-142">La **versión de revisión** se define mediante los dos últimos dígitos (`yz`) de la última parte del número (`xyz`) para las versiones 2.1.100 del SDK y posteriores.</span><span class="sxs-lookup"><span data-stu-id="f7385-142">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="f7385-143">Por ejemplo, si especifica `2.1.300` como la versión del SDK, la selección del SDK busca hasta `2.1.399` pero `2.1.400` no se considera una versión de revisión para `2.1.300`.</span><span class="sxs-lookup"><span data-stu-id="f7385-143">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="f7385-144">Las versiones del SDK de .NET Core de `2.1.100` a `2.1.201` se publicaron durante la transición entre las combinaciones de número de versión y no procesan correctamente la notación `xyz`.</span><span class="sxs-lookup"><span data-stu-id="f7385-144">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="f7385-145">Si estas versiones se especifican en el archivo *global.json*, se recomienda encarecidamente asegurarse de que las versiones especificadas están en los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="f7385-145">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

<span data-ttu-id="f7385-146">Con el SDK 1.x de .NET Core, si se especificaba una versión y no se encontraba ninguna coincidencia exacta, se usaba la versión del SDK instalada más reciente.</span><span class="sxs-lookup"><span data-stu-id="f7385-146">With .NET Core SDK 1.x, if you specified a version and no exact match was found, the latest installed SDK version was used.</span></span> <span data-ttu-id="f7385-147">La versión del SDK más reciente puede ser la versión o la versión preliminar: prevalece el número de versión más alto.</span><span class="sxs-lookup"><span data-stu-id="f7385-147">Latest SDK version can be either release or pre-release - the highest version number wins.</span></span>

## <a name="troubleshooting-build-warnings"></a><span data-ttu-id="f7385-148">Solución de problemas de advertencias de compilación</span><span class="sxs-lookup"><span data-stu-id="f7385-148">Troubleshooting build warnings</span></span>

> [!WARNING]
> <span data-ttu-id="f7385-149">Trabaja con una versión preliminar del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f7385-149">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="f7385-150">Puede definir la versión del SDK a través de un archivo global.json en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="f7385-150">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="f7385-151">Más información en <https://go.microsoft.com/fwlink/?linkid=869452>.</span><span class="sxs-lookup"><span data-stu-id="f7385-151">More at <https://go.microsoft.com/fwlink/?linkid=869452></span></span>

<span data-ttu-id="f7385-152">Esta advertencia indica que el proyecto se está compilando con una versión preliminar del SDK de .NET Core, como se explica en la sección [Reglas de coincidencia](#matching-rules).</span><span class="sxs-lookup"><span data-stu-id="f7385-152">This warning indicates that your project is being compiled using a preview version of the .NET Core SDK, as explained in the [Matching rules](#matching-rules) section.</span></span> <span data-ttu-id="f7385-153">Las versiones del SDK de .NET Core tienen un historial y el compromiso de ser de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="f7385-153">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="f7385-154">Pero si no quiere usar una versión preliminar, agregue un archivo *global.json* a la estructura de jerarquía del proyecto para especificar qué versión del SDK se va a utilizar, y use `dotnet --list-sdks` para confirmar que la versión está instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="f7385-154">However, if you don't want to use a preview version, add a *global.json* file to your project hierarchy structure to specify which SDK version to use, and use `dotnet --list-sdks` to confirm that the version is installed on your machine.</span></span> <span data-ttu-id="f7385-155">Cuando se publica una versión nueva, para usarla, quite el archivo *global.json* o actualícelo para usar la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="f7385-155">When a new version is released, to use the new version, either remove the *global.json* file or update it to use the newer version.</span></span>

> [!WARNING]
> <span data-ttu-id="f7385-156">El proyecto de inicio "{proyectoDeInicio}" está destinado a la versión "{versiónPlataformaDeDestino}" de ".NETCoreApp".</span><span class="sxs-lookup"><span data-stu-id="f7385-156">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="f7385-157">Esta versión de las herramientas de línea de comandos de Entity Framework Core .NET solo admite la versión 2.0 o superior.</span><span class="sxs-lookup"><span data-stu-id="f7385-157">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="f7385-158">Para obtener información sobre el uso de las versiones anteriores de las herramientas, vea <https://go.microsoft.com/fwlink/?linkid=871254></span><span class="sxs-lookup"><span data-stu-id="f7385-158">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254></span></span>

<span data-ttu-id="f7385-159">A partir del SDK de .NET Core 2.1 (versión 2.1.300), el comando `dotnet ef` se incluye en el SDK.</span><span class="sxs-lookup"><span data-stu-id="f7385-159">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="f7385-160">Esta advertencia indica que el proyecto tiene como destino EF Core 1.0 ó 1.1, que no es compatible con el SDK de .NET Core 2.1 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f7385-160">This warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions.</span></span> <span data-ttu-id="f7385-161">Para compilar el proyecto, instale el SDK de .NET Core 2.0 (versión 2.1.201) y versiones anteriores en el equipo y defina la versión del SDK deseada mediante el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="f7385-161">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) and earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="f7385-162">Para obtener más información sobre el comando `dotnet ef`, vea [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet) (Herramientas de línea de comandos de EF Core .NET).</span><span class="sxs-lookup"><span data-stu-id="f7385-162">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="f7385-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7385-163">See also</span></span>

- [<span data-ttu-id="f7385-164">Resolución de los SDK de proyecto</span><span class="sxs-lookup"><span data-stu-id="f7385-164">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
