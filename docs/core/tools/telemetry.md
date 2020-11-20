---
title: Telemetría del SDK de .NET
description: Descubra las características de telemetría del SDK de .NET que recopilan información de uso para el análisis, qué datos se recopilan y cómo deshabilitarlos.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: 4f137822c61e1a04eccd28ebd0cd56c04f4a85e2
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633875"
---
# <a name="net-sdk-telemetry"></a><span data-ttu-id="d6dee-103">Telemetría del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="d6dee-103">.NET SDK telemetry</span></span>

<span data-ttu-id="d6dee-104">El [SDK de .NET](index.md) incluye una característica de telemetría que recopila datos de uso e información de excepciones cuando se bloquea la CLI de .NET.</span><span class="sxs-lookup"><span data-stu-id="d6dee-104">The [.NET SDK](index.md) includes a telemetry feature that collects usage data and exception information when the .NET CLI crashes.</span></span> <span data-ttu-id="d6dee-105">La CLI de .NET se incluye en el SDK de .NET y es el conjunto de verbos que permiten compilar, probar y publicar las aplicaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="d6dee-105">The .NET CLI comes with the .NET SDK and is the set of verbs that enable you to build, test, and publish your .NET apps.</span></span> <span data-ttu-id="d6dee-106">Es importante que el equipo de .NET entienda cómo se usan las herramientas con el fin de mejorarlas.</span><span class="sxs-lookup"><span data-stu-id="d6dee-106">It's important that the .NET team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="d6dee-107">Con la información sobre los errores, el equipo consigue resolver problemas y corregir errores.</span><span class="sxs-lookup"><span data-stu-id="d6dee-107">Information on failures helps the team resolve problems and fix bugs.</span></span>

<span data-ttu-id="d6dee-108">Los datos recopilados se publican de forma agregada bajo la [licencia de atribución de Creative Commons](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="d6dee-108">The collected data is published in aggregate under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="d6dee-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d6dee-109">Scope</span></span>

<span data-ttu-id="d6dee-110">`dotnet` tiene dos funciones: ejecutar aplicaciones y ejecutar comandos de la CLI.</span><span class="sxs-lookup"><span data-stu-id="d6dee-110">`dotnet` has two functions: to run apps, and to execute CLI commands.</span></span> <span data-ttu-id="d6dee-111">La telemetría *no se recopila* cuando se usa `dotnet` para iniciar una aplicación con el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="d6dee-111">Telemetry *isn't collected* when using `dotnet` to start an application in the following format:</span></span>

- `dotnet [path-to-app].dll`

<span data-ttu-id="d6dee-112">La telemetría *se recopila* cuando se usa cualquiera de los [comandos de la CLI de .NET](index.md), como:</span><span class="sxs-lookup"><span data-stu-id="d6dee-112">Telemetry *is collected* when using any of the [.NET CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="d6dee-113">Cómo desactivar la característica</span><span class="sxs-lookup"><span data-stu-id="d6dee-113">How to opt out</span></span>

<span data-ttu-id="d6dee-114">La característica de telemetría del SDK de .NET está habilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d6dee-114">The .NET SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="d6dee-115">Para desactivar la característica de telemetría, establezca la variable de entorno `DOTNET_CLI_TELEMETRY_OPTOUT` en `1` o `true`.</span><span class="sxs-lookup"><span data-stu-id="d6dee-115">To opt out of the telemetry feature, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

<span data-ttu-id="d6dee-116">El instalador del SDK de .NET también envía una única entrada de telemetría cuando se produce una instalación correcta.</span><span class="sxs-lookup"><span data-stu-id="d6dee-116">A single telemetry entry is also sent by the .NET SDK installer when a successful installation happens.</span></span> <span data-ttu-id="d6dee-117">Para no participar, establezca la variable de entorno `DOTNET_CLI_TELEMETRY_OPTOUT` antes de instalar el SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="d6dee-117">To opt out, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable before you install the .NET SDK.</span></span>

## <a name="disclosure"></a><span data-ttu-id="d6dee-118">Divulgación</span><span class="sxs-lookup"><span data-stu-id="d6dee-118">Disclosure</span></span>

<span data-ttu-id="d6dee-119">El SDK de .NET muestra texto similar al siguiente cuando se ejecuta por primera vez uno de los [comandos de la CLI de .NET](index.md) (por ejemplo, `dotnet build`).</span><span class="sxs-lookup"><span data-stu-id="d6dee-119">The .NET SDK displays text similar to the following when you first run one of the [.NET CLI commands](index.md) (for example, `dotnet build`).</span></span> <span data-ttu-id="d6dee-120">El texto puede variar ligeramente según la versión del SDK que ejecute.</span><span class="sxs-lookup"><span data-stu-id="d6dee-120">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="d6dee-121">Esta experiencia de "primera vista" es la forma en que Microsoft le notifica sobre la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="d6dee-121">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Telemetry
---------
The .NET tools collect usage data in order to help us improve your experience. The data is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

<span data-ttu-id="d6dee-122">Para deshabilitar este mensaje y el de bienvenida de .NET, establezca la variable de entorno `DOTNET_NOLOGO` en `true`.</span><span class="sxs-lookup"><span data-stu-id="d6dee-122">To disable this message and the .NET welcome message, set the `DOTNET_NOLOGO` environment variable to `true`.</span></span> <span data-ttu-id="d6dee-123">Tenga en cuenta que esta variable no tiene ningún efecto sobre la exclusión de la telemetría.</span><span class="sxs-lookup"><span data-stu-id="d6dee-123">Note that this variable has no effect on telemetry opt out.</span></span>

## <a name="data-points"></a><span data-ttu-id="d6dee-124">Puntos de datos</span><span class="sxs-lookup"><span data-stu-id="d6dee-124">Data points</span></span>

<span data-ttu-id="d6dee-125">La característica de telemetría no recopila datos personales, como direcciones de correo electrónico o nombres de usuario.</span><span class="sxs-lookup"><span data-stu-id="d6dee-125">The telemetry feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="d6dee-126">No examina el código ni extrae datos de nivel de proyecto, como el nombre, el repositorio o el autor.</span><span class="sxs-lookup"><span data-stu-id="d6dee-126">It doesn't scan your code and doesn't extract project-level data, such as name, repository, or author.</span></span> <span data-ttu-id="d6dee-127">Los datos se envían de forma segura a los servidores de Microsoft con tecnología de [Azure Monitor](https://azure.microsoft.com/services/monitor/), se conservan bajo acceso restringido y se publican bajo controles de seguridad estrictos de sistemas seguros de [Azure Storage](https://azure.microsoft.com/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="d6dee-127">The data is sent securely to Microsoft servers using [Azure Monitor](https://azure.microsoft.com/services/monitor/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="d6dee-128">La protección de su privacidad es importante para nosotros.</span><span class="sxs-lookup"><span data-stu-id="d6dee-128">Protecting your privacy is important to us.</span></span> <span data-ttu-id="d6dee-129">Si sospecha que la telemetría está recopilando datos confidenciales o que los datos se están tratando de forma no segura o inapropiada, informe de un problema en el repositorio de [dotnet/cli](https://github.com/dotnet/sdk/issues) o envíenos un correo electrónico a [dotnet@microsoft.com](mailto:dotnet@microsoft.com) para que lo investiguemos.</span><span class="sxs-lookup"><span data-stu-id="d6dee-129">If you suspect the telemetry is collecting sensitive data or the data is being insecurely or inappropriately handled, file an issue in the [dotnet/sdk](https://github.com/dotnet/sdk/issues) repository or send an email to [dotnet@microsoft.com](mailto:dotnet@microsoft.com) for investigation.</span></span>

<span data-ttu-id="d6dee-130">La característica de telemetría recopila los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="d6dee-130">The telemetry feature collects the following data:</span></span>

| <span data-ttu-id="d6dee-131">Versiones del SDK</span><span class="sxs-lookup"><span data-stu-id="d6dee-131">SDK versions</span></span> | <span data-ttu-id="d6dee-132">Datos</span><span class="sxs-lookup"><span data-stu-id="d6dee-132">Data</span></span> |
|--------------|------|
| <span data-ttu-id="d6dee-133">Todas</span><span class="sxs-lookup"><span data-stu-id="d6dee-133">All</span></span>          | <span data-ttu-id="d6dee-134">Marca de tiempo de la invocación.</span><span class="sxs-lookup"><span data-stu-id="d6dee-134">Timestamp of invocation.</span></span> |
| <span data-ttu-id="d6dee-135">Todas</span><span class="sxs-lookup"><span data-stu-id="d6dee-135">All</span></span>          | <span data-ttu-id="d6dee-136">Comando invocado (por ejemplo, "build"), con hash a partir de 2.1.</span><span class="sxs-lookup"><span data-stu-id="d6dee-136">Command invoked (for example, "build"), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="d6dee-137">Todas</span><span class="sxs-lookup"><span data-stu-id="d6dee-137">All</span></span>          | <span data-ttu-id="d6dee-138">Dirección IP de tres octetos usada para determinar la ubicación geográfica.</span><span class="sxs-lookup"><span data-stu-id="d6dee-138">Three octet IP address used to determine the geographical location.</span></span> |
| <span data-ttu-id="d6dee-139">Todas</span><span class="sxs-lookup"><span data-stu-id="d6dee-139">All</span></span>          | <span data-ttu-id="d6dee-140">Sistema operativo y versión.</span><span class="sxs-lookup"><span data-stu-id="d6dee-140">Operating system and version.</span></span> |
| <span data-ttu-id="d6dee-141">Todas</span><span class="sxs-lookup"><span data-stu-id="d6dee-141">All</span></span>          | <span data-ttu-id="d6dee-142">Identificador de tiempo de ejecución (RID) en el que se ejecuta el SDK.</span><span class="sxs-lookup"><span data-stu-id="d6dee-142">Runtime ID (RID) the SDK is running on.</span></span> |
| <span data-ttu-id="d6dee-143">Todas</span><span class="sxs-lookup"><span data-stu-id="d6dee-143">All</span></span>          | <span data-ttu-id="d6dee-144">Versión del SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="d6dee-144">.NET SDK version.</span></span> |
| <span data-ttu-id="d6dee-145">Todas</span><span class="sxs-lookup"><span data-stu-id="d6dee-145">All</span></span>          | <span data-ttu-id="d6dee-146">Perfil de telemetría: valor opcional usado internamente en Microsoft y que solo se usa con la participación explícita del usuario.</span><span class="sxs-lookup"><span data-stu-id="d6dee-146">Telemetry profile: an optional value only used with explicit user opt-in and used internally at Microsoft.</span></span> |
| <span data-ttu-id="d6dee-147">>=2.0</span><span class="sxs-lookup"><span data-stu-id="d6dee-147">>=2.0</span></span>        | <span data-ttu-id="d6dee-148">Opciones y argumentos del comando: se recopilan varias opciones y argumentos (no cadenas arbitrarias).</span><span class="sxs-lookup"><span data-stu-id="d6dee-148">Command arguments and options: several arguments and options are collected (not arbitrary strings).</span></span> <span data-ttu-id="d6dee-149">Vea [opciones recopiladas](#collected-options).</span><span class="sxs-lookup"><span data-stu-id="d6dee-149">See [collected options](#collected-options).</span></span> <span data-ttu-id="d6dee-150">Con hash a partir de la versión 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="d6dee-150">Hashed after 2.1.300.</span></span> |
| <span data-ttu-id="d6dee-151">>=2.0</span><span class="sxs-lookup"><span data-stu-id="d6dee-151">>=2.0</span></span>         | <span data-ttu-id="d6dee-152">Si el SDK se ejecuta en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="d6dee-152">Whether the SDK is running in a container.</span></span> |
| <span data-ttu-id="d6dee-153">>=2.0</span><span class="sxs-lookup"><span data-stu-id="d6dee-153">>=2.0</span></span>         | <span data-ttu-id="d6dee-154">Plataformas de destino (desde el evento `TargetFramework`), con hash a partir de 2.1.</span><span class="sxs-lookup"><span data-stu-id="d6dee-154">Target frameworks (from the `TargetFramework` event), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="d6dee-155">>=2.0</span><span class="sxs-lookup"><span data-stu-id="d6dee-155">>=2.0</span></span>         | <span data-ttu-id="d6dee-156">Dirección de Media Access Control (MAC) con hash (SHA256).</span><span class="sxs-lookup"><span data-stu-id="d6dee-156">Hashed Media Access Control (MAC) address (SHA256).</span></span> |
| <span data-ttu-id="d6dee-157">>=2.0</span><span class="sxs-lookup"><span data-stu-id="d6dee-157">>=2.0</span></span>         | <span data-ttu-id="d6dee-158">Directorio de trabajo actual con hash.</span><span class="sxs-lookup"><span data-stu-id="d6dee-158">Hashed current working directory.</span></span> |
| <span data-ttu-id="d6dee-159">>=2.0</span><span class="sxs-lookup"><span data-stu-id="d6dee-159">>=2.0</span></span>         | <span data-ttu-id="d6dee-160">Informe de instalación correcta, con el nombre de archivo exe del instalador con hash.</span><span class="sxs-lookup"><span data-stu-id="d6dee-160">Install success report, with hashed installer exe filename.</span></span> |
| <span data-ttu-id="d6dee-161">>=2.1.300</span><span class="sxs-lookup"><span data-stu-id="d6dee-161">>=2.1.300</span></span>     | <span data-ttu-id="d6dee-162">Versión de kernel.</span><span class="sxs-lookup"><span data-stu-id="d6dee-162">Kernel version.</span></span> |
| <span data-ttu-id="d6dee-163">>=2.1.300</span><span class="sxs-lookup"><span data-stu-id="d6dee-163">>=2.1.300</span></span>     | <span data-ttu-id="d6dee-164">Versión/versión de libc.</span><span class="sxs-lookup"><span data-stu-id="d6dee-164">Libc release/version.</span></span> |
| <span data-ttu-id="d6dee-165">>=3.0.100</span><span class="sxs-lookup"><span data-stu-id="d6dee-165">>=3.0.100</span></span>     | <span data-ttu-id="d6dee-166">Indica si la salida se redirigió (true o false).</span><span class="sxs-lookup"><span data-stu-id="d6dee-166">Whether the output was redirected (true or false).</span></span> |
| <span data-ttu-id="d6dee-167">>=3.0.100</span><span class="sxs-lookup"><span data-stu-id="d6dee-167">>=3.0.100</span></span>     | <span data-ttu-id="d6dee-168">En un bloqueo de CLI/SDK, el tipo de excepción y su seguimiento de pila (solo el código de CLI/SDK se incluye en el seguimiento de la pila enviado).</span><span class="sxs-lookup"><span data-stu-id="d6dee-168">On a CLI/SDK crash, the exception type and its stack trace (only CLI/SDK code is included in the stack trace sent).</span></span> <span data-ttu-id="d6dee-169">Para obtener más información, vea [Telemetría de la excepción de bloqueo de SDK/CLI de .NET Core recopilada](#net-clisdk-crash-exception-telemetry-collected).</span><span class="sxs-lookup"><span data-stu-id="d6dee-169">For more information, see [.NET CLI/SDK crash exception telemetry collected](#net-clisdk-crash-exception-telemetry-collected).</span></span> |

### <a name="collected-options"></a><span data-ttu-id="d6dee-170">Opciones recopiladas</span><span class="sxs-lookup"><span data-stu-id="d6dee-170">Collected options</span></span>

<span data-ttu-id="d6dee-171">Determinados comandos envían datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="d6dee-171">Certain commands send additional data.</span></span> <span data-ttu-id="d6dee-172">Un subconjunto de comandos envía el primer argumento:</span><span class="sxs-lookup"><span data-stu-id="d6dee-172">A subset of commands sends the first argument:</span></span>

| <span data-ttu-id="d6dee-173">Comando</span><span class="sxs-lookup"><span data-stu-id="d6dee-173">Command</span></span>               | <span data-ttu-id="d6dee-174">Datos del primer argumento enviados</span><span class="sxs-lookup"><span data-stu-id="d6dee-174">First argument data sent</span></span>                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | <span data-ttu-id="d6dee-175">Se está consultando la ayuda del comando.</span><span class="sxs-lookup"><span data-stu-id="d6dee-175">The command help is being queried for.</span></span>  |
| `dotnet new <arg>`    | <span data-ttu-id="d6dee-176">Nombre de la plantilla (con hash).</span><span class="sxs-lookup"><span data-stu-id="d6dee-176">The template name (hashed).</span></span>             |
| `dotnet add <arg>`    | <span data-ttu-id="d6dee-177">La palabra `package` o `reference`.</span><span class="sxs-lookup"><span data-stu-id="d6dee-177">The word `package` or `reference`.</span></span>      |
| `dotnet remove <arg>` | <span data-ttu-id="d6dee-178">La palabra `package` o `reference`.</span><span class="sxs-lookup"><span data-stu-id="d6dee-178">The word `package` or `reference`.</span></span>      |
| `dotnet list <arg>`   | <span data-ttu-id="d6dee-179">La palabra `package` o `reference`.</span><span class="sxs-lookup"><span data-stu-id="d6dee-179">The word `package` or `reference`.</span></span>      |
| `dotnet sln <arg>`    | <span data-ttu-id="d6dee-180">La palabra `add`, `list` o `remove`.</span><span class="sxs-lookup"><span data-stu-id="d6dee-180">The word `add`, `list`, or `remove`.</span></span>    |
| `dotnet nuget <arg>`  | <span data-ttu-id="d6dee-181">La palabra `delete`, `locals` o `push`.</span><span class="sxs-lookup"><span data-stu-id="d6dee-181">The word `delete`, `locals`, or `push`.</span></span> |

<span data-ttu-id="d6dee-182">Un subconjunto de comandos envía las opciones seleccionadas, si se usan, junto con sus valores:</span><span class="sxs-lookup"><span data-stu-id="d6dee-182">A subset of commands sends selected options if they're used, along with their values:</span></span>

| <span data-ttu-id="d6dee-183">Opción</span><span class="sxs-lookup"><span data-stu-id="d6dee-183">Option</span></span>                  | <span data-ttu-id="d6dee-184">Comandos</span><span class="sxs-lookup"><span data-stu-id="d6dee-184">Commands</span></span>                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | <span data-ttu-id="d6dee-185">Todos los comandos</span><span class="sxs-lookup"><span data-stu-id="d6dee-185">All commands</span></span>                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | <span data-ttu-id="d6dee-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span><span class="sxs-lookup"><span data-stu-id="d6dee-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span></span>                  |
| `--framework`           | <span data-ttu-id="d6dee-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span><span class="sxs-lookup"><span data-stu-id="d6dee-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span></span> |
| `--runtime`             | <span data-ttu-id="d6dee-188">`dotnet build`,  `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="d6dee-188">`dotnet build`,  `dotnet publish`</span></span>                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

<span data-ttu-id="d6dee-189">A excepción de `--verbosity` y `--sdk-package-version`, se aplica un algoritmo hash a los demás valores a partir del SDK de .NET Core 2.1.100.</span><span class="sxs-lookup"><span data-stu-id="d6dee-189">Except for `--verbosity` and `--sdk-package-version`, all the other values are hashed starting with .NET Core 2.1.100 SDK.</span></span>

## <a name="net-clisdk-crash-exception-telemetry-collected"></a><span data-ttu-id="d6dee-190">Telemetría de la excepción de bloqueo de SDK/CLI de .NET Core recopilada</span><span class="sxs-lookup"><span data-stu-id="d6dee-190">.NET CLI/SDK crash exception telemetry collected</span></span>

<span data-ttu-id="d6dee-191">Si se bloquea el SDK o la CLI de .NET, se recopilan el nombre de la excepción y el seguimiento de la pila del código de la CLI o el SDK.</span><span class="sxs-lookup"><span data-stu-id="d6dee-191">If the .NET CLI/SDK crashes, it collects the name of the exception and stack trace of the CLI/SDK code.</span></span> <span data-ttu-id="d6dee-192">Esta información se recopila para evaluar los problemas y mejorar la calidad del SDK y la CLI de .NET.</span><span class="sxs-lookup"><span data-stu-id="d6dee-192">This information is collected to assess problems and improve the quality of the .NET SDK and CLI.</span></span> <span data-ttu-id="d6dee-193">En este artículo se proporciona información sobre los datos que se recopilan.</span><span class="sxs-lookup"><span data-stu-id="d6dee-193">This article provides information about the data we collect.</span></span> <span data-ttu-id="d6dee-194">También se ofrecen sugerencias para que los usuarios que compilan una versión propia del SDK de .NET eviten la divulgación involuntaria de información personal o confidencial.</span><span class="sxs-lookup"><span data-stu-id="d6dee-194">It also provides tips on how users building their own version of the .NET SDK can avoid inadvertent disclosure of personal or sensitive information.</span></span>

### <a name="types-of-collected-data"></a><span data-ttu-id="d6dee-195">Tipos de datos recopilados</span><span class="sxs-lookup"><span data-stu-id="d6dee-195">Types of collected data</span></span>

<span data-ttu-id="d6dee-196">La CLI de .NET solo recopila información de las excepciones de la CLI o el SDK, no de las excepciones de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d6dee-196">.NET CLI collects information for CLI/SDK exceptions only, not exceptions in your application.</span></span> <span data-ttu-id="d6dee-197">Los datos recopilados contienen el nombre de la excepción y el seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="d6dee-197">The collected data contains the name of the exception and the stack trace.</span></span> <span data-ttu-id="d6dee-198">Este seguimiento de la pila es del código de CLI/SDK.</span><span class="sxs-lookup"><span data-stu-id="d6dee-198">This stack trace is of CLI/SDK code.</span></span>

<span data-ttu-id="d6dee-199">En este ejemplo se muestra el tipo de datos que se recopilan:</span><span class="sxs-lookup"><span data-stu-id="d6dee-199">The following example shows the kind of data that is collected:</span></span>

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

### <a name="avoid-inadvertent-disclosure-of-information"></a><span data-ttu-id="d6dee-200">Evasión de la divulgación involuntaria de información</span><span class="sxs-lookup"><span data-stu-id="d6dee-200">Avoid inadvertent disclosure of information</span></span>

<span data-ttu-id="d6dee-201">Los colaboradores de .NET y cualquier otro usuario que ejecute una versión del SDK de .NET compilada por ellos mismos deben tener en cuenta la ruta de acceso al código fuente del SDK.</span><span class="sxs-lookup"><span data-stu-id="d6dee-201">.NET contributors and anyone else running a version of the .NET SDK that they built themselves should consider the path to their SDK source code.</span></span> <span data-ttu-id="d6dee-202">Si se produce un bloqueo mientras se usa un SDK de .NET que es una compilación de depuración personalizada o está configurado con archivos de símbolos de compilación personalizados, la ruta de acceso del archivo de origen del SDK desde el equipo de compilación se recopila como parte del seguimiento de la pila y no tiene un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d6dee-202">If a crash occurs while using a .NET SDK that is a custom debug build or configured with custom build symbol files, the SDK source file path from the build machine is collected as part of the stack trace and isn't hashed.</span></span>

<span data-ttu-id="d6dee-203">Por este motivo, las compilaciones personalizadas del SDK de .NET no se deben almacenar en directorios cuyos nombres de ruta de acceso expongan información personal o confidencial.</span><span class="sxs-lookup"><span data-stu-id="d6dee-203">Because of this, custom builds of the .NET SDK shouldn't be located in directories whose path names expose personal or sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6dee-204">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6dee-204">See also</span></span>

- [<span data-ttu-id="d6dee-205">Datos de telemetría de la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="d6dee-205">.NET CLI Telemetry Data</span></span>](https://dotnet.microsoft.com/platform/telemetry)
- [<span data-ttu-id="d6dee-206">Fuente de referencia de telemetría (repositorio dotnet/sdk)</span><span class="sxs-lookup"><span data-stu-id="d6dee-206">Telemetry reference source (dotnet/sdk repository)</span></span>](https://github.com/dotnet/sdk/tree/master/src/Cli/dotnet/Telemetry)
