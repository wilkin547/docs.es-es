---
title: Recopilación de telemetría mediante la CLI de ML.NET
description: Descubra las características de telemetría de la CLI de ML.NET que recopilan información de uso para el análisis, qué datos se recopilan y cómo deshabilitarlas. Además, encuentre vínculos al contrato de licencia de .NET, así como información sobre el cumplimiento de Microsoft del RGPD.
ms.topic: conceptual
ms.date: 06/03/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 833ee2ae54cf3a52adaf070837a33e00267d25dc
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599846"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a><span data-ttu-id="15c6c-104">Recopilación de telemetría mediante la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="15c6c-104">Telemetry collection by the ML.NET CLI</span></span>

<span data-ttu-id="15c6c-105">La [CLI de ML.NET](https://aka.ms/mlnet-cli) incluye una característica de telemetría que recopila datos de uso anónimos que se agregan para su uso por parte de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="15c6c-105">The [ML.NET CLI](https://aka.ms/mlnet-cli) includes a telemetry feature that collects anonymous usage data that is aggregated for use by Microsoft.</span></span>

## <a name="how-microsoft-uses-the-data"></a><span data-ttu-id="15c6c-106">Cómo Microsoft usa los datos</span><span class="sxs-lookup"><span data-stu-id="15c6c-106">How Microsoft uses the data</span></span>

<span data-ttu-id="15c6c-107">El equipo del producto usa los datos de telemetría de la CLI de ML.NET para ayudar a entender cómo mejorar las herramientas.</span><span class="sxs-lookup"><span data-stu-id="15c6c-107">The product team uses ML.NET CLI telemetry data to help understand how to improve the tools.</span></span> <span data-ttu-id="15c6c-108">Por ejemplo, si los clientes usan con poca frecuencia determinada tarea de aprendizaje de automático, el equipo del producto investiga por qué y usa las conclusiones para dar prioridad al desarrollo de características.</span><span class="sxs-lookup"><span data-stu-id="15c6c-108">For example, if customers infrequently use a particular machine learning task, the product team investigates why and uses findings to prioritize feature development.</span></span> <span data-ttu-id="15c6c-109">La telemetría de la CLI de ML.NET también ayuda con la depuración de problemas, como bloqueos y anomalías de código.</span><span class="sxs-lookup"><span data-stu-id="15c6c-109">ML.NET CLI telemetry also helps with debugging of issues such as crashes and code anomalies.</span></span>

<span data-ttu-id="15c6c-110">Mientras que el equipo del producto valora esta información, también sabemos que no todos desean enviar estos datos.</span><span class="sxs-lookup"><span data-stu-id="15c6c-110">While the product team appreciates this insight, we also know that not everyone wants to send this data.</span></span> [<span data-ttu-id="15c6c-111">Averigüe cómo deshabilitar la telemetría.</span><span class="sxs-lookup"><span data-stu-id="15c6c-111">Find out how to disable telemetry.</span></span>](#opt-out-of-data-collection)

## <a name="scope"></a><span data-ttu-id="15c6c-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="15c6c-112">Scope</span></span>

<span data-ttu-id="15c6c-113">El comando `mlnet` inicia la CLI de ML.NET, pero el comando por sí mismo no recopila la telemetría.</span><span class="sxs-lookup"><span data-stu-id="15c6c-113">The `mlnet` command launches the ML.NET CLI, but the command itself doesn't collect telemetry.</span></span>

<span data-ttu-id="15c6c-114">La telemetría *no está habilitada* cuando se ejecuta el comando `mlnet` sin ningún comando asociado.</span><span class="sxs-lookup"><span data-stu-id="15c6c-114">Telemetry *isn't enabled* when you run the `mlnet` command with no other command attached.</span></span> <span data-ttu-id="15c6c-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="15c6c-115">For example:</span></span>

- `mlnet`
- `mlnet --help`

<span data-ttu-id="15c6c-116">La telemetría *está habilitada* al ejecutar un [comando de la CLI de ML.NET](../reference/ml-net-cli-reference.md), tal como `mlnet classification`.</span><span class="sxs-lookup"><span data-stu-id="15c6c-116">Telemetry *is enabled* when you run an [ML.NET CLI command](../reference/ml-net-cli-reference.md), such as `mlnet classification`.</span></span>

## <a name="opt-out-of-data-collection"></a><span data-ttu-id="15c6c-117">No participar en la recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="15c6c-117">Opt out of data collection</span></span>

<span data-ttu-id="15c6c-118">La característica de telemetría de la CLI de ML.NET está habilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="15c6c-118">The ML.NET CLI telemetry feature is enabled by default.</span></span>

<span data-ttu-id="15c6c-119">Puede desactivar la característica de telemetría si establece la variable de entorno `MLDOTNET_CLI_TELEMETRY_OPTOUT` en `1` o `true`.</span><span class="sxs-lookup"><span data-stu-id="15c6c-119">Opt out of the telemetry feature by setting the `MLDOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span> <span data-ttu-id="15c6c-120">Esta variable de entorno se aplica globalmente a la herramienta CLI de ML.NET.</span><span class="sxs-lookup"><span data-stu-id="15c6c-120">This environment variable applies globally to the ML.NET CLI tool.</span></span>

## <a name="data-points-collected"></a><span data-ttu-id="15c6c-121">Punto de datos recopilados</span><span class="sxs-lookup"><span data-stu-id="15c6c-121">Data points collected</span></span>

<span data-ttu-id="15c6c-122">La característica recopila los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="15c6c-122">The feature collects the following data:</span></span>

- <span data-ttu-id="15c6c-123">Qué comando se invocó, por ejemplo, `classification`</span><span class="sxs-lookup"><span data-stu-id="15c6c-123">What command was invoked, such as `classification`</span></span>
- <span data-ttu-id="15c6c-124">Nombres de parámetros de línea de comandos usados (es decir, "dataset, label-col, output-path, train-time, verbosity")</span><span class="sxs-lookup"><span data-stu-id="15c6c-124">Command-line parameter names used (that is, "dataset, label-col, output-path, train-time, verbosity")</span></span>
- <span data-ttu-id="15c6c-125">Dirección MAC con hash: un id. único y anónimo criptográficamente (SHA256) para una máquina</span><span class="sxs-lookup"><span data-stu-id="15c6c-125">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine</span></span>
- <span data-ttu-id="15c6c-126">Marca de tiempo de una invocación</span><span class="sxs-lookup"><span data-stu-id="15c6c-126">Timestamp of an invocation</span></span>
- <span data-ttu-id="15c6c-127">Dirección IP de tres octetos (no la dirección IP completa) usada solo para determinar la ubicación geográfica</span><span class="sxs-lookup"><span data-stu-id="15c6c-127">Three octet IP address (not full IP address) used only to determine geographical location</span></span>
- <span data-ttu-id="15c6c-128">Nombre de todos los argumentos y parámetros utilizados.</span><span class="sxs-lookup"><span data-stu-id="15c6c-128">Name of all arguments/parameters used.</span></span> <span data-ttu-id="15c6c-129">No los valores del cliente, como las cadenas</span><span class="sxs-lookup"><span data-stu-id="15c6c-129">Not the customer's values, such as strings</span></span>
- <span data-ttu-id="15c6c-130">Nombre de archivo del conjunto de datos con hash</span><span class="sxs-lookup"><span data-stu-id="15c6c-130">Hashed dataset filename</span></span>
- <span data-ttu-id="15c6c-131">Depósito de tamaño de archivo del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="15c6c-131">Dataset file-size bucket</span></span>
- <span data-ttu-id="15c6c-132">Sistema operativo y versión</span><span class="sxs-lookup"><span data-stu-id="15c6c-132">Operating system and version</span></span>
- <span data-ttu-id="15c6c-133">Valor de los comandos de la tarea de Machine Learning: Valores categóricos, como `regression`, `classification`, y `recommendation`</span><span class="sxs-lookup"><span data-stu-id="15c6c-133">Value of ML task commands: Categorical values, such as `regression`, `classification`, and `recommendation`</span></span>
- <span data-ttu-id="15c6c-134">Versión de la CLI de ML.NET (es decir, 0.3.27703.4)</span><span class="sxs-lookup"><span data-stu-id="15c6c-134">ML.NET CLI version (that is, 0.3.27703.4)</span></span>

<span data-ttu-id="15c6c-135">Los datos se envían de forma segura a los servidores de Microsoft con tecnología de [Azure Application Insights](https://azure.microsoft.com/services/application-insights/), se conservan bajo acceso restringido y se utilizan bajo controles de seguridad estrictos de sistemas seguros de [Azure Storage](https://azure.microsoft.com/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="15c6c-135">The data is sent securely to Microsoft servers using [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and used under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

### <a name="data-points-not-collected"></a><span data-ttu-id="15c6c-136">Punto de datos no recopilados</span><span class="sxs-lookup"><span data-stu-id="15c6c-136">Data points not collected</span></span>

<span data-ttu-id="15c6c-137">La característica de telemetría *no* recopila:</span><span class="sxs-lookup"><span data-stu-id="15c6c-137">The telemetry feature *doesn't* collect:</span></span>

- <span data-ttu-id="15c6c-138">datos personales, como los nombres de usuario</span><span class="sxs-lookup"><span data-stu-id="15c6c-138">personal data, such as usernames</span></span>
- <span data-ttu-id="15c6c-139">nombres de archivo de conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="15c6c-139">dataset filenames</span></span>
- <span data-ttu-id="15c6c-140">datos de los archivos del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="15c6c-140">data from dataset files</span></span>

<span data-ttu-id="15c6c-141">Si sospecha que la telemetría de la CLI de ML.NET recopila datos confidenciales o que los datos se están tratando de forma insegura o inapropiada, informe de un problema en los problemas del repositorio de [ML.NET](https://github.com/dotnet/machinelearning) para que lo investiguemos.</span><span class="sxs-lookup"><span data-stu-id="15c6c-141">If you suspect that the ML.NET CLI telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [ML.NET](https://github.com/dotnet/machinelearning) repository for investigation.</span></span>

## <a name="license"></a><span data-ttu-id="15c6c-142">Licencia</span><span class="sxs-lookup"><span data-stu-id="15c6c-142">License</span></span>

<span data-ttu-id="15c6c-143">La distribución de Microsoft de la CLI de ML.NET cuenta con licencia en virtud de los [términos de licencia del software de Microsoft: biblioteca de Microsoft .NET](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="15c6c-143">The Microsoft distribution of ML.NET CLI is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="15c6c-144">Para obtener más información sobre la recolección y el procesamiento de datos, vea la sección titulada "Datos".</span><span class="sxs-lookup"><span data-stu-id="15c6c-144">For details on data collection and processing, see the section entitled "Data."</span></span>

## <a name="disclosure"></a><span data-ttu-id="15c6c-145">Divulgación</span><span class="sxs-lookup"><span data-stu-id="15c6c-145">Disclosure</span></span>

<span data-ttu-id="15c6c-146">Al ejecutar por primera vez un [comando de la CLI de ML.NET](../reference/ml-net-cli-reference.md) como `mlnet classification`, la herramienta de la CLI de ML.NET muestra el texto de divulgación que indica cómo dejar de participar en la telemetría.</span><span class="sxs-lookup"><span data-stu-id="15c6c-146">When you first run a [ML.NET CLI command](../reference/ml-net-cli-reference.md) such as `mlnet classification`, the ML.NET CLI tool displays disclosure text that tells you how to opt out of telemetry.</span></span> <span data-ttu-id="15c6c-147">El texto puede variar ligeramente según la versión de la CLI que ejecute.</span><span class="sxs-lookup"><span data-stu-id="15c6c-147">Text may vary slightly depending on the version of the CLI you're running.</span></span>

## <a name="see-also"></a><span data-ttu-id="15c6c-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="15c6c-148">See also</span></span>

- [<span data-ttu-id="15c6c-149">Referencia de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="15c6c-149">ML.NET CLI reference</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="15c6c-150">Términos de licencia del software de Microsoft: biblioteca de Microsoft .NET</span><span class="sxs-lookup"><span data-stu-id="15c6c-150">Microsoft Software License Terms: Microsoft .NET Library</span></span>](https://aka.ms/dotnet-core-eula)
- [<span data-ttu-id="15c6c-151">Privacidad en Microsoft</span><span class="sxs-lookup"><span data-stu-id="15c6c-151">Privacy at Microsoft</span></span>](https://www.microsoft.com/trustcenter/privacy/)
- [<span data-ttu-id="15c6c-152">Declaración de privacidad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="15c6c-152">Microsoft Privacy Statement</span></span>](https://privacy.microsoft.com/privacystatement)
