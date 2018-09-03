---
title: Telemetría del SDK de .NET Core
description: Descubra las características de telemetría del SDK de .NET Core que recopilan información de uso para el análisis, qué datos se recopilan y cómo deshabilitarlas.
author: richlander
ms.author: mairaw
ms.date: 06/20/2018
ms.openlocfilehash: b60fc9d9d619334269343fd858a782cdfeb09ba4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43408415"
---
# <a name="net-core-sdk-telemetry"></a><span data-ttu-id="f46d5-103">Telemetría del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f46d5-103">.NET Core SDK telemetry</span></span>

<span data-ttu-id="f46d5-104">El [SDK de .NET Core](index.md) incluye una [característica de telemetría](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) que recopila información de uso.</span><span class="sxs-lookup"><span data-stu-id="f46d5-104">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry) that collects usage information.</span></span> <span data-ttu-id="f46d5-105">Es importante que el equipo de .NET entienda cómo se usan las herramientas a fin de que se puedan mejorar.</span><span class="sxs-lookup"><span data-stu-id="f46d5-105">It's important that the .NET Team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="f46d5-106">Para obtener más información, consulte [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/) (Lo que hemos aprendido de la telemetría del SDK de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="f46d5-106">For more information, see [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="f46d5-107">Los datos recopilados son anónimos y se publican de forma agregada para que los usen Microsoft y la comunidad según la [licencia de atribución de Creative Commons](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="f46d5-107">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="f46d5-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f46d5-108">Scope</span></span>

<span data-ttu-id="f46d5-109">El comando `dotnet` se usa para iniciar ambas aplicaciones y la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f46d5-109">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="f46d5-110">El comando `dotnet` no recopila la telemetría por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f46d5-110">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="f46d5-111">Los comandos de la CLI de .NET Core que se ejecutan mediante el comando `dotnet` son los que recopilan la telemetría.</span><span class="sxs-lookup"><span data-stu-id="f46d5-111">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="f46d5-112">La telemetría *no está habilitada* cuando se usa el comando `dotnet` por sí mismo, sin ningún comando asociado:</span><span class="sxs-lookup"><span data-stu-id="f46d5-112">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="f46d5-113">La telemetría *está habilitada* cuando se usan los [comandos de la CLI de .NET Core](index.md), como:</span><span class="sxs-lookup"><span data-stu-id="f46d5-113">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="f46d5-114">Cómo desactivar la característica</span><span class="sxs-lookup"><span data-stu-id="f46d5-114">How to opt out</span></span>

<span data-ttu-id="f46d5-115">La característica de telemetría del SDK de .NET Core está habilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f46d5-115">The .NET Core SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="f46d5-116">Puede desactivar la característica de telemetría si establece la variable de entorno `DOTNET_CLI_TELEMETRY_OPTOUT` en `1` o `true`.</span><span class="sxs-lookup"><span data-stu-id="f46d5-116">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="f46d5-117">Puntos de datos</span><span class="sxs-lookup"><span data-stu-id="f46d5-117">Data points</span></span>

<span data-ttu-id="f46d5-118">La característica recopila los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="f46d5-118">The feature collects the following data:</span></span>

- <span data-ttu-id="f46d5-119">Marca de tiempo de la invocación&#8224;</span><span class="sxs-lookup"><span data-stu-id="f46d5-119">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="f46d5-120">Comando invocado (por ejemplo, “build”)&#8224;</span><span class="sxs-lookup"><span data-stu-id="f46d5-120">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="f46d5-121">Dirección IP de tres octetos usada para determinar la ubicación geográfica&#8224;</span><span class="sxs-lookup"><span data-stu-id="f46d5-121">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="f46d5-122">`ExitCode` del comando</span><span class="sxs-lookup"><span data-stu-id="f46d5-122">`ExitCode` of the command</span></span>
- <span data-ttu-id="f46d5-123">Ejecutor de pruebas (para los proyectos de prueba)</span><span class="sxs-lookup"><span data-stu-id="f46d5-123">Test runner (for test projects)</span></span>
- <span data-ttu-id="f46d5-124">Sistema operativo y versión&#8224;</span><span class="sxs-lookup"><span data-stu-id="f46d5-124">Operating system and version&#8224;</span></span>
- <span data-ttu-id="f46d5-125">Si los id. de tiempo de ejecución están presentes en el nodo “runtimes”</span><span class="sxs-lookup"><span data-stu-id="f46d5-125">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="f46d5-126">Versión del SDK de .NET Core&#8224;</span><span class="sxs-lookup"><span data-stu-id="f46d5-126">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="f46d5-127">&#8224;Esta métrica está publicada.</span><span class="sxs-lookup"><span data-stu-id="f46d5-127">&#8224;This metric is published.</span></span>

<span data-ttu-id="f46d5-128">A partir del SDK de .NET Core 2.0, se recopilan nuevos puntos de datos:</span><span class="sxs-lookup"><span data-stu-id="f46d5-128">Starting with .NET Core SDK 2.0, new data points are collected:</span></span>

- <span data-ttu-id="f46d5-129">Opciones y argumentos del comando `dotnet`: solo se recopilan opciones y argumentos conocidos (no cadenas arbitrarias).</span><span class="sxs-lookup"><span data-stu-id="f46d5-129">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="f46d5-130">Si el SDK se ejecuta en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="f46d5-130">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="f46d5-131">Marcos de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="f46d5-131">Target frameworks.</span></span>
- <span data-ttu-id="f46d5-132">Dirección MAC con hash: un id. único y anónimo criptográficamente (SHA256) para una máquina.</span><span class="sxs-lookup"><span data-stu-id="f46d5-132">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="f46d5-133">Esta métrica no está publicada.</span><span class="sxs-lookup"><span data-stu-id="f46d5-133">This metric isn't published.</span></span>
- <span data-ttu-id="f46d5-134">Directorio de trabajo actual con hash.</span><span class="sxs-lookup"><span data-stu-id="f46d5-134">Hashed current working directory.</span></span>

<span data-ttu-id="f46d5-135">La característica no recopila datos personales, como direcciones de correo electrónico o nombres de usuario.</span><span class="sxs-lookup"><span data-stu-id="f46d5-135">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="f46d5-136">No examina el código ni extrae datos a nivel de proyecto confidenciales, como el nombre, el repositorio o el autor.</span><span class="sxs-lookup"><span data-stu-id="f46d5-136">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="f46d5-137">Los datos se envían de forma segura a los servidores de Microsoft con tecnología de [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/), se conservan bajo acceso restringido y se publican bajo controles de seguridad estrictos de sistemas seguros de [Azure Storage](https://azure.microsoft.com/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="f46d5-137">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="f46d5-138">El equipo de .NET quiere saber cómo se usan las herramientas y si funcionan correctamente, no qué va a compilar con las herramientas.</span><span class="sxs-lookup"><span data-stu-id="f46d5-138">The .NET team wants to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="f46d5-139">Si sospecha que la telemetría recopila datos confidenciales o que los datos se están tratando de forma insegura o inapropiada, [informe de un problema en los problemas del repositorio de dotnet/cli](https://github.com/dotnet/cli/issues) para que lo investiguemos.</span><span class="sxs-lookup"><span data-stu-id="f46d5-139">If you suspect that the telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [dotnet/cli](https://github.com/dotnet/cli/issues) repository for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="f46d5-140">Datos publicados</span><span class="sxs-lookup"><span data-stu-id="f46d5-140">Published data</span></span>

<span data-ttu-id="f46d5-141">Los datos publicados están disponibles cada trimestre y se muestran en [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md) (Datos de uso del SDK de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="f46d5-141">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="f46d5-142">Las columnas de un archivo de datos son:</span><span class="sxs-lookup"><span data-stu-id="f46d5-142">The columns of a data file are:</span></span>

- <span data-ttu-id="f46d5-143">Marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="f46d5-143">Timestamp</span></span>
- <span data-ttu-id="f46d5-144">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="f46d5-144">Occurrences&#8224;</span></span>
- <span data-ttu-id="f46d5-145">Comando</span><span class="sxs-lookup"><span data-stu-id="f46d5-145">Command</span></span>
- <span data-ttu-id="f46d5-146">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="f46d5-146">Geography&#8225;</span></span>
- <span data-ttu-id="f46d5-147">OSFamily</span><span class="sxs-lookup"><span data-stu-id="f46d5-147">OSFamily</span></span>
- <span data-ttu-id="f46d5-148">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="f46d5-148">RuntimeID</span></span>
- <span data-ttu-id="f46d5-149">OSVersion</span><span class="sxs-lookup"><span data-stu-id="f46d5-149">OSVersion</span></span>
- <span data-ttu-id="f46d5-150">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="f46d5-150">SDKVersion</span></span>

<span data-ttu-id="f46d5-151">&#8224;En la columna *Ocurrences* se muestra el número agregado de usos de ese comando para las métricas de esa fila durante ese día.</span><span class="sxs-lookup"><span data-stu-id="f46d5-151">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span>

<span data-ttu-id="f46d5-152">&#8225;Normalmente, en la columna *Geography* se muestra el nombre de un país.</span><span class="sxs-lookup"><span data-stu-id="f46d5-152">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="f46d5-153">En algunos casos, el continente de Antártida aparece en esta columna, ya sea debido a los investigadores que usan .NET Core en la Antártida o a datos de ubicación incorrectos.</span><span class="sxs-lookup"><span data-stu-id="f46d5-153">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="f46d5-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f46d5-154">Example</span></span>

| <span data-ttu-id="f46d5-155">Marca de tiempo</span><span class="sxs-lookup"><span data-stu-id="f46d5-155">Timestamp</span></span>      | <span data-ttu-id="f46d5-156">Occurrences</span><span class="sxs-lookup"><span data-stu-id="f46d5-156">Occurrences</span></span> | <span data-ttu-id="f46d5-157">Comando</span><span class="sxs-lookup"><span data-stu-id="f46d5-157">Command</span></span> | <span data-ttu-id="f46d5-158">Geography</span><span class="sxs-lookup"><span data-stu-id="f46d5-158">Geography</span></span> | <span data-ttu-id="f46d5-159">OSFamily</span><span class="sxs-lookup"><span data-stu-id="f46d5-159">OSFamily</span></span> | <span data-ttu-id="f46d5-160">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="f46d5-160">RuntimeID</span></span>     | <span data-ttu-id="f46d5-161">OSVersion</span><span class="sxs-lookup"><span data-stu-id="f46d5-161">OSVersion</span></span> | <span data-ttu-id="f46d5-162">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="f46d5-162">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="f46d5-163">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="f46d5-163">4/16/2017 0:00</span></span> | <span data-ttu-id="f46d5-164">8</span><span class="sxs-lookup"><span data-stu-id="f46d5-164">8</span></span>           | <span data-ttu-id="f46d5-165">ejecutar</span><span class="sxs-lookup"><span data-stu-id="f46d5-165">run</span></span>     | <span data-ttu-id="f46d5-166">Uganda</span><span class="sxs-lookup"><span data-stu-id="f46d5-166">Uganda</span></span>    | <span data-ttu-id="f46d5-167">Darwin</span><span class="sxs-lookup"><span data-stu-id="f46d5-167">Darwin</span></span>   | <span data-ttu-id="f46d5-168">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="f46d5-168">osx.10.12-x64</span></span> | <span data-ttu-id="f46d5-169">10.12</span><span class="sxs-lookup"><span data-stu-id="f46d5-169">10.12</span></span>     | <span data-ttu-id="f46d5-170">1.0.1</span><span class="sxs-lookup"><span data-stu-id="f46d5-170">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="f46d5-171">Conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="f46d5-171">Datasets</span></span>

[<span data-ttu-id="f46d5-172">2016: tercer trimestre</span><span class="sxs-lookup"><span data-stu-id="f46d5-172">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[<span data-ttu-id="f46d5-173">2016: cuarto trimestre</span><span class="sxs-lookup"><span data-stu-id="f46d5-173">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[<span data-ttu-id="f46d5-174">2017: primer trimestre</span><span class="sxs-lookup"><span data-stu-id="f46d5-174">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[<span data-ttu-id="f46d5-175">2017: segundo trimestre</span><span class="sxs-lookup"><span data-stu-id="f46d5-175">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)  
[<span data-ttu-id="f46d5-176">2017: tercer trimestre</span><span class="sxs-lookup"><span data-stu-id="f46d5-176">2017 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q3.tsv)  
[<span data-ttu-id="f46d5-177">2017: cuarto trimestre</span><span class="sxs-lookup"><span data-stu-id="f46d5-177">2017 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q4.tsv)  

<span data-ttu-id="f46d5-178">Hay conjuntos de datos adicionales publicados con un formato de URL estándar.</span><span class="sxs-lookup"><span data-stu-id="f46d5-178">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="f46d5-179">Reemplace `<YEAR>` con el año y `<QUARTER>` con el trimestre del año (use `1`, `2`, `3` o `4`).</span><span class="sxs-lookup"><span data-stu-id="f46d5-179">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="f46d5-180">Los archivos están en formato de valores separados por tabulaciones (*TSV*).</span><span class="sxs-lookup"><span data-stu-id="f46d5-180">The files are in tab-separated values (*TSV*) format.</span></span>

`https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv`

## <a name="license"></a><span data-ttu-id="f46d5-181">Licencia</span><span class="sxs-lookup"><span data-stu-id="f46d5-181">License</span></span>

<span data-ttu-id="f46d5-182">La distribución de Microsoft de .NET Core cuenta con licencia en virtud del [CLUF DE LA BIBLIOTECA DE MICROSOFT .NET](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="f46d5-182">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="f46d5-183">Esta licencia incluye la sección “DATOS” para habilitar la telemetría (se muestra a continuación).</span><span class="sxs-lookup"><span data-stu-id="f46d5-183">This license includes the "DATA" section to enable telemetry (shown below).</span></span>

<span data-ttu-id="f46d5-184">Los [paquetes NuGet de .NET](https://www.nuget.org/profiles/dotnetframework) usan la misma licencia, pero no permiten la telemetría (consulte [Ámbito](#scope)).</span><span class="sxs-lookup"><span data-stu-id="f46d5-184">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

> 2. <span data-ttu-id="f46d5-185">DATOS.</span><span class="sxs-lookup"><span data-stu-id="f46d5-185">DATA.</span></span> <span data-ttu-id="f46d5-186">El software puede recopilar información sobre el usuario y la utilización del software y, después, enviarla a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f46d5-186">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="f46d5-187">Microsoft puede usarla para mejorar nuestros productos y servicios.</span><span class="sxs-lookup"><span data-stu-id="f46d5-187">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="f46d5-188">Puede obtener más información sobre la recopilación y el uso de datos en la documentación de ayuda y la declaración de privacidad en http://go.microsoft.com/fwlink/?LinkId=528096.</span><span class="sxs-lookup"><span data-stu-id="f46d5-188">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="f46d5-189">Al usar el software, se entiende que da su consentimiento para la realización de estas prácticas.</span><span class="sxs-lookup"><span data-stu-id="f46d5-189">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="f46d5-190">Divulgación</span><span class="sxs-lookup"><span data-stu-id="f46d5-190">Disclosure</span></span>

<span data-ttu-id="f46d5-191">El SDK de .NET Core muestra el texto siguiente cuando ejecuta por primera vez uno de los comandos de la [CLI de .NET Core](index.md) (por ejemplo, `dotnet restore`).</span><span class="sxs-lookup"><span data-stu-id="f46d5-191">The .NET Core SDK displays the following text when you first run one of the [.NET Core CLI commands](index.md) (for example, `dotnet restore`).</span></span> <span data-ttu-id="f46d5-192">El texto puede variar ligeramente según la versión del SDK que ejecute.</span><span class="sxs-lookup"><span data-stu-id="f46d5-192">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="f46d5-193">Esta experiencia de "primera vista" es la forma en que Microsoft le notifica sobre la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="f46d5-193">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core: https://aka.ms/dotnet-docs
Use 'dotnet --help' to see available commands or visit: https://aka.ms/dotnet-cli-docs

Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience.
The data is anonymous and doesn't include command-line arguments.
The data is collected by Microsoft and shared with the community.
You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="see-also"></a><span data-ttu-id="f46d5-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="f46d5-194">See also</span></span>

- <span data-ttu-id="f46d5-195">[What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/) (Lo que hemos aprendido de la telemetría del SDK de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="f46d5-195">[What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)</span></span>
- <span data-ttu-id="f46d5-196">[Telemetry reference source (dotnet/cli repo)](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)(Origen de referencia de telemetría)</span><span class="sxs-lookup"><span data-stu-id="f46d5-196">[Telemetry reference source (dotnet/cli repo)](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)</span></span>
- <span data-ttu-id="f46d5-197">[.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md) (Datos de uso del SDK de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="f46d5-197">[.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)</span></span>
