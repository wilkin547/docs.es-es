---
title: Controlar el registro de .NET Framework
description: Use el seguimiento de eventos para Windows (ETW) para controlar los eventos de registro y Common Language Runtime de registros de .NET (CLR). Use herramientas como Logman, tracerpt y Xperf.
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
ms.openlocfilehash: 45d9244eb11b914fd203f24057e1b65c6bef18c2
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309591"
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="389ef-104">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="389ef-104">Controlling .NET Framework Logging</span></span>

<span data-ttu-id="389ef-105">Se puede utilizar el seguimiento de eventos para Windows (ETW) para registrar los eventos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="389ef-105">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="389ef-106">Es posible crear y ver los seguimientos mediante las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="389ef-106">You can create and view traces by using the following tools:</span></span>

- <span data-ttu-id="389ef-107">Las herramientas de línea de comandos [Logman](/windows-server/administration/windows-commands/logman) y [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1), que se incluyen con el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="389ef-107">The [Logman](/windows-server/administration/windows-commands/logman) and [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) command-line tools, which are included with the Windows operating system.</span></span>

- <span data-ttu-id="389ef-108">Las herramientas [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) del [Kit de herramientas de rendimiento de Windows](/windows-hardware/test/wpt/).</span><span class="sxs-lookup"><span data-stu-id="389ef-108">The [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools in the [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span></span> <span data-ttu-id="389ef-109">Para obtener más información sobre Xperf, vea el [blog de rendimiento de Windows](https://docs.microsoft.com/archive/blogs/pigscanfly/).</span><span class="sxs-lookup"><span data-stu-id="389ef-109">For more information about Xperf, see the [Windows Performance blog](https://docs.microsoft.com/archive/blogs/pigscanfly/).</span></span>

<span data-ttu-id="389ef-110">Para capturar información de eventos de CLR, el proveedor de CLR debe estar instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="389ef-110">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="389ef-111">Para confirmar que el proveedor está instalado, escriba `logman query providers` en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="389ef-111">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="389ef-112">Se muestra una lista de proveedores.</span><span class="sxs-lookup"><span data-stu-id="389ef-112">A list of providers is displayed.</span></span> <span data-ttu-id="389ef-113">Esta lista debería contener una entrada para el proveedor de CLR, del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="389ef-113">This list should contain an entry for the CLR provider, as follows.</span></span>

```output
Provider                                 GUID
-------------------------------------------------------------------------------
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.
```

<span data-ttu-id="389ef-114">Si el proveedor de CLR no aparece en la lista, puede instalarlo en Windows Vista y sistemas operativos posteriores mediante la herramienta de línea de comandos [Wevtutil](/windows-server/administration/windows-commands/wevtutil) de Windows.</span><span class="sxs-lookup"><span data-stu-id="389ef-114">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil) command-line tool.</span></span> <span data-ttu-id="389ef-115">Abra una ventana del símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="389ef-115">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="389ef-116">Cambie el directorio prompt a la carpeta .NET Framework 4 (%WINDIR%\Microsoft.NET\Framework [64] \v4. \<.NET version> \ ).</span><span class="sxs-lookup"><span data-stu-id="389ef-116">Change the prompt directory to the .NET Framework 4 folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="389ef-117">Esta carpeta contiene el archivo CLR-ETW.man.</span><span class="sxs-lookup"><span data-stu-id="389ef-117">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="389ef-118">En el símbolo del sistema, escriba el siguiente comando para instalar el proveedor de CLR.</span><span class="sxs-lookup"><span data-stu-id="389ef-118">At the command prompt, type the following command to install the CLR provider:</span></span>

`wevtutil im CLR-ETW.man`

## <a name="capturing-clr-etw-events"></a><span data-ttu-id="389ef-119">Capturar eventos ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="389ef-119">Capturing CLR ETW Events</span></span>

<span data-ttu-id="389ef-120">Puede usar las herramientas de línea de comandos [Logman](/windows-server/administration/windows-commands/logman) y [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) para capturar eventos ETW y las herramientas [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) y [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) para descodificar eventos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="389ef-120">You can use the [Logman](/windows-server/administration/windows-commands/logman) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) command-line tools to capture ETW events, and the [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools to decode the trace events.</span></span>

<span data-ttu-id="389ef-121">Para activar el registro, el usuario debe especificar tres cosas:</span><span class="sxs-lookup"><span data-stu-id="389ef-121">To turn on logging, a user must specify three things:</span></span>

- <span data-ttu-id="389ef-122">El proveedor con el que comunicarse.</span><span class="sxs-lookup"><span data-stu-id="389ef-122">The provider to communicate to.</span></span>

- <span data-ttu-id="389ef-123">Número de 64 bits que representa un conjunto de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="389ef-123">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="389ef-124">Cada palabra clave representa un conjunto de eventos que el proveedor puede activar.</span><span class="sxs-lookup"><span data-stu-id="389ef-124">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="389ef-125">El número representa un conjunto combinado de palabras clave que se pueden activar.</span><span class="sxs-lookup"><span data-stu-id="389ef-125">The number represents a combined set of keywords to turn on.</span></span>

- <span data-ttu-id="389ef-126">Un número pequeño que representa el nivel (de detalle) con que se realiza el registro.</span><span class="sxs-lookup"><span data-stu-id="389ef-126">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="389ef-127">El nivel 1 es el menos detallado y el nivel 5, el más detallado.</span><span class="sxs-lookup"><span data-stu-id="389ef-127">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="389ef-128">El nivel 0 es un valor predeterminado cuyo significado es específico del proveedor.</span><span class="sxs-lookup"><span data-stu-id="389ef-128">Level 0 is a default whose meaning is provider-specific.</span></span>

### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="389ef-129">Para capturar eventos ETW de CLR mediante Logman</span><span class="sxs-lookup"><span data-stu-id="389ef-129">To capture CLR ETW events using Logman</span></span>

1. <span data-ttu-id="389ef-130">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="389ef-130">At the command prompt, type:</span></span>

     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`

     <span data-ttu-id="389ef-131">donde:</span><span class="sxs-lookup"><span data-stu-id="389ef-131">where:</span></span>

    - <span data-ttu-id="389ef-132">El parámetro `-p` identifica el GUID del proveedor.</span><span class="sxs-lookup"><span data-stu-id="389ef-132">The `-p` parameter identifies the provider GUID.</span></span>

    - <span data-ttu-id="389ef-133">`0x1CCBD` especifica las categorías de eventos que se van a producir.</span><span class="sxs-lookup"><span data-stu-id="389ef-133">`0x1CCBD` specifies the categories of events that will be raised.</span></span>

    - <span data-ttu-id="389ef-134">`0x5` establece el nivel de registro (en este caso, detallado (5)).</span><span class="sxs-lookup"><span data-stu-id="389ef-134">`0x5` sets the level of logging (in this case, verbose (5)).</span></span>

    - <span data-ttu-id="389ef-135">El parámetro `-ets` indica a Logman que envíe los comandos a las sesiones de seguimiento de eventos.</span><span class="sxs-lookup"><span data-stu-id="389ef-135">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>

    - <span data-ttu-id="389ef-136">El parámetro `-ct perf` especifica que la función `QueryPerformanceCounter` se utilizará para registrar la marca de tiempo para cada evento.</span><span class="sxs-lookup"><span data-stu-id="389ef-136">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>

2. <span data-ttu-id="389ef-137">Para dejar de registrar los eventos, escriba:</span><span class="sxs-lookup"><span data-stu-id="389ef-137">To stop logging the events, type:</span></span>

     `logman stop clrevents -ets`

     <span data-ttu-id="389ef-138">Este comando crea un archivo de seguimiento binario denominado clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="389ef-138">This command creates a binary trace file named clrevents.etl.</span></span>

### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="389ef-139">Para capturar eventos ETW de CLR mediante Xperf</span><span class="sxs-lookup"><span data-stu-id="389ef-139">To capture CLR ETW events using Xperf</span></span>

1. <span data-ttu-id="389ef-140">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="389ef-140">At the command prompt, type:</span></span>

     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`

     <span data-ttu-id="389ef-141">donde el GUID es el GUID del proveedor de ETW de CLR y `0x1CCBD:5` realiza la traza de todo en el nivel 5 y por debajo de este (detallado).</span><span class="sxs-lookup"><span data-stu-id="389ef-141">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>

2. <span data-ttu-id="389ef-142">Para detener el seguimiento, escriba:</span><span class="sxs-lookup"><span data-stu-id="389ef-142">To stop tracing, type:</span></span>

     `Xperf -stop clr`

     <span data-ttu-id="389ef-143">Este comando crea un archivo de seguimiento denominado clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="389ef-143">This command creates a trace file named clrevents.etl.</span></span>

## <a name="viewing-clr-etw-events"></a><span data-ttu-id="389ef-144">Ver eventos ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="389ef-144">Viewing CLR ETW Events</span></span>

<span data-ttu-id="389ef-145">Utilice los comandos enumerados a continuación para ver los eventos ETW de CLR.</span><span class="sxs-lookup"><span data-stu-id="389ef-145">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="389ef-146">Para obtener una descripción de los eventos, vea [Eventos ETW de CLR](clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="389ef-146">For a description of the events, see [CLR ETW Events](clr-etw-events.md).</span></span>

### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="389ef-147">Para ver los eventos ETW de CLR mediante Tracerpt</span><span class="sxs-lookup"><span data-stu-id="389ef-147">To view CLR ETW events using Tracerpt</span></span>

- <span data-ttu-id="389ef-148">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="389ef-148">At the command prompt, type:</span></span>

     `tracerpt clrevents.etl`

     <span data-ttu-id="389ef-149">Este comando crea dos archivos: dumpfile.xml y summary.txt.</span><span class="sxs-lookup"><span data-stu-id="389ef-149">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="389ef-150">El archivo dumpfile.xml muestra todos los eventos y summary.txt proporciona un resumen de ellos.</span><span class="sxs-lookup"><span data-stu-id="389ef-150">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>

### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="389ef-151">Para ver los eventos ETW de CLR mediante Xperf</span><span class="sxs-lookup"><span data-stu-id="389ef-151">To view CLR ETW events using Xperf</span></span>

- <span data-ttu-id="389ef-152">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="389ef-152">At the command prompt, type:</span></span>

     `xperf clrevents.etl`

     <span data-ttu-id="389ef-153">Este comando abre el visor de archivos ETL Xperf.</span><span class="sxs-lookup"><span data-stu-id="389ef-153">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="389ef-154">En este visor, los eventos de CLR se presentan en la vista **Eventos genéricos**.</span><span class="sxs-lookup"><span data-stu-id="389ef-154">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="389ef-155">Para mostrar una cuadrícula de datos de eventos clasificados por tipos, seleccione un área de tiempo en esta vista y, después, haga clic con el botón derecho del mouse y seleccione **Resumen**.</span><span class="sxs-lookup"><span data-stu-id="389ef-155">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>

### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="389ef-156">Para convertir el archivo .etl en un archivo de valores separados por comas</span><span class="sxs-lookup"><span data-stu-id="389ef-156">To convert the .etl file to a comma-separated value file</span></span>

- <span data-ttu-id="389ef-157">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="389ef-157">At the command prompt, type:</span></span>

     `xperf -i clrevents.etl -f clrevents.csv`

     <span data-ttu-id="389ef-158">Este comando hace que XPerf vuelque los eventos en un archivo de valores separados por comas (CSV) que se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="389ef-158">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="389ef-159">Dado que los distintos eventos tienen campos distintos, este archivo CSV contiene más de una línea de encabezado antes de los datos.</span><span class="sxs-lookup"><span data-stu-id="389ef-159">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="389ef-160">El primer campo de cada línea es el tipo de evento, que indica qué encabezado se debería utilizar para determinar el resto de los campos.</span><span class="sxs-lookup"><span data-stu-id="389ef-160">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="389ef-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="389ef-161">See also</span></span>

- [<span data-ttu-id="389ef-162">Kit de herramientas de rendimiento de Windows</span><span class="sxs-lookup"><span data-stu-id="389ef-162">Windows Performance Toolkit</span></span>](/windows-hardware/test/wpt/)
- [<span data-ttu-id="389ef-163">Eventos ETW en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="389ef-163">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
