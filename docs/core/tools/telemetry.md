---
title: "Telemetría de herramientas de la CLI de .NET Core"
description: "Descubra las características de telemetría de las herramientas de .NET Core que recopilan información de uso para el análisis, qué datos se recopilan y cómo deshabilitarlas."
keywords: ".NET,.NET Core,telemetría"
author: richlander
ms.author: mairaw
ms.date: 08/04/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.translationtype: HT
ms.sourcegitcommit: c58ed1b3c09f1e358d0b66f6cf7186821601fd69
ms.openlocfilehash: 8ea8ee44a58c6aabfd09afbc7ef53239a9029c57
ms.contentlocale: es-es
ms.lasthandoff: 08/12/2017

---

# <a name="net-core-cli-tools-telemetry"></a><span data-ttu-id="34fd6-104">Telemetría de herramientas de la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="34fd6-104">.NET Core CLI Tools telemetry</span></span>

<span data-ttu-id="34fd6-105">El [SDK de .NET Core](index.md) incluye una [característica de telemetría](https://github.com/dotnet/cli/pull/2145) que recopila información de uso.</span><span class="sxs-lookup"><span data-stu-id="34fd6-105">The [.NET Core SDK](index.md) includes a [telemetry feature](https://github.com/dotnet/cli/pull/2145) that collects usage information.</span></span> <span data-ttu-id="34fd6-106">Es importante que el equipo de .NET entienda cómo se usan las herramientas a fin de que podamos mejorarlas.</span><span class="sxs-lookup"><span data-stu-id="34fd6-106">It's important that the .NET Team understands how the tools are used so that we can improve them.</span></span> <span data-ttu-id="34fd6-107">Para obtener más información, consulte [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/) (Lo que hemos aprendido de la telemetría del SDK de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="34fd6-107">For more information, see [What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/).</span></span>

<span data-ttu-id="34fd6-108">Los datos recopilados son anónimos y se publican de forma agregada para que los usen Microsoft y la comunidad según la [licencia de atribución de Creative Commons](https://creativecommons.org/licenses/by/4.0/).</span><span class="sxs-lookup"><span data-stu-id="34fd6-108">The collected data is anonymous and published in an aggregated form for use by both Microsoft and the community under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span> 

## <a name="scope"></a><span data-ttu-id="34fd6-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="34fd6-109">Scope</span></span>

<span data-ttu-id="34fd6-110">El comando `dotnet` se usa para iniciar ambas aplicaciones y la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="34fd6-110">The `dotnet` command is used to launch both apps and the .NET Core CLI.</span></span> <span data-ttu-id="34fd6-111">El comando `dotnet` no recopila la telemetría por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="34fd6-111">The `dotnet` command itself doesn't collect telemetry.</span></span> <span data-ttu-id="34fd6-112">Los comandos de la CLI de .NET Core que se ejecutan mediante el comando `dotnet` son los que recopilan la telemetría.</span><span class="sxs-lookup"><span data-stu-id="34fd6-112">The .NET Core CLI commands run by the `dotnet` command collect the telemetry.</span></span>

<span data-ttu-id="34fd6-113">La telemetría *no está habilitada* cuando se usa el comando `dotnet` por sí mismo, sin ningún comando asociado:</span><span class="sxs-lookup"><span data-stu-id="34fd6-113">Telemetry *isn't enabled* when using the `dotnet` command itself, with no command attached:</span></span>

- `dotnet`
- `dotnet [path-to-app]`

<span data-ttu-id="34fd6-114">La telemetría *está habilitada* cuando se usan los [comandos de la CLI de .NET Core](index.md), como:</span><span class="sxs-lookup"><span data-stu-id="34fd6-114">Telemetry *is enabled* when using the [.NET Core CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="behavior"></a><span data-ttu-id="34fd6-115">Comportamiento</span><span class="sxs-lookup"><span data-stu-id="34fd6-115">Behavior</span></span>

<span data-ttu-id="34fd6-116">La característica de telemetría de la CLI de .NET Core está habilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="34fd6-116">The .NET Core CLI Tools telemetry feature is enabled by default.</span></span> <span data-ttu-id="34fd6-117">Puede desactivar la característica de telemetría si establece la variable de entorno `DOTNET_CLI_TELEMETRY_OPTOUT` en `1` o `true`.</span><span class="sxs-lookup"><span data-stu-id="34fd6-117">Opt-out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

## <a name="data-points"></a><span data-ttu-id="34fd6-118">Puntos de datos</span><span class="sxs-lookup"><span data-stu-id="34fd6-118">Data points</span></span>

<span data-ttu-id="34fd6-119">La característica recopila los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="34fd6-119">The feature collects the following data:</span></span>

- <span data-ttu-id="34fd6-120">Marca de tiempo de la invocación&#8224;</span><span class="sxs-lookup"><span data-stu-id="34fd6-120">Timestamp of invocation&#8224;</span></span>
- <span data-ttu-id="34fd6-121">Comando invocado (por ejemplo, “build”)&#8224;</span><span class="sxs-lookup"><span data-stu-id="34fd6-121">Command invoked (for example, "build")&#8224;</span></span>
- <span data-ttu-id="34fd6-122">Dirección IP de tres octetos usada para determinar la ubicación geográfica&#8224;</span><span class="sxs-lookup"><span data-stu-id="34fd6-122">Three octet IP address used to determine geographical location&#8224;</span></span>
- <span data-ttu-id="34fd6-123">`ExitCode` del comando</span><span class="sxs-lookup"><span data-stu-id="34fd6-123">`ExitCode` of the command</span></span>
- <span data-ttu-id="34fd6-124">Ejecutor de pruebas (para los proyectos de prueba)</span><span class="sxs-lookup"><span data-stu-id="34fd6-124">Test runner (for test projects)</span></span>
- <span data-ttu-id="34fd6-125">Sistema operativo y versión&#8224;</span><span class="sxs-lookup"><span data-stu-id="34fd6-125">Operating system and version&#8224;</span></span>
- <span data-ttu-id="34fd6-126">Si los id. de tiempo de ejecución están presentes en el nodo “runtimes”</span><span class="sxs-lookup"><span data-stu-id="34fd6-126">Whether runtime IDs are present in the runtimes node</span></span>
- <span data-ttu-id="34fd6-127">Versión del SDK de .NET Core&#8224;</span><span class="sxs-lookup"><span data-stu-id="34fd6-127">.NET Core SDK version&#8224;</span></span>

<span data-ttu-id="34fd6-128">&#8224;Esta métrica está publicada.</span><span class="sxs-lookup"><span data-stu-id="34fd6-128">&#8224;This metric is published.</span></span>

<span data-ttu-id="34fd6-129">A partir del SDK de .NET Core 2.0, se recopilan nuevos puntos de datos:</span><span class="sxs-lookup"><span data-stu-id="34fd6-129">Starting with .NET Core SDK 2.0, new data points are collected:</span></span>

- <span data-ttu-id="34fd6-130">Opciones y argumentos del comando `dotnet`: solo se recopilan opciones y argumentos conocidos (no cadenas arbitrarias).</span><span class="sxs-lookup"><span data-stu-id="34fd6-130">`dotnet` command arguments and options: only known arguments and options are collected (not arbitrary strings).</span></span>
- <span data-ttu-id="34fd6-131">Si el SDK se ejecuta en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="34fd6-131">Whether the SDK is running in a container.</span></span>
- <span data-ttu-id="34fd6-132">Marcos de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="34fd6-132">Target frameworks.</span></span>
- <span data-ttu-id="34fd6-133">Dirección MAC con hash: un id. único y anónimo criptográficamente (SHA256) para una máquina.</span><span class="sxs-lookup"><span data-stu-id="34fd6-133">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine.</span></span> <span data-ttu-id="34fd6-134">Esta métrica no está publicada.</span><span class="sxs-lookup"><span data-stu-id="34fd6-134">This metric is not published.</span></span>
- <span data-ttu-id="34fd6-135">Directorio de trabajo actual con hash.</span><span class="sxs-lookup"><span data-stu-id="34fd6-135">Hashed current working directory.</span></span>

<span data-ttu-id="34fd6-136">La característica no recopila datos personales, como direcciones de correo electrónico o nombres de usuario.</span><span class="sxs-lookup"><span data-stu-id="34fd6-136">The feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="34fd6-137">No examina el código ni extrae datos a nivel de proyecto confidenciales, como el nombre, el repositorio o el autor.</span><span class="sxs-lookup"><span data-stu-id="34fd6-137">It doesn't scan your code and doesn't extract sensitive project-level data, such as name, repo, or author.</span></span> <span data-ttu-id="34fd6-138">Los datos se envían de forma segura a los servidores de Microsoft con tecnología de [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/), se conservan bajo acceso restringido y se publican bajo controles de seguridad estrictos de sistemas seguros de [Azure Storage](https://azure.microsoft.com/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="34fd6-138">The data is sent securely to Microsoft servers using [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="34fd6-139">Queremos saber cómo se usan las herramientas y si funcionan correctamente, no qué va a compilar con las herramientas.</span><span class="sxs-lookup"><span data-stu-id="34fd6-139">We want to know how the tools are used and if they're working well, not what you're building with the tools.</span></span> <span data-ttu-id="34fd6-140">Si sospecha que la telemetría recopila datos confidenciales o que los estamos tratando de forma insegura o inapropiada, [informe de un problema en los problemas del repositorio de dotnet/cli](https://github.com/dotnet/cli/issues) para que lo investiguemos.</span><span class="sxs-lookup"><span data-stu-id="34fd6-140">If you suspect that the telemetry is collecting sensitive data or that we're insecurely or inappropriately handling data, [file an issue in the dotnet/cli repo issues](https://github.com/dotnet/cli/issues) for investigation.</span></span>

## <a name="published-data"></a><span data-ttu-id="34fd6-141">Datos publicados</span><span class="sxs-lookup"><span data-stu-id="34fd6-141">Published data</span></span>

<span data-ttu-id="34fd6-142">Los datos publicados están disponibles cada trimestre y se muestran en [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md) (Datos de uso del SDK de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="34fd6-142">Published data is available quarterly and are listed at [.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md).</span></span> <span data-ttu-id="34fd6-143">Las columnas de un archivo de datos son:</span><span class="sxs-lookup"><span data-stu-id="34fd6-143">The columns of a data file are:</span></span>
- <span data-ttu-id="34fd6-144">Timestamp</span><span class="sxs-lookup"><span data-stu-id="34fd6-144">Timestamp</span></span>
- <span data-ttu-id="34fd6-145">Occurrences&#8224;</span><span class="sxs-lookup"><span data-stu-id="34fd6-145">Occurrences&#8224;</span></span>
- <span data-ttu-id="34fd6-146">Command</span><span class="sxs-lookup"><span data-stu-id="34fd6-146">Command</span></span>
- <span data-ttu-id="34fd6-147">Geography&#8225;</span><span class="sxs-lookup"><span data-stu-id="34fd6-147">Geography&#8225;</span></span>
- <span data-ttu-id="34fd6-148">OSFamily</span><span class="sxs-lookup"><span data-stu-id="34fd6-148">OSFamily</span></span>
- <span data-ttu-id="34fd6-149">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="34fd6-149">RuntimeID</span></span>
- <span data-ttu-id="34fd6-150">OSVersion</span><span class="sxs-lookup"><span data-stu-id="34fd6-150">OSVersion</span></span>
- <span data-ttu-id="34fd6-151">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="34fd6-151">SDKVersion</span></span>

<span data-ttu-id="34fd6-152">&#8224;En la columna *Ocurrences* se muestra el número agregado de usos de ese comando para las métricas de esa fila durante ese día.</span><span class="sxs-lookup"><span data-stu-id="34fd6-152">&#8224;The *Occurrences* column displays the aggregate count of that command's use for that row's metrics that day.</span></span> 

<span data-ttu-id="34fd6-153">&#8225;Normalmente, en la columna *Geography* se muestra el nombre de un país.</span><span class="sxs-lookup"><span data-stu-id="34fd6-153">&#8225;Typically, the *Geography* column displays the name of a country.</span></span> <span data-ttu-id="34fd6-154">En algunos casos, el continente de Antártida aparece en esta columna, ya sea debido a los investigadores que usan .NET Core en la Antártida o a datos de ubicación incorrectos.</span><span class="sxs-lookup"><span data-stu-id="34fd6-154">In some cases, the continent of Antarctica appears in this column, either due to researchers using .NET Core in Antarctica or incorrect location data.</span></span>

### <a name="example"></a><span data-ttu-id="34fd6-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34fd6-155">Example</span></span>

| <span data-ttu-id="34fd6-156">Timestamp</span><span class="sxs-lookup"><span data-stu-id="34fd6-156">Timestamp</span></span>      | <span data-ttu-id="34fd6-157">Occurrences</span><span class="sxs-lookup"><span data-stu-id="34fd6-157">Occurrences</span></span> | <span data-ttu-id="34fd6-158">Command</span><span class="sxs-lookup"><span data-stu-id="34fd6-158">Command</span></span> | <span data-ttu-id="34fd6-159">Geography</span><span class="sxs-lookup"><span data-stu-id="34fd6-159">Geography</span></span> | <span data-ttu-id="34fd6-160">OSFamily</span><span class="sxs-lookup"><span data-stu-id="34fd6-160">OSFamily</span></span> | <span data-ttu-id="34fd6-161">RuntimeID</span><span class="sxs-lookup"><span data-stu-id="34fd6-161">RuntimeID</span></span>     | <span data-ttu-id="34fd6-162">OSVersion</span><span class="sxs-lookup"><span data-stu-id="34fd6-162">OSVersion</span></span> | <span data-ttu-id="34fd6-163">SDKVersion</span><span class="sxs-lookup"><span data-stu-id="34fd6-163">SDKVersion</span></span> |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| <span data-ttu-id="34fd6-164">4/16/2017 0:00</span><span class="sxs-lookup"><span data-stu-id="34fd6-164">4/16/2017 0:00</span></span> | <span data-ttu-id="34fd6-165">8</span><span class="sxs-lookup"><span data-stu-id="34fd6-165">8</span></span>           | <span data-ttu-id="34fd6-166">run</span><span class="sxs-lookup"><span data-stu-id="34fd6-166">run</span></span>     | <span data-ttu-id="34fd6-167">Uganda</span><span class="sxs-lookup"><span data-stu-id="34fd6-167">Uganda</span></span>    | <span data-ttu-id="34fd6-168">Darwin</span><span class="sxs-lookup"><span data-stu-id="34fd6-168">Darwin</span></span>   | <span data-ttu-id="34fd6-169">osx.10.12-x64</span><span class="sxs-lookup"><span data-stu-id="34fd6-169">osx.10.12-x64</span></span> | <span data-ttu-id="34fd6-170">10.12</span><span class="sxs-lookup"><span data-stu-id="34fd6-170">10.12</span></span>     | <span data-ttu-id="34fd6-171">1.0.1</span><span class="sxs-lookup"><span data-stu-id="34fd6-171">1.0.1</span></span>      |

### <a name="datasets"></a><span data-ttu-id="34fd6-172">Conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="34fd6-172">Datasets</span></span>

[<span data-ttu-id="34fd6-173">2016: tercer trimestre</span><span class="sxs-lookup"><span data-stu-id="34fd6-173">2016 - Q3</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)  
[<span data-ttu-id="34fd6-174">2016: cuarto trimestre</span><span class="sxs-lookup"><span data-stu-id="34fd6-174">2016 - Q4</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)  
[<span data-ttu-id="34fd6-175">2017: primer trimestre</span><span class="sxs-lookup"><span data-stu-id="34fd6-175">2017 - Q1</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)  
[<span data-ttu-id="34fd6-176">2017: segundo trimestre</span><span class="sxs-lookup"><span data-stu-id="34fd6-176">2017 - Q2</span></span>](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)

<span data-ttu-id="34fd6-177">Hay conjuntos de datos adicionales publicados con un formato de URL estándar.</span><span class="sxs-lookup"><span data-stu-id="34fd6-177">Additional datasets are posted using a standard URL format.</span></span> <span data-ttu-id="34fd6-178">Reemplace `<YEAR>` con el año y `<QUARTER>` con el trimestre del año (use `1`, `2`, `3` o `4`).</span><span class="sxs-lookup"><span data-stu-id="34fd6-178">Replace `<YEAR>` with the year and replace `<QUARTER>` with the quarter of the year (use `1`, `2`, `3`, or `4`).</span></span> <span data-ttu-id="34fd6-179">Los archivos están en formato de valores separados por tabulaciones (*TSV*).</span><span class="sxs-lookup"><span data-stu-id="34fd6-179">The files are in tab-separated values (*TSV*) format.</span></span> 

```
https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv
```

## <a name="license"></a><span data-ttu-id="34fd6-180">Licencia</span><span class="sxs-lookup"><span data-stu-id="34fd6-180">License</span></span>

<span data-ttu-id="34fd6-181">La distribución de Microsoft de .NET Core cuenta con licencia en virtud del [CLUF DE LA BIBLIOTECA DE MICROSOFT .NET](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="34fd6-181">The Microsoft distribution of .NET Core is licensed with the [MICROSOFT .NET LIBRARY EULA](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="34fd6-182">Esta licencia incluye la sección “DATOS” para habilitar la telemetría (se muestra a continuación).</span><span class="sxs-lookup"><span data-stu-id="34fd6-182">This license includes the "DATA" section to enable telemetry (shown below).</span></span>

<span data-ttu-id="34fd6-183">Los [paquetes NuGet de .NET](https://www.nuget.org/profiles/dotnetframework) usan la misma licencia, pero no permiten la telemetría (consulte [Ámbito](#scope)).</span><span class="sxs-lookup"><span data-stu-id="34fd6-183">[.NET NuGet packages](https://www.nuget.org/profiles/dotnetframework) use the same license but don't enable telemetry (see [Scope](#scope)).</span></span>

> 2. <span data-ttu-id="34fd6-184">DATOS.</span><span class="sxs-lookup"><span data-stu-id="34fd6-184">DATA.</span></span> <span data-ttu-id="34fd6-185">El software puede recopilar información sobre el usuario y la utilización del software y, después, enviarla a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34fd6-185">The software may collect information about you and your use of the software, and send that to Microsoft.</span></span> <span data-ttu-id="34fd6-186">Microsoft puede usarla para mejorar nuestros productos y servicios.</span><span class="sxs-lookup"><span data-stu-id="34fd6-186">Microsoft may use this information to improve our products and services.</span></span> <span data-ttu-id="34fd6-187">Puede obtener más información sobre la recopilación y el uso de datos en la documentación de ayuda y la declaración de privacidad en http://go.microsoft.com/fwlink/?LinkId=528096.</span><span class="sxs-lookup"><span data-stu-id="34fd6-187">You can learn more about data collection and use in the help documentation and the privacy statement at http://go.microsoft.com/fwlink/?LinkId=528096.</span></span> <span data-ttu-id="34fd6-188">Al usar el software, se entiende que da su consentimiento para la realización de estas prácticas.</span><span class="sxs-lookup"><span data-stu-id="34fd6-188">Your use of the software operates as your consent to these practices.</span></span>

## <a name="disclosure"></a><span data-ttu-id="34fd6-189">Divulgación</span><span class="sxs-lookup"><span data-stu-id="34fd6-189">Disclosure</span></span>

<span data-ttu-id="34fd6-190">Las herramientas de la CLI de .NET Core muestran el texto siguiente cuando ejecuta por primera vez uno de los comandos (por ejemplo, `dotnet restore`).</span><span class="sxs-lookup"><span data-stu-id="34fd6-190">The .NET Core CLI Tools display the following text when you first run one of the commands (for example, `dotnet restore`).</span></span> <span data-ttu-id="34fd6-191">El texto puede variar ligeramente según la versión del SDK que ejecute.</span><span class="sxs-lookup"><span data-stu-id="34fd6-191">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="34fd6-192">Esta experiencia de "primera vista" es la forma en que Microsoft le notifica sobre la recopilación de datos.</span><span class="sxs-lookup"><span data-stu-id="34fd6-192">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.
 
Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience. The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.
```

## <a name="see-also"></a><span data-ttu-id="34fd6-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="34fd6-193">See also</span></span>

<span data-ttu-id="34fd6-194">[What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/) (Lo que hemos aprendido de la telemetría del SDK de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="34fd6-194">[What we've learned from .NET Core SDK Telemetry](https://blogs.msdn.microsoft.com/dotnet/2017/07/21/what-weve-learned-from-net-core-sdk-telemetry/)</span></span>  
<span data-ttu-id="34fd6-195">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch)](https://github.com/dotnet/cli/blob/release/2.0.0/src/dotnet/Telemetry.cs)  (Origen de referencia de telemetría)</span><span class="sxs-lookup"><span data-stu-id="34fd6-195">[Telemetry reference source (dotnet/cli repo; release/2.0.0 branch)](https://github.com/dotnet/cli/blob/release/2.0.0/src/dotnet/Telemetry.cs) </span></span>  
<span data-ttu-id="34fd6-196">[.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md) (Datos de uso del SDK de .NET Core)</span><span class="sxs-lookup"><span data-stu-id="34fd6-196">[.NET Core SDK Usage Data](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)</span></span>

