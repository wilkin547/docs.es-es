---
title: Telemetría del SDK de .NET Core
description: Descubra las características de telemetría del SDK de .NET Core que recopilan información de uso para el análisis, qué datos se recopilan y cómo deshabilitarlas.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: 9d5d7ff09ade89712f2fbbe35224851bb1c28b4c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156691"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="51e49-103">Telemetría del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="51e49-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="51e49-104">El [SDK de .NET Core](index.md) incluye una característica de telemetría que recopila datos de uso e información de excepción cuando se bloquea el CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51e49-104">The [.NET Core SDK](index.md) includes a telemetry feature that collects usage data and exception information when the .NET Core CLI crashes.</span></span> <span data-ttu-id="51e49-105">El CLI de .NET Core incluye el SDK de .NET Core y es el conjunto de verbos que permiten compilar, probar y publicar las aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51e49-105">The .NET Core CLI comes with the .NET Core SDK and is the set of verbs that enable you to build, test, and publish your .NET Core apps.</span></span> <span data-ttu-id="51e49-106">Es importante que el equipo de .NET entienda cómo se usan las herramientas con el fin de mejorarlas.</span><span class="sxs-lookup"><span data-stu-id="51e49-106">It's important that the .NET team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="51e49-107">Con la información sobre los errores, el equipo consigue resolver problemas y corregir errores.</span><span class="sxs-lookup"><span data-stu-id="51e49-107">Information on failures helps the team resolve problems and fix bugs.</span></span>

<span data-ttu-id="51e49-108">Los datos recopilados son anónimos y se publican de forma agregada bajo la [licencia de atribución de Creative Commons](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="51e49-108">The collected data is anonymous and published in aggregate under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="51e49-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="51e49-109">Scope</span></span>

<span data-ttu-id="51e49-110">`dotnet` tiene dos funciones: ejecutar aplicaciones y ejecutar comandos de la CLI.</span><span class="sxs-lookup"><span data-stu-id="51e49-110">`dotnet` has two functions: to run apps, and to execute CLI commands.</span></span> <span data-ttu-id="51e49-111">La telemetría *no se recopila* cuando se usa `dotnet` para iniciar una aplicación con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="51e49-111">Telemetry *isn't collected* when using `dotnet` to start an application in the following format:</span></span>

- `dotnet [path-to-app].dll`

<span data-ttu-id="51e49-112">La telemetría *se recopila* cuando se usa cualquiera de los [comandos de la CLI de .NET Core](index.md), como:</span><span class="sxs-lookup"><span data-stu-id="51e49-112">Telemetry *is collected* when using any of the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="51e49-113">Cómo desactivar la característica</span><span class="sxs-lookup"><span data-stu-id="51e49-113">How to opt out</span></span>

<span data-ttu-id="51e49-114">La característica de telemetría del SDK de .NET Core está habilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="51e49-114">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="51e49-115">Para desactivar la característica de telemetría, establezca la variable de entorno `DOTNET_CLI_TELEMETRY_OPTOUT` en `1` o `true`.</span><span class="sxs-lookup"><span data-stu-id="51e49-115">To opt out of the telemetry feature, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

<span data-ttu-id="51e49-116">El instalador del SDK de .NET Core también envía una única entrada de telemetría cuando se produce una instalación correcta.</span><span class="sxs-lookup"><span data-stu-id="51e49-116">A single telemetry entry is also sent by the .NET Core SDK installer when a successful installation happens.</span></span> <span data-ttu-id="51e49-117">Para desactivarla, establezca la variable de entorno de `DOTNET_CLI_TELEMETRY_OPTOUT` antes de instalar el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51e49-117">To opt out, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable before you install the .NET Core SDK.</span></span>

## <a name="disclosure"></a><span data-ttu-id="51e49-118">Divulgación</span><span class="sxs-lookup"><span data-stu-id="51e49-118">Disclosure</span></span>

<span data-ttu-id="51e49-119">El SDK de .NET Core muestra texto similar al siguiente cuando se ejecuta por primera vez uno de los [comandos de la CLI de .NET Core](index.md) (por ejemplo, `dotnet build`).</span><span class="sxs-lookup"><span data-stu-id="51e49-119">The .NET Core SDK displays text similar to the following when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet build`).</span></span> <span data-ttu-id="51e49-120">El texto puede variar ligeramente según la versión del SDK que ejecute.</span><span class="sxs-lookup"><span data-stu-id="51e49-120">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="51e49-121">Esta experiencia de "primera vista" es la forma en que Microsoft le notifica sobre la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="51e49-121">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience. The data is anonymous. It is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="data-points"></a><span data-ttu-id="51e49-122">Puntos de datos</span><span class="sxs-lookup"><span data-stu-id="51e49-122">Data points</span></span>

<span data-ttu-id="51e49-123">La característica de telemetría no recopila datos personales, como direcciones de correo electrónico o nombres de usuario.</span><span class="sxs-lookup"><span data-stu-id="51e49-123">The telemetry feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="51e49-124">No examina el código ni extrae datos de nivel de proyecto, como el nombre, el repositorio o el autor.</span><span class="sxs-lookup"><span data-stu-id="51e49-124">It doesn't scan your code and doesn't extract project-level data, such as name, repository, or author.</span></span> <span data-ttu-id="51e49-125">Los datos se envían de forma segura a los servidores de Microsoft con tecnología de [Azure Monitor](https://azure.microsoft.com/services/monitor/), se conservan bajo acceso restringido y se publican bajo controles de seguridad estrictos de sistemas seguros de [Azure Storage](https://azure.microsoft.com/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="51e49-125">The data is sent securely to Microsoft servers using [Azure Monitor](https://azure.microsoft.com/services/monitor/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="51e49-126">La protección de su privacidad es importante para nosotros.</span><span class="sxs-lookup"><span data-stu-id="51e49-126">Protecting your privacy is important to us.</span></span> <span data-ttu-id="51e49-127">Si sospecha que la telemetría está recopilando datos confidenciales o que los datos se están tratando de forma no segura o inapropiada, informe de un problema en el repositorio de [dotnet/cli](https://github.com/dotnet/cli/issues) o envíenos un correo electrónico a [dotnet@microsoft.com](mailto:dotnet@microsoft.com) para que lo investiguemos.</span><span class="sxs-lookup"><span data-stu-id="51e49-127">If you suspect the telemetry is collecting sensitive data or the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository or send an email to [dotnet@microsoft.com](mailto:dotnet@microsoft.com) for investigation.</span></span>

<span data-ttu-id="51e49-128">La característica de telemetría recopila los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="51e49-128">The telemetry feature collects the following data:</span></span>

| <span data-ttu-id="51e49-129">Versiones del SDK</span><span class="sxs-lookup"><span data-stu-id="51e49-129">SDK versions</span></span> | <span data-ttu-id="51e49-130">Datos</span><span class="sxs-lookup"><span data-stu-id="51e49-130">Data</span></span> |
|--------------|------|
| <span data-ttu-id="51e49-131">Todas</span><span class="sxs-lookup"><span data-stu-id="51e49-131">All</span></span>          | <span data-ttu-id="51e49-132">Marca de tiempo de la invocación.</span><span class="sxs-lookup"><span data-stu-id="51e49-132">Timestamp of invocation.</span></span> |
| <span data-ttu-id="51e49-133">Todas</span><span class="sxs-lookup"><span data-stu-id="51e49-133">All</span></span>          | <span data-ttu-id="51e49-134">Comando invocado (por ejemplo, "build"), con hash a partir de 2.1.</span><span class="sxs-lookup"><span data-stu-id="51e49-134">Command invoked (for example, "build"), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="51e49-135">Todas</span><span class="sxs-lookup"><span data-stu-id="51e49-135">All</span></span>          | <span data-ttu-id="51e49-136">Dirección IP de tres octetos usada para determinar la ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="51e49-136">Three octet IP address used to determine the geographical location.</span></span> |
| <span data-ttu-id="51e49-137">Todas</span><span class="sxs-lookup"><span data-stu-id="51e49-137">All</span></span>          | <span data-ttu-id="51e49-138">Sistema operativo y versión.</span><span class="sxs-lookup"><span data-stu-id="51e49-138">Operating system and version.</span></span> |
| <span data-ttu-id="51e49-139">Todas</span><span class="sxs-lookup"><span data-stu-id="51e49-139">All</span></span>          | <span data-ttu-id="51e49-140">Identificador de tiempo de ejecución (RID) en el que se ejecuta el SDK.</span><span class="sxs-lookup"><span data-stu-id="51e49-140">Runtime ID (RID) the SDK is running on.</span></span> |
| <span data-ttu-id="51e49-141">Todas</span><span class="sxs-lookup"><span data-stu-id="51e49-141">All</span></span>          | <span data-ttu-id="51e49-142">Versión del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="51e49-142">.NET Core SDK version.</span></span> |
| <span data-ttu-id="51e49-143">Todas</span><span class="sxs-lookup"><span data-stu-id="51e49-143">All</span></span>          | <span data-ttu-id="51e49-144">Perfil de telemetría: valor opcional usado internamente en Microsoft y que solo se usa con la participación explícita del usuario.</span><span class="sxs-lookup"><span data-stu-id="51e49-144">Telemetry profile: an optional value only used with explicit user opt-in and used internally at Microsoft.</span></span> |
| <span data-ttu-id="51e49-145">>=2.0</span><span class="sxs-lookup"><span data-stu-id="51e49-145">>=2.0</span></span>        | <span data-ttu-id="51e49-146">Opciones y argumentos del comando: se recopilan varias opciones y argumentos (no cadenas arbitrarias).</span><span class="sxs-lookup"><span data-stu-id="51e49-146">Command arguments and options: several arguments and options are collected (not arbitrary strings).</span></span> <span data-ttu-id="51e49-147">Vea [opciones recopiladas](#collected-options).</span><span class="sxs-lookup"><span data-stu-id="51e49-147">See [collected options](#collected-options).</span></span> <span data-ttu-id="51e49-148">Con hash a partir de la versión 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="51e49-148">Hashed after 2.1.300.</span></span> |
| <span data-ttu-id="51e49-149">>=2.0</span><span class="sxs-lookup"><span data-stu-id="51e49-149">>=2.0</span></span>         | <span data-ttu-id="51e49-150">Si el SDK se ejecuta en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="51e49-150">Whether the SDK is running in a container.</span></span> |
| <span data-ttu-id="51e49-151">>=2.0</span><span class="sxs-lookup"><span data-stu-id="51e49-151">>=2.0</span></span>         | <span data-ttu-id="51e49-152">Plataformas de destino (desde el evento `TargetFramework`), con hash a partir de 2.1.</span><span class="sxs-lookup"><span data-stu-id="51e49-152">Target frameworks (from the `TargetFramework` event), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="51e49-153">>=2.0</span><span class="sxs-lookup"><span data-stu-id="51e49-153">>=2.0</span></span>         | <span data-ttu-id="51e49-154">Dirección MAC con hash: identificador único y anónimo criptográficamente (SHA256) para una máquina.</span><span class="sxs-lookup"><span data-stu-id="51e49-154">Hashed Media Access Control (MAC) address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> |
| <span data-ttu-id="51e49-155">>=2.0</span><span class="sxs-lookup"><span data-stu-id="51e49-155">>=2.0</span></span>         | <span data-ttu-id="51e49-156">Directorio de trabajo actual con hash.</span><span class="sxs-lookup"><span data-stu-id="51e49-156">Hashed current working directory.</span></span> |
| <span data-ttu-id="51e49-157">>=2.0</span><span class="sxs-lookup"><span data-stu-id="51e49-157">>=2.0</span></span>         | <span data-ttu-id="51e49-158">Informe de instalación correcta, con el nombre de archivo exe del instalador con hash.</span><span class="sxs-lookup"><span data-stu-id="51e49-158">Install success report, with hashed installer exe filename.</span></span> |
| <span data-ttu-id="51e49-159">>=2.1.300</span><span class="sxs-lookup"><span data-stu-id="51e49-159">>=2.1.300</span></span>     | <span data-ttu-id="51e49-160">Versión de kernel.</span><span class="sxs-lookup"><span data-stu-id="51e49-160">Kernel version.</span></span> |
| <span data-ttu-id="51e49-161">>=2.1.300</span><span class="sxs-lookup"><span data-stu-id="51e49-161">>=2.1.300</span></span>     | <span data-ttu-id="51e49-162">Versión/versión de libc.</span><span class="sxs-lookup"><span data-stu-id="51e49-162">Libc release/version.</span></span> |
| <span data-ttu-id="51e49-163">>=3.0.100</span><span class="sxs-lookup"><span data-stu-id="51e49-163">>=3.0.100</span></span>     | <span data-ttu-id="51e49-164">Indica si la salida se redirigió (true o false).</span><span class="sxs-lookup"><span data-stu-id="51e49-164">Whether the output was redirected (true or false).</span></span> |
| <span data-ttu-id="51e49-165">>=3.0.100</span><span class="sxs-lookup"><span data-stu-id="51e49-165">>=3.0.100</span></span>     | <span data-ttu-id="51e49-166">En un bloqueo de CLI/SDK, el tipo de excepción y su seguimiento de pila (solo el código de CLI/SDK se incluye en el seguimiento de la pila enviado).</span><span class="sxs-lookup"><span data-stu-id="51e49-166">On a CLI/SDK crash, the exception type and its stack trace (only CLI/SDK code is included in the stack trace sent).</span></span> <span data-ttu-id="51e49-167">Para más información, vea [Telemetría de la excepción de bloqueo de SDK/CLI de .NET Core recopilada](#net-core-clisdk-crash-exception-telemetry-collected).</span><span class="sxs-lookup"><span data-stu-id="51e49-167">For more information, see [.NET Core CLI/SDK crash exception telemetry collected](#net-core-clisdk-crash-exception-telemetry-collected).</span></span> |

### <a name="collected-options"></a><span data-ttu-id="51e49-168">Opciones recopiladas</span><span class="sxs-lookup"><span data-stu-id="51e49-168">Collected options</span></span>

<span data-ttu-id="51e49-169">Determinados comandos envían datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="51e49-169">Certain commands send additional data.</span></span> <span data-ttu-id="51e49-170">Un subconjunto de comandos envía el primer argumento:</span><span class="sxs-lookup"><span data-stu-id="51e49-170">A subset of commands sends the first argument:</span></span>

| <span data-ttu-id="51e49-171">Comando</span><span class="sxs-lookup"><span data-stu-id="51e49-171">Command</span></span>               | <span data-ttu-id="51e49-172">Datos del primer argumento enviados</span><span class="sxs-lookup"><span data-stu-id="51e49-172">First argument data sent</span></span>                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | <span data-ttu-id="51e49-173">Se está consultando la ayuda del comando.</span><span class="sxs-lookup"><span data-stu-id="51e49-173">The command help is being queried for.</span></span>  |
| `dotnet new <arg>`    | <span data-ttu-id="51e49-174">Nombre de la plantilla (con hash).</span><span class="sxs-lookup"><span data-stu-id="51e49-174">The template name (hashed).</span></span>             |
| `dotnet add <arg>`    | <span data-ttu-id="51e49-175">La palabra `package` o `reference`.</span><span class="sxs-lookup"><span data-stu-id="51e49-175">The word `package` or `reference`.</span></span>      |
| `dotnet remove <arg>` | <span data-ttu-id="51e49-176">La palabra `package` o `reference`.</span><span class="sxs-lookup"><span data-stu-id="51e49-176">The word `package` or `reference`.</span></span>      |
| `dotnet list <arg>`   | <span data-ttu-id="51e49-177">La palabra `package` o `reference`.</span><span class="sxs-lookup"><span data-stu-id="51e49-177">The word `package` or `reference`.</span></span>      |
| `dotnet sln <arg>`    | <span data-ttu-id="51e49-178">La palabra `add`, `list` o `remove`.</span><span class="sxs-lookup"><span data-stu-id="51e49-178">The word `add`, `list`, or `remove`.</span></span>    |
| `dotnet nuget <arg>`  | <span data-ttu-id="51e49-179">La palabra `delete`, `locals` o `push`.</span><span class="sxs-lookup"><span data-stu-id="51e49-179">The word `delete`, `locals`, or `push`.</span></span> |

<span data-ttu-id="51e49-180">Un subconjunto de comandos envía las opciones seleccionadas, si se usan, junto con sus valores:</span><span class="sxs-lookup"><span data-stu-id="51e49-180">A subset of commands sends selected options if they're used, along with their values:</span></span>

| <span data-ttu-id="51e49-181">Opción</span><span class="sxs-lookup"><span data-stu-id="51e49-181">Option</span></span>                  | <span data-ttu-id="51e49-182">Comandos</span><span class="sxs-lookup"><span data-stu-id="51e49-182">Commands</span></span>                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | <span data-ttu-id="51e49-183">Todos los comandos</span><span class="sxs-lookup"><span data-stu-id="51e49-183">All commands</span></span>                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | <span data-ttu-id="51e49-184">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span><span class="sxs-lookup"><span data-stu-id="51e49-184">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span></span>                  |
| `--framework`           | <span data-ttu-id="51e49-185">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span><span class="sxs-lookup"><span data-stu-id="51e49-185">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span></span> |
| `--runtime`             | <span data-ttu-id="51e49-186">`dotnet build`,  `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="51e49-186">`dotnet build`,  `dotnet publish`</span></span>                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

<span data-ttu-id="51e49-187">A excepción de `--verbosity` y `--sdk-package-version`, se aplica un algoritmo hash a los demás valores a partir del SDK de .NET Core 2.1.100.</span><span class="sxs-lookup"><span data-stu-id="51e49-187">Except for `--verbosity` and `--sdk-package-version`, all the other values are hashed starting with .NET Core 2.1.100 SDK.</span></span>

## <a name="net-core-clisdk-crash-exception-telemetry-collected"></a><span data-ttu-id="51e49-188">Telemetría de la excepción de bloqueo de SDK/CLI de .NET Core recopilada</span><span class="sxs-lookup"><span data-stu-id="51e49-188">.NET Core CLI/SDK crash exception telemetry collected</span></span>

<span data-ttu-id="51e49-189">Si el SDK/CLI de .NET Core se bloquea, se recopila el nombre de la excepción y el seguimiento de la pila del código de CLI/SDK.</span><span class="sxs-lookup"><span data-stu-id="51e49-189">If the .NET Core CLI/SDK crashes, it collects the name of the exception and stack trace of the CLI/SDK code.</span></span> <span data-ttu-id="51e49-190">Esta información se recopila para evaluar los problemas y mejorar la calidad del SDK de .NET Core y la CLI.</span><span class="sxs-lookup"><span data-stu-id="51e49-190">This information is collected to assess problems and improve the quality of the .NET Core SDK and CLI.</span></span> <span data-ttu-id="51e49-191">En este artículo se proporciona información sobre los datos que se recopilan.</span><span class="sxs-lookup"><span data-stu-id="51e49-191">This article provides information about the data we collect.</span></span> <span data-ttu-id="51e49-192">También se ofrecen sugerencias para que los usuarios que compilan su propia versión del SDK de .NET Core eviten la divulgación involuntaria de información personal o confidencial.</span><span class="sxs-lookup"><span data-stu-id="51e49-192">It also provides tips on how users building their own version of the .NET Core SDK can avoid inadvertent disclosure of personal or sensitive information.</span></span>

### <a name="types-of-collected-data"></a><span data-ttu-id="51e49-193">Tipos de datos recopilados</span><span class="sxs-lookup"><span data-stu-id="51e49-193">Types of collected data</span></span>

<span data-ttu-id="51e49-194">El CLI de .NET Core recopila información solo de las excepciones de CLI/SDK, pero no de las excepciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="51e49-194">.NET Core CLI collects information for CLI/SDK exceptions only, not exceptions in your application.</span></span> <span data-ttu-id="51e49-195">Los datos recopilados contienen el nombre de la excepción y el seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="51e49-195">The collected data contains the name of the exception and the stack trace.</span></span> <span data-ttu-id="51e49-196">Este seguimiento de la pila es del código de CLI/SDK.</span><span class="sxs-lookup"><span data-stu-id="51e49-196">This stack trace is of CLI/SDK code.</span></span>

<span data-ttu-id="51e49-197">En este ejemplo se muestra el tipo de datos que se recopilan:</span><span class="sxs-lookup"><span data-stu-id="51e49-197">The following example shows the kind of data that is collected:</span></span>

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-of-information"></a><span data-ttu-id="51e49-198">Evasión de la divulgación involuntaria de información</span><span class="sxs-lookup"><span data-stu-id="51e49-198">Avoid inadvertent disclosure of information</span></span>

<span data-ttu-id="51e49-199">Los colaboradores de .NET Core y cualquier otro usuario que ejecute una versión del SDK de .NET Core compilada por ellos mismos deben tener en cuenta la ruta de acceso al código fuente del SDK.</span><span class="sxs-lookup"><span data-stu-id="51e49-199">.NET Core contributors and anyone else running a version of the .NET Core SDK that they built themselves should consider the path to their SDK source code.</span></span> <span data-ttu-id="51e49-200">Si se produce un bloqueo mientras se usa un SDK de .NET Core que es una compilación de depuración personalizada o está configurado con archivos de símbolos de compilación personalizados, la ruta de acceso del archivo de origen del SDK desde el equipo de compilación se recopila como parte del seguimiento de la pila y no tiene un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="51e49-200">If a crash occurs while using a .NET Core SDK that is a custom debug build or configured with custom build symbol files, the SDK source file path from the build machine is collected as part of the stack trace and isn't hashed.</span></span>

<span data-ttu-id="51e49-201">Por este motivo, las compilaciones personalizadas del SDK de .NET Core no deben almacenarse en directorios cuyos nombres de ruta de acceso expongan información personal o confidencial.</span><span class="sxs-lookup"><span data-stu-id="51e49-201">Because of this, custom builds of the .NET Core SDK shouldn't be located in directories whose path names expose personal or sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="51e49-202">Vea también</span><span class="sxs-lookup"><span data-stu-id="51e49-202">See also</span></span>

- [<span data-ttu-id="51e49-203">Telemetría de la CLI de .NET Core: datos del segundo trimestre de 2019</span><span class="sxs-lookup"><span data-stu-id="51e49-203">.NET Core CLI Telemetry - 2019 Q2 Data</span></span>](https://dotnet.microsoft.com/platform/telemetry/dotnet-core-cli-2019q2)
- [<span data-ttu-id="51e49-204">Fuente de referencia de telemetría (repositorio dotnet/cli)</span><span class="sxs-lookup"><span data-stu-id="51e49-204">Telemetry reference source (dotnet/cli repository)</span></span>](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
