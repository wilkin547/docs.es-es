---
title: Cómo depurar servicios y aplicaciones con reconocimiento de notificaciones mediante el seguimiento de WIF
ms.date: 03/30/2017
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
author: BrucePerlerMS
ms.openlocfilehash: 604ebf5ad71197f6614ffa45b6d7c181d474e1aa
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990478"
---
# <a name="how-to-debug-claims-aware-applications-and-services-using-wif-tracing"></a><span data-ttu-id="53b45-102">Cómo depurar servicios y aplicaciones con reconocimiento de notificaciones mediante el seguimiento de WIF</span><span class="sxs-lookup"><span data-stu-id="53b45-102">How To: Debug Claims-Aware Applications And Services Using WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="53b45-103">Se aplica a</span><span class="sxs-lookup"><span data-stu-id="53b45-103">Applies To</span></span>  
  
- <span data-ttu-id="53b45-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="53b45-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="53b45-105">Herramienta del visor de seguimiento de servicio (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="53b45-105">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>  
  
- <span data-ttu-id="53b45-106">Solución de problemas y depuración de aplicaciones de WIF</span><span class="sxs-lookup"><span data-stu-id="53b45-106">Troubleshooting and Debugging WIF Applications</span></span>  
  
## <a name="summary"></a><span data-ttu-id="53b45-107">Resumen</span><span class="sxs-lookup"><span data-stu-id="53b45-107">Summary</span></span>  
 <span data-ttu-id="53b45-108">En este procedimiento se describen los pasos necesarios para configurar el seguimiento de WIF, recopilar registros de seguimiento y analizar los registros de seguimiento con la herramienta Visor de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="53b45-108">This How-To describes required steps for how to configure WIF tracing, collect trace logs, and how to analyze the trace logs using Trace Viewer tool.</span></span> <span data-ttu-id="53b45-109">Proporciona una correspondencia entre las entradas de seguimiento y las acciones necesarias para solucionar los problemas relacionados con WIF.</span><span class="sxs-lookup"><span data-stu-id="53b45-109">It provides general mapping for trace entries to actions needed to troubleshoot issues related to WIF.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="53b45-110">Contenido</span><span class="sxs-lookup"><span data-stu-id="53b45-110">Contents</span></span>  
  
- <span data-ttu-id="53b45-111">Objetivos</span><span class="sxs-lookup"><span data-stu-id="53b45-111">Objectives</span></span>  
  
- <span data-ttu-id="53b45-112">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="53b45-112">Summary of Steps</span></span>  
  
- <span data-ttu-id="53b45-113">Paso 1: configurar el seguimiento de WIF mediante el archivo de configuración Web.config</span><span class="sxs-lookup"><span data-stu-id="53b45-113">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
- <span data-ttu-id="53b45-114">Paso 2: analizar los archivos de seguimiento de WIF mediante la herramienta Visor de seguimiento</span><span class="sxs-lookup"><span data-stu-id="53b45-114">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
- <span data-ttu-id="53b45-115">Paso 3: identificar soluciones para corregir los problemas relacionados con WIF</span><span class="sxs-lookup"><span data-stu-id="53b45-115">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
- <span data-ttu-id="53b45-116">Elementos relacionados</span><span class="sxs-lookup"><span data-stu-id="53b45-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="53b45-117">Objetivos</span><span class="sxs-lookup"><span data-stu-id="53b45-117">Objectives</span></span>  
  
- <span data-ttu-id="53b45-118">Configurar el seguimiento de WIF.</span><span class="sxs-lookup"><span data-stu-id="53b45-118">Configure WIF tracing.</span></span>  
  
- <span data-ttu-id="53b45-119">Ver los registros de seguimiento en la herramienta Visor de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="53b45-119">View trace logs in the Trace Viewer tool.</span></span>  
  
- <span data-ttu-id="53b45-120">Identificar los problemas relacionados con WIF en los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="53b45-120">Identify WIF related issues in the trace logs.</span></span>  
  
- <span data-ttu-id="53b45-121">Aplicar acciones correctivas a los problemas relacionados con WIF encontrados en los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="53b45-121">Apply corrective actions to WIF related issues found in the trace logs.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="53b45-122">Resumen de pasos</span><span class="sxs-lookup"><span data-stu-id="53b45-122">Summary of Steps</span></span>  
  
- <span data-ttu-id="53b45-123">Paso 1: configurar el seguimiento de WIF mediante el archivo de configuración Web.config</span><span class="sxs-lookup"><span data-stu-id="53b45-123">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
- <span data-ttu-id="53b45-124">Paso 2: analizar los archivos de seguimiento de WIF mediante la herramienta Visor de seguimiento</span><span class="sxs-lookup"><span data-stu-id="53b45-124">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
- <span data-ttu-id="53b45-125">Paso 3: identificar soluciones para corregir los problemas relacionados con WIF</span><span class="sxs-lookup"><span data-stu-id="53b45-125">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
## <a name="step-1--configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="53b45-126">Paso 1: configurar el seguimiento de WIF mediante el archivo de configuración Web.config</span><span class="sxs-lookup"><span data-stu-id="53b45-126">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
 <span data-ttu-id="53b45-127">En este paso, realizará cambios en las secciones de configuración del archivo *Web.config* que permite a WIF realizar un seguimiento de sus eventos y almacenarlos en un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="53b45-127">In this step, you will add changes to configuration sections in the *Web.config* file that enable WIF to trace its events and store them in a trace log.</span></span>  
  
#### <a name="to-configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="53b45-128">Para configurar el seguimiento de WIF mediante el archivo de configuración Web.config</span><span class="sxs-lookup"><span data-stu-id="53b45-128">To configure WIF tracing using Web.config configuration file</span></span>  
  
1. <span data-ttu-id="53b45-129">Abra el archivo de configuración raíz **Web.config** o **App.config** en el editor de Visual Studio. Para ello, haga doble clic en él en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="53b45-129">Open the root **Web.config** or **App.config** configuration file in the Visual Studio editor by double clicking on it in **Solution Explorer**.</span></span> <span data-ttu-id="53b45-130">Si su solución no tiene un archivo de configuración **Web.config** o **App.config**, agréguelo. Para ello, haga clic con el botón derecho en la solución en el **Explorador de soluciones**, haga clic en **Agregar** y, después, haga clic en **Nuevo elemento…**</span><span class="sxs-lookup"><span data-stu-id="53b45-130">If your solution does not have **Web.config** or **App.config** configuration file, add it by right clicking on the solution in the **Solution Explorer** and clicking **Add**, then clicking **New Item…**.</span></span> <span data-ttu-id="53b45-131">En el cuadro de diálogo **Nuevo elemento**, seleccione **Archivo de configuración de la aplicación** para **App.config** o **Archivo de configuración web** para **Web.config** en la lista y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53b45-131">On the **New Item** dialog, Select **Application Configuration File** for **App.config** or **Web Configuration File** for **Web.config** from the list and click **OK**.</span></span>  
  
2. <span data-ttu-id="53b45-132">Agregue las entradas de configuración similares a las siguientes al archivo de configuración, en el nodo **\<configuration>** al final del archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="53b45-132">Add the configuration entries similar to the following to the configuration file inside **\<configuration>** node at the end of the configuration file:</span></span>  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3. <span data-ttu-id="53b45-133">La configuración anterior le indica a WIF que genere eventos de seguimiento detallados y los registre en el archivo *WIFTrace.e2e*.</span><span class="sxs-lookup"><span data-stu-id="53b45-133">The above configuration instructs WIF to generate verbose trace events and log them into *WIFTrace.e2e* file.</span></span> <span data-ttu-id="53b45-134">Para obtener una lista completa de los valores del modificador **switchValue** , consulte la tabla del nivel de seguimiento que se encuentra en el tema siguiente: [Configuración](../wcf/diagnostics/tracing/configuring-tracing.md)de la traza.</span><span class="sxs-lookup"><span data-stu-id="53b45-134">For a complete list of values for the **switchValue** switch, refer to the Trace Level table found in the following topic: [Configuring Tracing](../wcf/diagnostics/tracing/configuring-tracing.md).</span></span>  
  
## <a name="step-2--analyze-wif-trace-files-using-trace-viewer-tool"></a><span data-ttu-id="53b45-135">Paso 2: analizar los archivos de seguimiento de WIF mediante la herramienta Visor de seguimiento</span><span class="sxs-lookup"><span data-stu-id="53b45-135">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
 <span data-ttu-id="53b45-136">En este paso, usará la herramienta Visor de seguimiento (SvcTraceViewer.exe) para analizar los registros de seguimiento de WIF.</span><span class="sxs-lookup"><span data-stu-id="53b45-136">In this step, you will use the Trace Viewer Tool (SvcTraceViewer.exe) to analyze WIF trace logs.</span></span>  
  
#### <a name="to-analyze-wif-trace-logs-using-trace-viewer-tool-svctraceviewerexe"></a><span data-ttu-id="53b45-137">Para analizar los registros de seguimiento de WIF con la herramienta Visor de seguimiento (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="53b45-137">To analyze WIF trace logs using Trace Viewer tool (SvcTraceViewer.exe)</span></span>  
  
1. <span data-ttu-id="53b45-138">La herramienta Visor de seguimiento (SvcTraceViewer.exe) se incluye como parte de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="53b45-138">Trace Viewer tool (SvcTraceViewer.exe) ships as part of the Windows SDK.</span></span> <span data-ttu-id="53b45-139">Si aún no ha instalado el Windows SDK, puede descargarlo aquí: [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).</span><span class="sxs-lookup"><span data-stu-id="53b45-139">If you haven’t already installed the Windows SDK, you can download it here: [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).</span></span>  
  
2. <span data-ttu-id="53b45-140">Ejecute la herramienta Visor de seguimiento (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="53b45-140">Run the Trace Viewer tool (SvcTraceViewer.exe).</span></span> <span data-ttu-id="53b45-141">Normalmente está disponible en la carpeta **Bin** de la ruta de instalación.</span><span class="sxs-lookup"><span data-stu-id="53b45-141">It is typically available in the **Bin** folder of the installation path.</span></span>  
  
3. <span data-ttu-id="53b45-142">Para abrir el archivo de registro de seguimiento de WIF, por ejemplo, WIFTrace.e2e, seleccione la opción **Archivo**, **Abrir…**</span><span class="sxs-lookup"><span data-stu-id="53b45-142">Open the WIF trace log file, for example, WIFTrace.e2e by selecting **File**, **Open…**</span></span> <span data-ttu-id="53b45-143">en el menú o use el acceso directo **Ctrl+O**.</span><span class="sxs-lookup"><span data-stu-id="53b45-143">option in the menu or using the **Ctrl+O** shortcut.</span></span> <span data-ttu-id="53b45-144">Se abre el archivo de registro de seguimiento en la herramienta Visor de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="53b45-144">The trace log file opens in the Trace Viewer tool.</span></span>  
  
4. <span data-ttu-id="53b45-145">Consulte las entradas de la pestaña **Actividad**. Cada entrada debe contener un número de actividad, el número de seguimientos que se registraron, la duración de la actividad y sus marcas de tiempo de inicio y finalización.</span><span class="sxs-lookup"><span data-stu-id="53b45-145">Review entries in the **Activity** tab. Each entry should contain an activity number, the number of traces that were logged, duration of the activity and its start and end timestamps.</span></span>  
  
5. <span data-ttu-id="53b45-146">Haga clic en la pestaña **Actividad**. Verá las entradas de seguimiento detalladas en el área principal de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="53b45-146">Click on the **Activity** tab. You should see detailed trace entries in the main area of the tool.</span></span> <span data-ttu-id="53b45-147">Use la lista desplegable **nivel** del menú para filtrar el nivel específico de seguimientos, por ejemplo: **Todo**, **ADVERTENCIA**, **errores**, **información**, etc.</span><span class="sxs-lookup"><span data-stu-id="53b45-147">Use the **Level** dropdown list on the menu to filter specific level of traces, for example: **All**, **Warning**, **Errors**, **Information**, etc.</span></span>  
  
6. <span data-ttu-id="53b45-148">Haga clic en entradas de seguimiento específicas para revisar los detalles en el área inferior de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="53b45-148">Click on specific trace entries to review the details in the lower area of the tool.</span></span> <span data-ttu-id="53b45-149">Elija las pestañas **Con formato** o **XML** para ver los detalles en la vista correspondiente.</span><span class="sxs-lookup"><span data-stu-id="53b45-149">The details can be viewed using **Formatted** and **XML** view by choosing corresponding tabs.</span></span>  
  
## <a name="step-3--identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="53b45-150">Paso 3: identificar soluciones para corregir los problemas relacionados con WIF</span><span class="sxs-lookup"><span data-stu-id="53b45-150">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
 <span data-ttu-id="53b45-151">En este paso, puede encontrar soluciones a problemas relacionados con WIF identificados con la herramienta Visor de seguimiento y el registro de seguimiento de WIF.</span><span class="sxs-lookup"><span data-stu-id="53b45-151">In this step, you can identify solutions for WIF-related issues identified by using the WIF trace log and Trace Viewer tool.</span></span> <span data-ttu-id="53b45-152">Realiza una correspondencia general entre las excepciones de WIF y sus posibles soluciones o las acciones necesarias para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="53b45-152">It outlines general mapping of WIF related exceptions to potential solutions or required actions to troubleshoot the issue.</span></span>  
  
#### <a name="to-identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="53b45-153">Para identificar soluciones para corregir los problemas relacionados con WIF</span><span class="sxs-lookup"><span data-stu-id="53b45-153">To identify solutions to fix WIF related issues</span></span>  
  
1. <span data-ttu-id="53b45-154">Revise la siguiente tabla de excepciones de WIF y las acciones necesarias para corregir los problemas.</span><span class="sxs-lookup"><span data-stu-id="53b45-154">Review the following table of WIF exceptions and the required actions to correct the issues.</span></span>  
  
|<span data-ttu-id="53b45-155">**Identificador del error**</span><span class="sxs-lookup"><span data-stu-id="53b45-155">**Error ID**</span></span>|<span data-ttu-id="53b45-156">**Mensaje de error**</span><span class="sxs-lookup"><span data-stu-id="53b45-156">**Error Message**</span></span>|<span data-ttu-id="53b45-157">**Acción necesaria para corregir el error**</span><span class="sxs-lookup"><span data-stu-id="53b45-157">**Action needed to fix the error**</span></span>|  
|-|-|-|  
|<span data-ttu-id="53b45-158">ID4175</span><span class="sxs-lookup"><span data-stu-id="53b45-158">ID4175</span></span>|<span data-ttu-id="53b45-159">IssuerNameRegistry no reconoció el emisor del token de seguridad.</span><span class="sxs-lookup"><span data-stu-id="53b45-159">The issuer of the security token was not recognized by the IssuerNameRegistry.</span></span>  <span data-ttu-id="53b45-160">Para aceptar los tokens de seguridad de este emisor, configure IssuerNameRegistry para devolver un nombre válido para este emisor.</span><span class="sxs-lookup"><span data-stu-id="53b45-160">To accept security tokens from this issuer, configure the IssuerNameRegistry to return a valid name for this issuer.</span></span>|<span data-ttu-id="53b45-161">Este error se puede producir cuando se copia una huella digital desde el complemento MMC y se pega en el archivo *Web.config*.</span><span class="sxs-lookup"><span data-stu-id="53b45-161">This error can be caused by copying a thumbprint from the MMC snap-in and pasting it into the *Web.config* file.</span></span> <span data-ttu-id="53b45-162">En concreto, puede obtener un carácter adicional no imprimible en la cadena de texto cuando se copia desde la ventana de propiedades del certificado.</span><span class="sxs-lookup"><span data-stu-id="53b45-162">Specifically, you can get an extra non-printable character in the text string when copying from the certificate properties window.</span></span> <span data-ttu-id="53b45-163">Este carácter adicional produce un error en la coincidencia de la huella digital.</span><span class="sxs-lookup"><span data-stu-id="53b45-163">This extra character causes the thumbprint match to fail.</span></span> <span data-ttu-id="53b45-164">El procedimiento para copiar correctamente la huella digital se puede encontrar en [el inicio de sesión único basado en notificaciones para web y Microsoft Azure](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29).</span><span class="sxs-lookup"><span data-stu-id="53b45-164">The procedure for correctly copying the thumbprint can be found at [Claims-Based Single Sign-On for the Web and Microsoft Azure](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29).</span></span>|  
  
## <a name="related-items"></a><span data-ttu-id="53b45-165">Elementos relacionados</span><span class="sxs-lookup"><span data-stu-id="53b45-165">Related Items</span></span>  
  
- [<span data-ttu-id="53b45-166">Uso del visor de seguimiento de servicios para ver seguimientos asociados y para la solución de problemas</span><span class="sxs-lookup"><span data-stu-id="53b45-166">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
