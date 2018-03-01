---
title: Controlar el registro de .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 90de9dd6bd32eb2142dceb98c142f3c50a0a5691
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="9f339-102">Controlar el registro de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9f339-102">Controlling .NET Framework Logging</span></span>
<span data-ttu-id="9f339-103">Se puede utilizar el seguimiento de eventos para Windows (ETW) para registrar los eventos de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9f339-103">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="9f339-104">Es posible crear y ver los seguimientos mediante las siguientes herramientas:</span><span class="sxs-lookup"><span data-stu-id="9f339-104">You can create and view traces by using the following tools:</span></span>  
  
-   <span data-ttu-id="9f339-105">Las herramientas de línea de comandos [Logman](http://go.microsoft.com/fwlink/?LinkId=150916) y [Tracerpt](http://go.microsoft.com/fwlink/?LinkId=150919), que se incluyen con el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="9f339-105">The [Logman](http://go.microsoft.com/fwlink/?LinkId=150916) and [Tracerpt](http://go.microsoft.com/fwlink/?LinkId=150919) command-line tools, which are included with the Windows operating system.</span></span>  
  
-   <span data-ttu-id="9f339-106">Las herramientas [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) del [Kit de herramientas de rendimiento de Windows](http://msdn.microsoft.com/library/windows/hardware/hh162945.aspx).</span><span class="sxs-lookup"><span data-stu-id="9f339-106">The [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) tools in the [Windows Performance Toolkit](http://msdn.microsoft.com/library/windows/hardware/hh162945.aspx).</span></span> <span data-ttu-id="9f339-107">Para obtener más información sobre Xperf, vea el [blog de rendimiento de Windows](http://go.microsoft.com/fwlink/?LinkId=179509).</span><span class="sxs-lookup"><span data-stu-id="9f339-107">For more information about Xperf, see the [Windows Performance blog](http://go.microsoft.com/fwlink/?LinkId=179509).</span></span>  
  
 <span data-ttu-id="9f339-108">Para capturar información de eventos de CLR, el proveedor de CLR debe estar instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9f339-108">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="9f339-109">Para confirmar que el proveedor está instalado, escriba `logman query providers` en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="9f339-109">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="9f339-110">Se muestra una lista de proveedores.</span><span class="sxs-lookup"><span data-stu-id="9f339-110">A list of providers is displayed.</span></span> <span data-ttu-id="9f339-111">Esta lista debería contener una entrada para el proveedor de CLR, del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="9f339-111">This list should contain an entry for the CLR provider, as follows.</span></span>  
  
```  
Provider                                 GUID  
-------------------------------------------------------------------------------  
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.  
```  
  
 <span data-ttu-id="9f339-112">Si el proveedor de CLR no aparece en la lista, puede instalarlo en Windows Vista y sistemas operativos posteriores mediante la herramienta de línea de comandos [Wevtutil](http://go.microsoft.com/fwlink/?LinkID=150915) de Windows.</span><span class="sxs-lookup"><span data-stu-id="9f339-112">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](http://go.microsoft.com/fwlink/?LinkID=150915) command-line tool.</span></span> <span data-ttu-id="9f339-113">Abra la ventana Símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="9f339-113">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="9f339-114">Cambie del directorio del símbolo del sistema a la carpeta [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.versión de .NET>\).</span><span class="sxs-lookup"><span data-stu-id="9f339-114">Change the prompt directory to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="9f339-115">Esta carpeta contiene el archivo CLR-ETW.man.</span><span class="sxs-lookup"><span data-stu-id="9f339-115">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="9f339-116">En el símbolo del sistema, escriba el siguiente comando para instalar el proveedor de CLR.</span><span class="sxs-lookup"><span data-stu-id="9f339-116">At the command prompt, type the following command to install the CLR provider:</span></span>  
  
 `wevtutil im CLR-ETW.man`  
  
## <a name="capturing-clr-etw-events"></a><span data-ttu-id="9f339-117">Capturar eventos ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="9f339-117">Capturing CLR ETW Events</span></span>  
 <span data-ttu-id="9f339-118">Puede usar las herramientas de línea de comandos [Logman](http://go.microsoft.com/fwlink/?LinkId=150916) y [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) para capturar eventos ETW y las herramientas [Tracerpt](http://go.microsoft.com/fwlink/?LinkId=150919) y [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) para descodificar eventos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9f339-118">You can use the [Logman](http://go.microsoft.com/fwlink/?LinkId=150916) and [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) command-line tools to capture ETW events, and the [Tracerpt](http://go.microsoft.com/fwlink/?LinkId=150919) and [Xperf](http://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) tools to decode the trace events.</span></span>  
  
 <span data-ttu-id="9f339-119">Para activar el registro, el usuario debe especificar tres cosas:</span><span class="sxs-lookup"><span data-stu-id="9f339-119">To turn on logging, a user must specify three things:</span></span>  
  
-   <span data-ttu-id="9f339-120">El proveedor con el que comunicarse.</span><span class="sxs-lookup"><span data-stu-id="9f339-120">The provider to communicate to.</span></span>  
  
-   <span data-ttu-id="9f339-121">Número de 64 bits que representa un conjunto de palabras clave.</span><span class="sxs-lookup"><span data-stu-id="9f339-121">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="9f339-122">Cada palabra clave representa un conjunto de eventos que el proveedor puede activar.</span><span class="sxs-lookup"><span data-stu-id="9f339-122">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="9f339-123">El número representa un conjunto combinado de palabras clave que se pueden activar.</span><span class="sxs-lookup"><span data-stu-id="9f339-123">The number represents a combined set of keywords to turn on.</span></span>  
  
-   <span data-ttu-id="9f339-124">Un número pequeño que representa el nivel (de detalle) con que se realiza el registro.</span><span class="sxs-lookup"><span data-stu-id="9f339-124">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="9f339-125">El nivel 1 es el menos detallado y el nivel 5, el más detallado.</span><span class="sxs-lookup"><span data-stu-id="9f339-125">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="9f339-126">El nivel 0 es un valor predeterminado cuyo significado es específico del proveedor.</span><span class="sxs-lookup"><span data-stu-id="9f339-126">Level 0 is a default whose meaning is provider-specific.</span></span>  
  
#### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="9f339-127">Para capturar eventos ETW de CLR mediante Logman</span><span class="sxs-lookup"><span data-stu-id="9f339-127">To capture CLR ETW events using Logman</span></span>  
  
1.  <span data-ttu-id="9f339-128">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="9f339-128">At the command prompt, type:</span></span>  
  
     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`  
  
     <span data-ttu-id="9f339-129">donde:</span><span class="sxs-lookup"><span data-stu-id="9f339-129">where:</span></span>  
  
    -   <span data-ttu-id="9f339-130">El parámetro `-p` identifica el GUID del proveedor.</span><span class="sxs-lookup"><span data-stu-id="9f339-130">The `-p` parameter identifies the provider GUID.</span></span>  
  
    -   <span data-ttu-id="9f339-131">`0x1CCBD` especifica las categorías de eventos que se van a producir.</span><span class="sxs-lookup"><span data-stu-id="9f339-131">`0x1CCBD` specifies the categories of events that will be raised.</span></span>  
  
    -   <span data-ttu-id="9f339-132">`0x5` establece el nivel de registro (en este caso, detallado (5)).</span><span class="sxs-lookup"><span data-stu-id="9f339-132">`0x5` sets the level of logging (in this case, verbose (5)).</span></span>  
  
    -   <span data-ttu-id="9f339-133">El parámetro `-ets` indica a Logman que envíe los comandos a las sesiones de seguimiento de eventos.</span><span class="sxs-lookup"><span data-stu-id="9f339-133">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>  
  
    -   <span data-ttu-id="9f339-134">El parámetro `-ct perf` especifica que la función `QueryPerformanceCounter` se utilizará para registrar la marca de tiempo para cada evento.</span><span class="sxs-lookup"><span data-stu-id="9f339-134">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>  
  
2.  <span data-ttu-id="9f339-135">Para dejar de registrar los eventos, escriba:</span><span class="sxs-lookup"><span data-stu-id="9f339-135">To stop logging the events, type:</span></span>  
  
     `logman stop clrevents -ets`  
  
     <span data-ttu-id="9f339-136">Este comando crea un archivo de seguimiento binario denominado clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="9f339-136">This command creates a binary trace file named clrevents.etl.</span></span>  
  
#### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="9f339-137">Para capturar eventos ETW de CLR mediante Xperf</span><span class="sxs-lookup"><span data-stu-id="9f339-137">To capture CLR ETW events using Xperf</span></span>  
  
1.  <span data-ttu-id="9f339-138">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="9f339-138">At the command prompt, type:</span></span>  
  
     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`  
  
     <span data-ttu-id="9f339-139">donde el GUID es el GUID del proveedor de ETW de CLR y `0x1CCBD:5` realiza la traza de todo en el nivel 5 y por debajo de este (detallado).</span><span class="sxs-lookup"><span data-stu-id="9f339-139">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>  
  
2.  <span data-ttu-id="9f339-140">Para detener el seguimiento, escriba:</span><span class="sxs-lookup"><span data-stu-id="9f339-140">To stop tracing, type:</span></span>  
  
     `Xperf -stop clr`  
  
     <span data-ttu-id="9f339-141">Este comando crea un archivo de seguimiento denominado clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="9f339-141">This command creates a trace file named clrevents.etl.</span></span>  
  
## <a name="viewing-clr-etw-events"></a><span data-ttu-id="9f339-142">Ver eventos ETW de CLR</span><span class="sxs-lookup"><span data-stu-id="9f339-142">Viewing CLR ETW Events</span></span>  
 <span data-ttu-id="9f339-143">Utilice los comandos enumerados a continuación para ver los eventos ETW de CLR.</span><span class="sxs-lookup"><span data-stu-id="9f339-143">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="9f339-144">Para obtener una descripción de los eventos, vea [Eventos ETW de CLR](../../../docs/framework/performance/clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="9f339-144">For a description of the events, see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md).</span></span>  
  
#### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="9f339-145">Para ver los eventos ETW de CLR mediante Tracerpt</span><span class="sxs-lookup"><span data-stu-id="9f339-145">To view CLR ETW events using Tracerpt</span></span>  
  
-   <span data-ttu-id="9f339-146">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="9f339-146">At the command prompt, type:</span></span>  
  
     `tracerpt clrevents.etl`  
  
     <span data-ttu-id="9f339-147">Este comando crea dos archivos: dumpfile.xml y summary.txt.</span><span class="sxs-lookup"><span data-stu-id="9f339-147">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="9f339-148">El archivo dumpfile.xml muestra todos los eventos y summary.txt proporciona un resumen de ellos.</span><span class="sxs-lookup"><span data-stu-id="9f339-148">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>  
  
#### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="9f339-149">Para ver los eventos ETW de CLR mediante Xperf</span><span class="sxs-lookup"><span data-stu-id="9f339-149">To view CLR ETW events using Xperf</span></span>  
  
-   <span data-ttu-id="9f339-150">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="9f339-150">At the command prompt, type:</span></span>  
  
     `xperf clrevents.etl`  
  
     <span data-ttu-id="9f339-151">Este comando abre el visor de archivos ETL Xperf.</span><span class="sxs-lookup"><span data-stu-id="9f339-151">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="9f339-152">En este visor, los eventos de CLR se presentan en la vista **Eventos genéricos**.</span><span class="sxs-lookup"><span data-stu-id="9f339-152">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="9f339-153">Para mostrar una cuadrícula de datos de eventos clasificados por tipos, seleccione un área de tiempo en esta vista y, después, haga clic con el botón derecho del mouse y seleccione **Resumen**.</span><span class="sxs-lookup"><span data-stu-id="9f339-153">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>  
  
#### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="9f339-154">Para convertir el archivo .etl en un archivo de valores separados por comas</span><span class="sxs-lookup"><span data-stu-id="9f339-154">To convert the .etl file to a comma-separated value file</span></span>  
  
-   <span data-ttu-id="9f339-155">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="9f339-155">At the command prompt, type:</span></span>  
  
     `xperf -i clrevents.etl -f clrevents.csv`  
  
     <span data-ttu-id="9f339-156">Este comando hace que XPerf vuelque los eventos en un archivo de valores separados por comas (CSV) que se puede consultar.</span><span class="sxs-lookup"><span data-stu-id="9f339-156">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="9f339-157">Dado que los distintos eventos tienen campos distintos, este archivo CSV contiene más de una línea de encabezado antes de los datos.</span><span class="sxs-lookup"><span data-stu-id="9f339-157">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="9f339-158">El primer campo de cada línea es el tipo de evento, que indica qué encabezado se debería utilizar para determinar el resto de los campos.</span><span class="sxs-lookup"><span data-stu-id="9f339-158">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f339-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f339-159">See Also</span></span>  
 [<span data-ttu-id="9f339-160">Kit de herramientas de rendimiento de Windows</span><span class="sxs-lookup"><span data-stu-id="9f339-160">Windows Performance Toolkit</span></span>](http://go.microsoft.com/fwlink/?LinkID=161141)  
 [<span data-ttu-id="9f339-161">Eventos ETW en Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="9f339-161">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
