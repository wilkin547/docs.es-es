---
title: Información general de global.json
description: Obtenga información sobre cómo usar el archivo global.json para establecer la versión del SDK de .NET al ejecutar comandos de la CLI de .NET.
ms.topic: how-to
ms.date: 05/01/2020
ms.custom: updateeachrelease
ms.openlocfilehash: cc471cf5b50cf91c38b46607ccf38bd4d087aa6a
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104146"
---
# <a name="globaljson-overview"></a><span data-ttu-id="88d00-103">Información general de global.json</span><span class="sxs-lookup"><span data-stu-id="88d00-103">global.json overview</span></span>

<span data-ttu-id="88d00-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="88d00-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<span data-ttu-id="88d00-105">El archivo *global.json* permite definir qué versión del SDK de .NET se usa al ejecutar comandos de la CLI de .NET.</span><span class="sxs-lookup"><span data-stu-id="88d00-105">The *global.json* file allows you to define which .NET SDK version is used when you run .NET CLI commands.</span></span> <span data-ttu-id="88d00-106">La selección del SDK de .NET es independiente de especificar el entorno de ejecución al que está destinado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="88d00-106">Selecting the .NET SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="88d00-107">La versión del SDK de .NET indica qué versiones de la CLI de .NET se usan.</span><span class="sxs-lookup"><span data-stu-id="88d00-107">The .NET SDK version indicates which versions of the .NET CLI is used.</span></span>

<span data-ttu-id="88d00-108">En general, se quiere usar la versión más reciente de las herramientas del SDK, por lo que no es necesario ningún archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="88d00-108">In general, you want to use the latest version of the SDK tools, so no *global.json* file is needed.</span></span> <span data-ttu-id="88d00-109">En algunos escenarios avanzados, es posible que quiera controlar la versión de las herramientas del SDK, así que en este artículo se explica cómo.</span><span class="sxs-lookup"><span data-stu-id="88d00-109">In some advanced scenarios, you might want to control the version of the SDK tools, and this article explains how to do this.</span></span>

<span data-ttu-id="88d00-110">Para obtener más información sobre cómo especificar el runtime en su lugar, vea [Plataformas de destino](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="88d00-110">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="88d00-111">El SDK de .NET busca un archivo *global.json* en el directorio de trabajo actual (que no es necesariamente el mismo que el directorio del proyecto) o en uno de sus directorios principales.</span><span class="sxs-lookup"><span data-stu-id="88d00-111">The .NET SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="88d00-112">Esquema de global.JSON</span><span class="sxs-lookup"><span data-stu-id="88d00-112">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="88d00-113">sdk</span><span class="sxs-lookup"><span data-stu-id="88d00-113">sdk</span></span>

<span data-ttu-id="88d00-114">Tipo: `object`</span><span class="sxs-lookup"><span data-stu-id="88d00-114">Type: `object`</span></span>

<span data-ttu-id="88d00-115">Especifica información sobre el SDK de .NET que se va a seleccionar.</span><span class="sxs-lookup"><span data-stu-id="88d00-115">Specifies information about the .NET SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="88d00-116">version</span><span class="sxs-lookup"><span data-stu-id="88d00-116">version</span></span>

- <span data-ttu-id="88d00-117">Tipo: `string`</span><span class="sxs-lookup"><span data-stu-id="88d00-117">Type: `string`</span></span>

- <span data-ttu-id="88d00-118">Disponible a partir del SDK de .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="88d00-118">Available since: .NET Core 1.0 SDK.</span></span>

<span data-ttu-id="88d00-119">La versión del SDK de .NET que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="88d00-119">The version of the .NET SDK to use.</span></span>

<span data-ttu-id="88d00-120">Este campo:</span><span class="sxs-lookup"><span data-stu-id="88d00-120">This field:</span></span>

- <span data-ttu-id="88d00-121">No admite caracteres comodín, es decir, se debe especificar el número de versión completo.</span><span class="sxs-lookup"><span data-stu-id="88d00-121">Doesn't have wildcard support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="88d00-122">No admite intervalos de versiones.</span><span class="sxs-lookup"><span data-stu-id="88d00-122">Doesn't support version ranges.</span></span>

#### <a name="allowprerelease"></a><span data-ttu-id="88d00-123">allowPrerelease</span><span class="sxs-lookup"><span data-stu-id="88d00-123">allowPrerelease</span></span>

- <span data-ttu-id="88d00-124">Tipo: `boolean`</span><span class="sxs-lookup"><span data-stu-id="88d00-124">Type: `boolean`</span></span>

- <span data-ttu-id="88d00-125">Disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="88d00-125">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="88d00-126">Indica si la resolución del SDK debe tener en cuenta las versiones preliminares a la hora de seleccionar la versión del SDK que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="88d00-126">Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>

<span data-ttu-id="88d00-127">Si no se establece este valor de forma explícita, el valor predeterminado depende de si se está ejecutando desde Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="88d00-127">If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:</span></span>

- <span data-ttu-id="88d00-128">Si **no** se está en Visual Studio, el valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="88d00-128">If you're **not** in Visual Studio, the default value is `true`.</span></span>
- <span data-ttu-id="88d00-129">Si se está en Visual Studio, se usa el estado de versión preliminar solicitado.</span><span class="sxs-lookup"><span data-stu-id="88d00-129">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="88d00-130">Es decir, si se usa una versión preliminar de Visual Studio o se establece la opción **Usar versiones preliminares del SDK de .NET Core** (en **Herramientas** > **Opciones** > **Entorno** > **Características en versión preliminar**), el valor predeterminado es `true`; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="88d00-130">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), the default value is `true`; otherwise, `false`.</span></span>

#### <a name="rollforward"></a><span data-ttu-id="88d00-131">rollForward</span><span class="sxs-lookup"><span data-stu-id="88d00-131">rollForward</span></span>

- <span data-ttu-id="88d00-132">Tipo: `string`</span><span class="sxs-lookup"><span data-stu-id="88d00-132">Type: `string`</span></span>

- <span data-ttu-id="88d00-133">Disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="88d00-133">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="88d00-134">Directiva de puesta al día que se va a usar al seleccionar una versión del SDK, ya sea como reserva si falta una versión específica del SDK o como una directiva para usar una versión superior.</span><span class="sxs-lookup"><span data-stu-id="88d00-134">The roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span> <span data-ttu-id="88d00-135">Se debe especificar una [versión](#version) con un valor `rollForward`, a menos que se esté estableciendo en `latestMajor`.</span><span class="sxs-lookup"><span data-stu-id="88d00-135">A [version](#version) must be specified with a `rollForward` value, unless you're setting it to `latestMajor`.</span></span>
<span data-ttu-id="88d00-136">El comportamiento predeterminado de puesta al día lo determinan las [reglas de coincidencia](#matching-rules).</span><span class="sxs-lookup"><span data-stu-id="88d00-136">The default roll forward behavior is determined by the [matching rules](#matching-rules).</span></span>

<span data-ttu-id="88d00-137">Para comprender las directivas disponibles y su comportamiento, tenga en cuenta las siguientes definiciones de una versión del SDK en el formato `x.y.znn`:</span><span class="sxs-lookup"><span data-stu-id="88d00-137">To understand the available policies and their behavior, consider the following definitions for an SDK version in the format `x.y.znn`:</span></span>

- <span data-ttu-id="88d00-138">`x` es la versión principal.</span><span class="sxs-lookup"><span data-stu-id="88d00-138">`x` is the major version.</span></span>
- <span data-ttu-id="88d00-139">`y` es la versión secundaria.</span><span class="sxs-lookup"><span data-stu-id="88d00-139">`y` is the minor version.</span></span>
- <span data-ttu-id="88d00-140">`z` es la banda de características.</span><span class="sxs-lookup"><span data-stu-id="88d00-140">`z` is the feature band.</span></span>
- <span data-ttu-id="88d00-141">`nn` es la versión de la revisión.</span><span class="sxs-lookup"><span data-stu-id="88d00-141">`nn` is the patch version.</span></span>

<span data-ttu-id="88d00-142">En la siguiente tabla se muestran los posibles valores de la clave `rollForward`:</span><span class="sxs-lookup"><span data-stu-id="88d00-142">The following table shows the possible values for the `rollForward` key:</span></span>

| <span data-ttu-id="88d00-143">Valor</span><span class="sxs-lookup"><span data-stu-id="88d00-143">Value</span></span>         | <span data-ttu-id="88d00-144">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="88d00-144">Behavior</span></span> |
| ------------- | ---------- |
| `patch`       | <span data-ttu-id="88d00-145">Usa la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="88d00-145">Uses the specified version.</span></span> <br> <span data-ttu-id="88d00-146">Si no se encuentra, se pone al día hasta el nivel de revisión más reciente.</span><span class="sxs-lookup"><span data-stu-id="88d00-146">If not found, rolls forward to the latest patch level.</span></span> <br> <span data-ttu-id="88d00-147">Si no se encuentra, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="88d00-147">If not found, fails.</span></span> <br><br> <span data-ttu-id="88d00-148">Este valor es el comportamiento heredado de las versiones anteriores del SDK.</span><span class="sxs-lookup"><span data-stu-id="88d00-148">This value is the legacy behavior from the earlier versions of the SDK.</span></span> |
| `feature`     | <span data-ttu-id="88d00-149">Usa el nivel de revisión más reciente para las versiones principal y secundaria y la banda de características especificadas.</span><span class="sxs-lookup"><span data-stu-id="88d00-149">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="88d00-150">Si no se encuentra, se pone al día hasta la siguiente banda de características superior dentro de la misma versión principal/secundaria y usa el nivel de revisión más reciente para esa banda de características.</span><span class="sxs-lookup"><span data-stu-id="88d00-150">If not found, rolls forward to the next higher feature band within the same major/minor and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="88d00-151">Si no se encuentra, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="88d00-151">If not found, fails.</span></span> |
| `minor`       | <span data-ttu-id="88d00-152">Usa el nivel de revisión más reciente para las versiones principal y secundaria y la banda de características especificadas.</span><span class="sxs-lookup"><span data-stu-id="88d00-152">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="88d00-153">Si no se encuentra, se pone al día hasta la siguiente banda de características superior dentro de la misma versión principal/secundaria y usa el nivel de revisión más reciente para esa banda de características.</span><span class="sxs-lookup"><span data-stu-id="88d00-153">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="88d00-154">Si no se encuentra, se pone al día hasta la siguiente versión secundaria y banda de características superiores dentro de la misma versión principal y usa el nivel de revisión más reciente para esa banda de características.</span><span class="sxs-lookup"><span data-stu-id="88d00-154">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="88d00-155">Si no se encuentra, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="88d00-155">If not found, fails.</span></span> |
| `major`       | <span data-ttu-id="88d00-156">Usa el nivel de revisión más reciente para las versiones principal y secundaria y la banda de características especificadas.</span><span class="sxs-lookup"><span data-stu-id="88d00-156">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="88d00-157">Si no se encuentra, se pone al día hasta la siguiente banda de características superior dentro de la misma versión principal/secundaria y usa el nivel de revisión más reciente para esa banda de características.</span><span class="sxs-lookup"><span data-stu-id="88d00-157">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="88d00-158">Si no se encuentra, se pone al día hasta la siguiente versión secundaria y banda de características superiores dentro de la misma versión principal y usa el nivel de revisión más reciente para esa banda de características.</span><span class="sxs-lookup"><span data-stu-id="88d00-158">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="88d00-159">Si no se encuentra, se pone al día hasta la siguiente versión principal, secundaria y banda de características superiores y usa el nivel de revisión más reciente para esa banda de características.</span><span class="sxs-lookup"><span data-stu-id="88d00-159">If not found, rolls forward to the next higher major, minor, and feature band and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="88d00-160">Si no se encuentra, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="88d00-160">If not found, fails.</span></span> |
| `latestPatch` | <span data-ttu-id="88d00-161">Usa el nivel de revisión instalado más reciente que coincide con la versión principal, secundaria y banda de características solicitadas con un nivel de revisión y que es mayor o igual que el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="88d00-161">Uses the latest installed patch level that matches the requested major, minor, and feature band with a patch level and that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="88d00-162">Si no se encuentra, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="88d00-162">If not found, fails.</span></span> |
| `latestFeature` | <span data-ttu-id="88d00-163">Usa la banda de características instalada superior y el nivel de revisión que coincide con la versión principal y secundaria solicitados con una banda de características y un nivel de revisión que es mayor o igual que el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="88d00-163">Uses the highest installed feature band and patch level that matches the requested major and minor with a feature band and patch level that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="88d00-164">Si no se encuentra, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="88d00-164">If not found, fails.</span></span> |
| `latestMinor` | <span data-ttu-id="88d00-165">Usa la versión secundaria y la banda de características instalados superiores y la versión de revisión que coincide con la versión principal solicitada con una versión secundaria que es mayor o igual que el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="88d00-165">Uses the highest installed minor, feature band, and patch level that matches the requested major with a minor, feature band, and patch level that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="88d00-166">Si no se encuentra, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="88d00-166">If not found, fails.</span></span> |
| `latestMajor` | <span data-ttu-id="88d00-167">Usa el SDK de .NET más reciente que haya instalado con una versión que es mayor o igual que el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="88d00-167">Uses the highest installed .NET SDK with a version that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="88d00-168">Si no se encuentra, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="88d00-168">If not found, fail.</span></span> |
| `disable`     | <span data-ttu-id="88d00-169">No se pone al día.</span><span class="sxs-lookup"><span data-stu-id="88d00-169">Doesn't roll forward.</span></span> <span data-ttu-id="88d00-170">Se requiere una coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="88d00-170">Exact match required.</span></span> |

### <a name="msbuild-sdks"></a><span data-ttu-id="88d00-171">msbuild-sdks</span><span class="sxs-lookup"><span data-stu-id="88d00-171">msbuild-sdks</span></span>

<span data-ttu-id="88d00-172">Tipo: `object`</span><span class="sxs-lookup"><span data-stu-id="88d00-172">Type: `object`</span></span>

<span data-ttu-id="88d00-173">Permite controlar la versión del SDK del proyecto en un lugar, en vez de hacerlo en cada proyecto individual.</span><span class="sxs-lookup"><span data-stu-id="88d00-173">Lets you control the project SDK version in one place rather than in each individual project.</span></span> <span data-ttu-id="88d00-174">Para más información, vea [Resolución de los SDK de proyecto](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).</span><span class="sxs-lookup"><span data-stu-id="88d00-174">For more information, see [How project SDKs are resolved](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).</span></span>

## <a name="examples"></a><span data-ttu-id="88d00-175">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="88d00-175">Examples</span></span>

<span data-ttu-id="88d00-176">En el ejemplo siguiente se muestra cómo no usar versiones preliminares:</span><span class="sxs-lookup"><span data-stu-id="88d00-176">The following example shows how to not use prerelease versions:</span></span>

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

<span data-ttu-id="88d00-177">En este ejemplo se muestra cómo usar la versión superior instalada que es mayor o igual que la versión especificada.</span><span class="sxs-lookup"><span data-stu-id="88d00-177">The following example shows how to use the highest version installed that is greater or equal than the specified version.</span></span> <span data-ttu-id="88d00-178">El JSON mostrado no permite ninguna versión del SDK anterior a 2.2.200 y permite 2.2.200 o cualquier versión posterior, incluidos 3.0.xxx y 3.1.xxx.</span><span class="sxs-lookup"><span data-stu-id="88d00-178">The JSON shown disallows any SDK version earlier than 2.2.200 and allows 2.2.200 or any later version, including 3.0.xxx and 3.1.xxx.</span></span>

```json
{
  "sdk": {
    "version": "2.2.200",
    "rollForward": "latestMajor"
  }
}
```

<span data-ttu-id="88d00-179">En el ejemplo siguiente se muestra cómo usar la versión exacta especificada:</span><span class="sxs-lookup"><span data-stu-id="88d00-179">The following example shows how to use the exact specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

<span data-ttu-id="88d00-180">En este ejemplo se muestra cómo usar la versión de revisión y banda de características más reciente instalada de una versión principal y secundaria concreta.</span><span class="sxs-lookup"><span data-stu-id="88d00-180">The following example shows how to use the latest feature band and patch version installed of a specific major and minor version.</span></span> <span data-ttu-id="88d00-181">El JSON mostrado no permite ninguna versión del SDK anterior a 3.1.102 y permite 3.1.102 o cualquier versión 3.1.xxx posterior, como 3.1.103 o 3.1.200.</span><span class="sxs-lookup"><span data-stu-id="88d00-181">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any later 3.1.xxx version, such as 3.1.103 or 3.1.200.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestFeature"
  }
}
```

<span data-ttu-id="88d00-182">En este ejemplo se muestra cómo usar la versión de revisión superior instalada de una versión específica.</span><span class="sxs-lookup"><span data-stu-id="88d00-182">The following example shows how to use the highest patch version installed of a specific version.</span></span> <span data-ttu-id="88d00-183">El JSON mostrado no permite ninguna versión del SDK anterior a 3.1.102 y permite 3.1.102 o cualquier versión 3.1.1xx posterior, como 3.1.103 o 3.1.199.</span><span class="sxs-lookup"><span data-stu-id="88d00-183">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any later 3.1.1xx version, such as 3.1.103 or 3.1.199.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-cli"></a><span data-ttu-id="88d00-184">global.json y la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="88d00-184">global.json and the .NET CLI</span></span>

<span data-ttu-id="88d00-185">Resulta útil saber qué versiones del SDK están instaladas en el equipo con el fin de establecer una en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="88d00-185">It's helpful to know which SDK versions are installed on your machine to set one in the *global.json* file.</span></span> <span data-ttu-id="88d00-186">Para obtener más información sobre cómo hacerlo, vea [Cómo comprobar que .NET Core ya está instalado](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span><span class="sxs-lookup"><span data-stu-id="88d00-186">For more information on how to do that, see [How to check that .NET is already installed](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span></span>

<span data-ttu-id="88d00-187">Para instalar otras versiones del SDK de .NET en el equipo, visite la página [Descargas de .NET](https://dotnet.microsoft.com/download/dotnet).</span><span class="sxs-lookup"><span data-stu-id="88d00-187">To install additional .NET SDK versions on your machine, visit the [Download .NET](https://dotnet.microsoft.com/download/dotnet) page.</span></span>

<span data-ttu-id="88d00-188">Puede crear un archivo *global.json* en el directorio actual mediante la ejecución del comando [dotnet new](dotnet-new.md), similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="88d00-188">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a><span data-ttu-id="88d00-189">Reglas de coincidencia</span><span class="sxs-lookup"><span data-stu-id="88d00-189">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="88d00-190">Las reglas de coincidencia se rigen por el punto de entrada de `dotnet.exe`, que es común en todos los entornos de ejecución instalados de .NET.</span><span class="sxs-lookup"><span data-stu-id="88d00-190">The matching rules are governed by the `dotnet.exe` entry point, which is common across all installed .NET installed runtimes.</span></span> <span data-ttu-id="88d00-191">Se usan las reglas de coincidencia de la última versión instalada del entorno de ejecución de .NET cuando se tienen varios instalados en paralelo o si usa un archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="88d00-191">The matching rules for the latest installed version of the .NET Runtime are used when you have multiple runtimes installed side-by-side or if or you're using a *global.json* file.</span></span>

## <a name="net-core-3x"></a>[<span data-ttu-id="88d00-192">.NET Core 3.x</span><span class="sxs-lookup"><span data-stu-id="88d00-192">.NET Core 3.x</span></span>](#tab/netcore3x)

<span data-ttu-id="88d00-193">A partir de .NET Core 3.0, se aplican las reglas siguientes al determinar qué versión del SDK se va a usar:</span><span class="sxs-lookup"><span data-stu-id="88d00-193">Starting with .NET Core 3.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="88d00-194">Si no se encuentra ningún archivo *global.json* o en *global.json* no se especifica una versión del SDK ni un valor `allowPrerelease`, se usa la versión del SDK instalada más reciente (lo que equivale a establecer `rollForward` en `latestMajor`).</span><span class="sxs-lookup"><span data-stu-id="88d00-194">If no *global.json* file is found, or *global.json* doesn't specify an SDK version nor an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="88d00-195">El que se consideren o no las versiones preliminares del SDK depende de cómo se invoque a `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="88d00-195">Whether prerelease SDK versions are considered depends on how `dotnet` is being invoked.</span></span>
  - <span data-ttu-id="88d00-196">Si **no** se está en Visual Studio, se tienen en cuenta las versiones preliminares.</span><span class="sxs-lookup"><span data-stu-id="88d00-196">If you're **not** in Visual Studio, prerelease versions are considered.</span></span>
  - <span data-ttu-id="88d00-197">Si se está en Visual Studio, se usa el estado de versión preliminar solicitado.</span><span class="sxs-lookup"><span data-stu-id="88d00-197">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="88d00-198">Es decir, si se usa una versión preliminar de Visual Studio o se establece la opción **Usar versiones preliminares del SDK de .NET Core** (en **Herramientas** > **Opciones** > **Entorno** > **Características en versión preliminar**), se tienen en cuenta las versiones preliminares; de lo contrario, solo se consideran las versiones publicadas.</span><span class="sxs-lookup"><span data-stu-id="88d00-198">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), prerelease versions are considered; otherwise, only release versions are considered.</span></span>
- <span data-ttu-id="88d00-199">Si se encuentra un archivo *global.json* que no especifica una versión del SDK pero sí un valor `allowPrerelease`, se usa la versión del SDK instalada superior (lo que equivale a establecer `rollForward` en `latestMajor`).</span><span class="sxs-lookup"><span data-stu-id="88d00-199">If a *global.json* file is found that doesn't specify an SDK version but it specifies an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="88d00-200">El que la versión más reciente del SDK pueda ser publicada o preliminar, depende del valor de `allowPrerelease`.</span><span class="sxs-lookup"><span data-stu-id="88d00-200">Whether the latest SDK version can be release or prerelease depends on the value of `allowPrerelease`.</span></span> <span data-ttu-id="88d00-201">`true` indica que se tienen en cuenta las versiones preliminares; `false` indica que solo se tienen en cuenta las versiones publicadas.</span><span class="sxs-lookup"><span data-stu-id="88d00-201">`true` indicates prerelease versions are considered; `false` indicates that only release versions are considered.</span></span>
- <span data-ttu-id="88d00-202">Si se encuentra un archivo *global.json* y especifica una versión del SDK:</span><span class="sxs-lookup"><span data-stu-id="88d00-202">If a *global.json* file is found and it specifies an SDK version:</span></span>

  - <span data-ttu-id="88d00-203">Si no hay ningún valor `rollForward` establecido, se usa `latestPatch` como directiva de `rollForward` predeterminada.</span><span class="sxs-lookup"><span data-stu-id="88d00-203">If no `rollForward` value is set, it uses `latestPatch` as the default `rollForward` policy.</span></span> <span data-ttu-id="88d00-204">De lo contrario, vea cada valor y su comportamiento en la sección [rollForward](#rollforward).</span><span class="sxs-lookup"><span data-stu-id="88d00-204">Otherwise, check each value and their behavior in the [rollForward](#rollforward) section.</span></span>
  - <span data-ttu-id="88d00-205">En la sección [allowPrerelease](#allowprerelease) se explica si se tienen en cuenta las versiones preliminares y cuál es el comportamiento predeterminado cuando `allowPrerelease` no está establecido.</span><span class="sxs-lookup"><span data-stu-id="88d00-205">Whether prerelease versions are considered and what's the default behavior when `allowPrerelease` isn't set is described in the [allowPrerelease](#allowprerelease) section.</span></span>

## <a name="net-core-2x"></a>[<span data-ttu-id="88d00-206">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="88d00-206">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="88d00-207">En el SDK de .NET Core 2.x, se aplican las reglas siguientes a la hora de determinar qué versión del SDK se va a usar:</span><span class="sxs-lookup"><span data-stu-id="88d00-207">In .NET Core 2.x SDK, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="88d00-208">Si no se encuentra ningún archivo *global.json* o en *global.json* no se especifica una versión del SDK, se usa la versión instalada del SDK más reciente.</span><span class="sxs-lookup"><span data-stu-id="88d00-208">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="88d00-209">La versión del SDK más reciente puede ser la publicada o la preliminar: prevalece el número de versión más alto.</span><span class="sxs-lookup"><span data-stu-id="88d00-209">Latest SDK version can be either release or prerelease - the highest version number wins.</span></span>
- <span data-ttu-id="88d00-210">Si *global.json* especifica una versión del SDK:</span><span class="sxs-lookup"><span data-stu-id="88d00-210">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="88d00-211">Si la versión del SDK especificada se encuentra en el equipo, se usa esa versión exacta.</span><span class="sxs-lookup"><span data-stu-id="88d00-211">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="88d00-212">Si la versión del SDK especificada no se encuentra en el equipo, se usa la **versión de revisión** del SDK instalada más reciente de esa versión.</span><span class="sxs-lookup"><span data-stu-id="88d00-212">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="88d00-213">La **versión de revisión** del SDK instalada más reciente puede ser la publicada o la preliminar: prevalece el número de versión más alto.</span><span class="sxs-lookup"><span data-stu-id="88d00-213">Latest installed SDK **patch version** can be either release or prerelease - the highest version number wins.</span></span> <span data-ttu-id="88d00-214">En .NET Core 2.1 y versiones posteriores, las **versiones de revisión** inferiores a la **versión de revisión** especificada se omiten en la selección del SDK.</span><span class="sxs-lookup"><span data-stu-id="88d00-214">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="88d00-215">Si no se encuentra la versión del SDK especificada y una **versión de revisión** adecuada del SDK, se produce un error.</span><span class="sxs-lookup"><span data-stu-id="88d00-215">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="88d00-216">La versión del SDK se compone de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="88d00-216">The SDK version is composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="88d00-217">La **versión de características** del SDK de .NET Core se representa por medio del primer dígito (`x`) de la última parte del número (`xyz`) para las versiones 2.1.100 del SDK y posteriores.</span><span class="sxs-lookup"><span data-stu-id="88d00-217">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="88d00-218">En general, el SDK de .NET Core tiene un ciclo de versiones más rápido que .NET Core.</span><span class="sxs-lookup"><span data-stu-id="88d00-218">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="88d00-219">La **versión de revisión** se define mediante los dos últimos dígitos (`yz`) de la última parte del número (`xyz`) para las versiones 2.1.100 del SDK y posteriores.</span><span class="sxs-lookup"><span data-stu-id="88d00-219">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="88d00-220">Por ejemplo, si especifica `2.1.300` como la versión del SDK, la selección del SDK busca hasta `2.1.399` pero `2.1.400` no se considera una versión de revisión para `2.1.300`.</span><span class="sxs-lookup"><span data-stu-id="88d00-220">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="88d00-221">Las versiones del SDK de .NET Core de `2.1.100` a `2.1.201` se publicaron durante la transición entre las combinaciones de número de versión y no procesan correctamente la notación `xyz`.</span><span class="sxs-lookup"><span data-stu-id="88d00-221">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="88d00-222">Si estas versiones se especifican en el archivo *global.json*, se recomienda encarecidamente asegurarse de que las versiones especificadas están en los equipos de destino.</span><span class="sxs-lookup"><span data-stu-id="88d00-222">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

---

## <a name="troubleshoot-build-warnings"></a><span data-ttu-id="88d00-223">Solución de problemas de advertencias de compilación</span><span class="sxs-lookup"><span data-stu-id="88d00-223">Troubleshoot build warnings</span></span>

* <span data-ttu-id="88d00-224">La advertencia siguiente indica que el proyecto se ha compilado con una versión preliminar del SDK de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="88d00-224">The following warning indicates that your project was compiled using a prerelease version of the .NET Core SDK:</span></span>

  > <span data-ttu-id="88d00-225">Trabaja con una versión preliminar del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="88d00-225">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="88d00-226">Puede definir la versión del SDK a través de un archivo global.json en el proyecto actual.</span><span class="sxs-lookup"><span data-stu-id="88d00-226">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="88d00-227">Más información en <https://go.microsoft.com/fwlink/?linkid=869452>.</span><span class="sxs-lookup"><span data-stu-id="88d00-227">More at <https://go.microsoft.com/fwlink/?linkid=869452>.</span></span>

  <span data-ttu-id="88d00-228">Las versiones del SDK de .NET Core tienen un historial y el compromiso de ser de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="88d00-228">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="88d00-229">Pero si no quiere usar una versión preliminar, vea las distintas estrategias que puede aplicar con el SDK de .NET Core 3.0 o una versión posterior en la sección [allowPrerelease](#allowprerelease).</span><span class="sxs-lookup"><span data-stu-id="88d00-229">However, if you don't want to use a prerelease version, check the different strategies you can use with the .NET Core 3.0 SDK or a later version in the [allowPrerelease](#allowprerelease) section.</span></span> <span data-ttu-id="88d00-230">En el caso de los equipos que nunca han tenido instalado un SDK o un runtime de .NET Core 3.0 o superior, debe crear un archivo *global.json* y especificar la versión exacta que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="88d00-230">For machines that have never had a .NET Core 3.0 or higher Runtime or SDK installed, you need to create a *global.json* file and specify the exact version you want to use.</span></span>

* <span data-ttu-id="88d00-231">La advertencia siguiente indica que el proyecto tiene como destino EF Core 1.0 ó 1.1, que no es compatible con el SDK de .NET Core 2.1 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="88d00-231">The following warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions:</span></span>

  > <span data-ttu-id="88d00-232">El proyecto de inicio "{proyectoDeInicio}" está destinado a la versión "{versiónPlataformaDeDestino}" de ".NETCoreApp".</span><span class="sxs-lookup"><span data-stu-id="88d00-232">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="88d00-233">Esta versión de las herramientas de línea de comandos de Entity Framework Core .NET solo admite la versión 2.0 o superior.</span><span class="sxs-lookup"><span data-stu-id="88d00-233">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="88d00-234">Para obtener información sobre el uso de versiones anteriores de las herramientas, vea <https://go.microsoft.com/fwlink/?linkid=871254>.</span><span class="sxs-lookup"><span data-stu-id="88d00-234">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254>.</span></span>

  <span data-ttu-id="88d00-235">A partir del SDK de .NET Core 2.1 (versión 2.1.300), el comando `dotnet ef` se incluye en el SDK.</span><span class="sxs-lookup"><span data-stu-id="88d00-235">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="88d00-236">Para compilar el proyecto, instale el SDK de .NET Core 2.0 (versión 2.1.201) o versiones anteriores en el equipo y defina la versión del SDK deseada mediante el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="88d00-236">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) or earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="88d00-237">Para obtener más información sobre el comando `dotnet ef`, vea [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet) (Herramientas de línea de comandos de EF Core .NET).</span><span class="sxs-lookup"><span data-stu-id="88d00-237">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="88d00-238">Vea también</span><span class="sxs-lookup"><span data-stu-id="88d00-238">See also</span></span>

- [<span data-ttu-id="88d00-239">Resolución de los SDK de proyecto</span><span class="sxs-lookup"><span data-stu-id="88d00-239">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
