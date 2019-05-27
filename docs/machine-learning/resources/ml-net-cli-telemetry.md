---
title: Recopilación de telemetría mediante la CLI de ML.NET
description: Descubra las características de telemetría de la CLI de ML.NET que recopilan información de uso para el análisis, qué datos se recopilan y cómo deshabilitarlas. Además, encuentre vínculos al contrato de licencia de .NET, así como información sobre el cumplimiento de Microsoft del RGPD.
ms.topic: conceptual
ms.date: 05/05/2019
ms.custom: ''
ms.openlocfilehash: 49ebd6c9e1b77c85d891b8c9fb8cbd5c66b478a9
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065548"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a><span data-ttu-id="13b08-104">Recopilación de telemetría mediante la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="13b08-104">Telemetry collection by the ML.NET CLI</span></span>

<span data-ttu-id="13b08-105">La [CLI de ML.NET](http://aka.ms/mlnet-cli) incluye una característica de telemetría que recopila datos de uso anónimos que se agregan para su uso por parte de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13b08-105">The [ML.NET CLI](http://aka.ms/mlnet-cli) includes a telemetry feature that collects anonymous usage data that is aggregated for use by Microsoft.</span></span>

## <a name="how-microsoft-uses-the-data"></a><span data-ttu-id="13b08-106">Cómo Microsoft usa los datos</span><span class="sxs-lookup"><span data-stu-id="13b08-106">How Microsoft uses the data</span></span>

<span data-ttu-id="13b08-107">El equipo del producto usa los datos de telemetría de la CLI de ML.NET para ayudar a entender cómo mejorar las herramientas.</span><span class="sxs-lookup"><span data-stu-id="13b08-107">The product team uses ML.NET CLI telemetry data to help understand how to improve the tools.</span></span> <span data-ttu-id="13b08-108">Por ejemplo, si los clientes usan con poca frecuencia determinada tarea de aprendizaje de automático, el equipo del producto investiga por qué y usa las conclusiones para dar prioridad al desarrollo de características.</span><span class="sxs-lookup"><span data-stu-id="13b08-108">For example, if customers infrequently use a particular machine learning task, the product team investigates why and uses findings to prioritize feature development.</span></span> <span data-ttu-id="13b08-109">La telemetría de la CLI de ML.NET también ayuda con la depuración de problemas, como bloqueos y anomalías de código.</span><span class="sxs-lookup"><span data-stu-id="13b08-109">ML.NET CLI telemetry also helps with debugging of issues such as crashes and code anomalies.</span></span> 

<span data-ttu-id="13b08-110">Mientras que el equipo del producto valora esta información, también sabemos que no todos desean enviar estos datos.</span><span class="sxs-lookup"><span data-stu-id="13b08-110">While the product team appreciates this insight, we also know that not everyone wants to send this data.</span></span> [<span data-ttu-id="13b08-111">Averigüe cómo deshabilitar la telemetría.</span><span class="sxs-lookup"><span data-stu-id="13b08-111">Find out how to disable telemetry.</span></span>](#opt-out-of-data-collection)

## <a name="scope"></a><span data-ttu-id="13b08-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="13b08-112">Scope</span></span>

<span data-ttu-id="13b08-113">El comando `mlnet` inicia la CLI de ML.NET, pero el comando por sí mismo no recopila la telemetría.</span><span class="sxs-lookup"><span data-stu-id="13b08-113">The `mlnet` command launches the ML.NET CLI, but the command itself doesn't collect telemetry.</span></span>

<span data-ttu-id="13b08-114">La telemetría *no está habilitada* cuando se ejecuta el comando `mlnet` sin ningún comando asociado.</span><span class="sxs-lookup"><span data-stu-id="13b08-114">Telemetry *isn't enabled* when you run the `mlnet` command with no other command attached.</span></span> <span data-ttu-id="13b08-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="13b08-115">For example:</span></span>

- `mlnet`
- `mlnet --help`

<span data-ttu-id="13b08-116">La telemetría *está habilitada* al ejecutar un [comando de la CLI de ML.NET](../reference/ml-net-cli-reference.md), tal como `mlnet auto-train`.</span><span class="sxs-lookup"><span data-stu-id="13b08-116">Telemetry *is enabled* when you run an [ML.NET CLI command](../reference/ml-net-cli-reference.md), such as `mlnet auto-train`.</span></span>

## <a name="opt-out-of-data-collection"></a><span data-ttu-id="13b08-117">No participar en la recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="13b08-117">Opt out of data collection</span></span>

<span data-ttu-id="13b08-118">La característica de telemetría de la CLI de ML.NET está habilitada de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="13b08-118">The ML.NET CLI telemetry feature is enabled by default.</span></span>

<span data-ttu-id="13b08-119">Puede desactivar la característica de telemetría si establece la variable de entorno `DOTNET_CLI_TELEMETRY_OPTOUT` en `1` o `true`.</span><span class="sxs-lookup"><span data-stu-id="13b08-119">Opt out of the telemetry feature by setting the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span> <span data-ttu-id="13b08-120">Esta variable de entorno se aplica globalmente a la herramienta de la CLI de .NET.</span><span class="sxs-lookup"><span data-stu-id="13b08-120">This environment variable applies globally to the .NET CLI tool.</span></span>

## <a name="data-points-collected"></a><span data-ttu-id="13b08-121">Punto de datos recopilados</span><span class="sxs-lookup"><span data-stu-id="13b08-121">Data points collected</span></span>

<span data-ttu-id="13b08-122">La característica recopila los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="13b08-122">The feature collects the following data:</span></span>

- <span data-ttu-id="13b08-123">Los comandos que se invocan, como `auto-train`</span><span class="sxs-lookup"><span data-stu-id="13b08-123">Which commands are invoked, such as `auto-train`</span></span>
- <span data-ttu-id="13b08-124">Dirección MAC con hash: un id. único y anónimo criptográficamente (SHA256) para una máquina</span><span class="sxs-lookup"><span data-stu-id="13b08-124">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine</span></span>
- <span data-ttu-id="13b08-125">Marca de tiempo de una invocación</span><span class="sxs-lookup"><span data-stu-id="13b08-125">Timestamp of an invocation</span></span>
- <span data-ttu-id="13b08-126">Dirección IP de tres octetos usada solo para determinar la ubicación geográfica</span><span class="sxs-lookup"><span data-stu-id="13b08-126">Three octet IP address used only to determine geographical location</span></span>
- <span data-ttu-id="13b08-127">Nombre de todos los argumentos y parámetros utilizados.</span><span class="sxs-lookup"><span data-stu-id="13b08-127">Name of all arguments/parameters used.</span></span> <span data-ttu-id="13b08-128">No los valores del cliente, como las cadenas</span><span class="sxs-lookup"><span data-stu-id="13b08-128">Not the customer's values, such as strings</span></span>
- <span data-ttu-id="13b08-129">Sistema operativo y versión</span><span class="sxs-lookup"><span data-stu-id="13b08-129">Operating system and version</span></span>
- <span data-ttu-id="13b08-130">Valor del parámetro --ml-task: Valores categóricos, como `regression`, `binary-classification`, y `multiclass-classification`</span><span class="sxs-lookup"><span data-stu-id="13b08-130">Value of --ml-task parameter: Categorical values, such as `regression`, `binary-classification`, and `multiclass-classification`</span></span>
- <span data-ttu-id="13b08-131">Tamaño de archivo del conjunto de datos de [logarítmica redondeada](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power) (a la potencia al cuadrado más próxima)</span><span class="sxs-lookup"><span data-stu-id="13b08-131">[Logarithmic rounded](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power) dataset file size (nearest power of 2)</span></span>
- <span data-ttu-id="13b08-132">`ExitCode` del comando</span><span class="sxs-lookup"><span data-stu-id="13b08-132">`ExitCode` of the command</span></span>

<span data-ttu-id="13b08-133">Los datos se envían de forma segura a los servidores de Microsoft con tecnología de [Azure Application Insights](https://azure.microsoft.com/services/application-insights/), se conservan bajo acceso restringido y se utilizan bajo controles de seguridad estrictos de sistemas seguros de [Azure Storage](https://azure.microsoft.com/services/storage/).</span><span class="sxs-lookup"><span data-stu-id="13b08-133">The data is sent securely to Microsoft servers using [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and used under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

### <a name="data-points-not-collected"></a><span data-ttu-id="13b08-134">Punto de datos no recopilados</span><span class="sxs-lookup"><span data-stu-id="13b08-134">Data points not collected</span></span>
<span data-ttu-id="13b08-135">La característica de telemetría *no* recopila:</span><span class="sxs-lookup"><span data-stu-id="13b08-135">The telemetry feature *doesn't* collect:</span></span>
- <span data-ttu-id="13b08-136">datos personales, como los nombres de usuario</span><span class="sxs-lookup"><span data-stu-id="13b08-136">personal data, such as usernames</span></span>
- <span data-ttu-id="13b08-137">nombres de archivo de conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="13b08-137">dataset filenames</span></span>
- <span data-ttu-id="13b08-138">datos de los archivos del conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="13b08-138">data from dataset files</span></span>

<span data-ttu-id="13b08-139">Si sospecha que la telemetría de la CLI de ML.NET recopila datos confidenciales o que los datos se están tratando de forma insegura o inapropiada, informe de un problema en los problemas del repositorio de [ML.NET](https://github.com/dotnet/machinelearning) para que lo investiguemos.</span><span class="sxs-lookup"><span data-stu-id="13b08-139">If you suspect that the ML.NET CLI telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [ML.NET](https://github.com/dotnet/machinelearning) repository for investigation.</span></span>

## <a name="license"></a><span data-ttu-id="13b08-140">Licencia</span><span class="sxs-lookup"><span data-stu-id="13b08-140">License</span></span>

<span data-ttu-id="13b08-141">La distribución de Microsoft de la CLI de ML.NET cuenta con licencia en virtud de los [términos de licencia del software de Microsoft: biblioteca de Microsoft .NET](https://aka.ms/dotnet-core-eula).</span><span class="sxs-lookup"><span data-stu-id="13b08-141">The Microsoft distribution of ML.NET CLI is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="13b08-142">Para obtener más información sobre la recolección y el procesamiento de datos, vea la sección titulada "Datos".</span><span class="sxs-lookup"><span data-stu-id="13b08-142">For details on data collection and processing, see the section entitled "Data."</span></span>

## <a name="disclosure"></a><span data-ttu-id="13b08-143">Divulgación</span><span class="sxs-lookup"><span data-stu-id="13b08-143">Disclosure</span></span>

<span data-ttu-id="13b08-144">Al ejecutar por primera vez un [comando de la CLI de ML.NET](../reference/ml-net-cli-reference.md) como `mlnet auto-train`, la herramienta de la CLI de ML.NET muestra el texto de divulgación que indica cómo dejar de participar en la telemetría.</span><span class="sxs-lookup"><span data-stu-id="13b08-144">When you first run a [ML.NET CLI command](../reference/ml-net-cli-reference.md) such as `mlnet auto-train`, the ML.NET CLI tool displays disclosure text that tells you how to opt out of telemetry.</span></span> <span data-ttu-id="13b08-145">El texto puede variar ligeramente según la versión de la CLI que ejecute.</span><span class="sxs-lookup"><span data-stu-id="13b08-145">Text may vary slightly depending on the version of the CLI you're running.</span></span>

## <a name="see-also"></a><span data-ttu-id="13b08-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="13b08-146">See also</span></span>
- [<span data-ttu-id="13b08-147">Referencia de la CLI de ML.NET</span><span class="sxs-lookup"><span data-stu-id="13b08-147">ML.NET CLI reference</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="13b08-148">Términos de licencia del software de Microsoft: biblioteca de Microsoft .NET</span><span class="sxs-lookup"><span data-stu-id="13b08-148">Microsoft Software License Terms: Microsoft .NET Library</span></span>](https://aka.ms/dotnet-core-eula)
- [<span data-ttu-id="13b08-149">Privacidad en Microsoft</span><span class="sxs-lookup"><span data-stu-id="13b08-149">Privacy at Microsoft</span></span>](https://www.microsoft.com/en-us/trustcenter/privacy/)
- [<span data-ttu-id="13b08-150">Declaración de privacidad de Microsoft</span><span class="sxs-lookup"><span data-stu-id="13b08-150">Microsoft Privacy Statement</span></span>](https://privacy.microsoft.com/en-us/privacystatement)
