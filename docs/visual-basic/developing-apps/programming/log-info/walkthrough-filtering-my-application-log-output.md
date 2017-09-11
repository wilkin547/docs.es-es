---
title: Filtrar el resultado de My.Application.Log (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Log object, filtering output
- My.Application.Log object, filtering output
- application event logs, output filtering
ms.assetid: 2c0a457a-38a4-49e1-934d-a51320b7b4ca
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a19bd71f1346be292dcc7b143a0080ac1cf11ec0
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-filtering-myapplicationlog-output-visual-basic"></a><span data-ttu-id="a24be-102">Tutorial: Filtrar el resultado de My.Application.Log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a24be-102">Walkthrough: Filtering My.Application.Log Output (Visual Basic)</span></span>
<span data-ttu-id="a24be-103">En este tutorial se muestra cómo cambiar el filtrado del registro predeterminado para el objeto `My.Application.Log`, para controlar qué información se pasa desde el objeto `Log` a los agentes de escucha y qué información escriben estos.</span><span class="sxs-lookup"><span data-stu-id="a24be-103">This walkthrough demonstrates how to change the default log filtering for the `My.Application.Log` object, to control what information is passed from the `Log` object to the listeners and what information is written by the listeners.</span></span> <span data-ttu-id="a24be-104">Puede cambiar el comportamiento del registro incluso después de generar la aplicación, porque la información de configuración se almacena en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a24be-104">You can change the logging behavior even after building the application, because the configuration information is stored in the application's configuration file.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="a24be-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="a24be-105">Getting Started</span></span>  
 <span data-ttu-id="a24be-106">Cada mensaje que `My.Application.Log` escribe tiene un nivel de gravedad asociado, que los mecanismos de filtrado usan para controlar el resultado del registro.</span><span class="sxs-lookup"><span data-stu-id="a24be-106">Each message that `My.Application.Log` writes has an associated severity level, which filtering mechanisms use to control the log output.</span></span> <span data-ttu-id="a24be-107">En esta aplicación de ejemplo se usan métodos `My.Application.Log` para escribir varios mensajes de registro con distintos niveles de gravedad.</span><span class="sxs-lookup"><span data-stu-id="a24be-107">This sample application uses `My.Application.Log` methods to write several log messages with different severity levels.</span></span>  
  
#### <a name="to-build-the-sample-application"></a><span data-ttu-id="a24be-108">Para crear la aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a24be-108">To build the sample application</span></span>  
  
1.  <span data-ttu-id="a24be-109">Abra un proyecto de aplicación Windows de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] nuevo.</span><span class="sxs-lookup"><span data-stu-id="a24be-109">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="a24be-110">Agregue un botón denominado Button1 a Form1.</span><span class="sxs-lookup"><span data-stu-id="a24be-110">Add a button named Button1 to Form1.</span></span>  
  
3.  <span data-ttu-id="a24be-111">En el controlador de eventos <xref:System.Windows.Forms.Control.Click> para Button1, agregue el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a24be-111">In the <xref:System.Windows.Forms.Control.Click> event handler for Button1, add the following code:</span></span>  
  
     <span data-ttu-id="a24be-112">[!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-filtering-my-application-log-output_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a24be-112">[!code-vb[VbVbcnMyApplicationLogFiltering#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/walkthrough-filtering-my-application-log-output_1.vb)]</span></span>  
  
4.  <span data-ttu-id="a24be-113">Ejecute la aplicación en el depurador.</span><span class="sxs-lookup"><span data-stu-id="a24be-113">Run the application in the debugger.</span></span>  
  
5.  <span data-ttu-id="a24be-114">Pulse **Button1**.</span><span class="sxs-lookup"><span data-stu-id="a24be-114">Press **Button1**.</span></span>  
  
     <span data-ttu-id="a24be-115">La aplicación escribe la siguiente información en el archivo de registro y de salida de la depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a24be-115">The application writes the following information to the application's debug output and log file.</span></span>  
  
     `DefaultSource Information: 0 : In Button1_Click`  
  
     `DefaultSource Error: 2 : Error in the application.`  
  
6.  <span data-ttu-id="a24be-116">Cierre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a24be-116">Close the application.</span></span>  
  
     <span data-ttu-id="a24be-117">Para obtener información sobre cómo ver la ventana de salida de la depuración de la aplicación, vea [Resultados (Ventana)](/visualstudio/ide/reference/output-window).</span><span class="sxs-lookup"><span data-stu-id="a24be-117">For information on how to view the application's debug output window, see [Output Window](/visualstudio/ide/reference/output-window).</span></span> <span data-ttu-id="a24be-118">Para obtener información sobre la ubicación del archivo de registro de la aplicación, vea [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información (Visual Basic)](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="a24be-118">For information on the location of the application's log file, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a24be-119">De manera predeterminada, la aplicación vacía el resultado del archivo de registro cuando la aplicación se cierra.</span><span class="sxs-lookup"><span data-stu-id="a24be-119">By default, the application flushes the log-file output when the application closes.</span></span>  
  
     <span data-ttu-id="a24be-120">En el ejemplo anterior, la segunda llamada al método <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> y la llamada al método <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> producen una salida del registro, mientras que la primera y la última llamada al método `WriteEntry` no lo hacen.</span><span class="sxs-lookup"><span data-stu-id="a24be-120">In the example above, the second call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A> method and the call to the <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A> method produces log output, while the first and last calls to the `WriteEntry` method do not.</span></span> <span data-ttu-id="a24be-121">Esto se debe a que los niveles de gravedad de `WriteEntry` y `WriteException` son "Information" y "Error", que permite el filtrado de registro predeterminado del objeto `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="a24be-121">This is because the severity levels of `WriteEntry` and `WriteException` are "Information" and "Error", both of which are allowed by the `My.Application.Log` object's default log filtering.</span></span> <span data-ttu-id="a24be-122">En cambio, los eventos con niveles de gravedad "Start" y "Stop" no pueden generar el resultado del registro.</span><span class="sxs-lookup"><span data-stu-id="a24be-122">However, events with "Start" and "Stop" severity levels are prevented from producing log output.</span></span>  
  
## <a name="filtering-for-all-myapplicationlog-listeners"></a><span data-ttu-id="a24be-123">Filtrado para todos los agentes de escucha de My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="a24be-123">Filtering for All My.Application.Log Listeners</span></span>  
 <span data-ttu-id="a24be-124">El objeto `My.Application.Log` usa un objeto <xref:System.Diagnostics.SourceSwitch> denominado `DefaultSwitch` para controlar qué mensajes pasa de los métodos `WriteEntry` y `WriteException` a los agentes de escucha de registro.</span><span class="sxs-lookup"><span data-stu-id="a24be-124">The `My.Application.Log` object uses a <xref:System.Diagnostics.SourceSwitch> named `DefaultSwitch` to control which messages it passes from the `WriteEntry` and `WriteException` methods to the log listeners.</span></span> <span data-ttu-id="a24be-125">Puede configurar `DefaultSwitch` en el archivo de configuración de la aplicación estableciendo su valor en uno de los valores de enumeración <xref:System.Diagnostics.SourceLevels>.</span><span class="sxs-lookup"><span data-stu-id="a24be-125">You can configure `DefaultSwitch` in the application's configuration file by setting its value to one of the <xref:System.Diagnostics.SourceLevels> enumeration values.</span></span> <span data-ttu-id="a24be-126">De manera predeterminada, su valor es "Information".</span><span class="sxs-lookup"><span data-stu-id="a24be-126">By default, its value is "Information".</span></span>  
  
 <span data-ttu-id="a24be-127">En esta tabla se muestra el nivel de gravedad necesario para que el registro escriba un mensaje a los agentes de escucha, con un valor `DefaultSwitch` determinado.</span><span class="sxs-lookup"><span data-stu-id="a24be-127">This table shows the severity level required for Log to write a message to the listeners, given a particular `DefaultSwitch` setting.</span></span>  
  
|<span data-ttu-id="a24be-128">Valor DefaultSwitch</span><span class="sxs-lookup"><span data-stu-id="a24be-128">DefaultSwitch Value</span></span>|<span data-ttu-id="a24be-129">Gravedad del mensaje que se necesita para el resultado</span><span class="sxs-lookup"><span data-stu-id="a24be-129">Message severity required for output</span></span>|  
|---|---| 
|`Critical`|`Critical`|  
|`Error`|<span data-ttu-id="a24be-130">`Critical` o `Error`</span><span class="sxs-lookup"><span data-stu-id="a24be-130">`Critical` or `Error`</span></span>|  
|`Warning`|<span data-ttu-id="a24be-131">`Critical`, `Error` o `Warning`</span><span class="sxs-lookup"><span data-stu-id="a24be-131">`Critical`, `Error`, or `Warning`</span></span>|  
|`Information`|<span data-ttu-id="a24be-132">`Critical`, `Error`, `Warning` o `Information`</span><span class="sxs-lookup"><span data-stu-id="a24be-132">`Critical`, `Error`, `Warning`, or `Information`</span></span>|  
|`Verbose`|<span data-ttu-id="a24be-133">`Critical`, `Error`, `Warning`, `Information` o `Verbose`</span><span class="sxs-lookup"><span data-stu-id="a24be-133">`Critical`, `Error`, `Warning`, `Information`, or `Verbose`</span></span>|  
|`ActivityTracing`|<span data-ttu-id="a24be-134">`Start`, `Stop`, `Suspend`, `Resume` o `Transfer`</span><span class="sxs-lookup"><span data-stu-id="a24be-134">`Start`, `Stop`, `Suspend`, `Resume`, or `Transfer`</span></span>|  
|`All`|<span data-ttu-id="a24be-135">Se permiten todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a24be-135">All messages are allowed.</span></span>|  
|`Off`|<span data-ttu-id="a24be-136">Se bloquean todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a24be-136">All messages are blocked.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="a24be-137">Los métodos `WriteEntry` y `WriteException` tienen una sobrecarga que no especifica un nivel de gravedad.</span><span class="sxs-lookup"><span data-stu-id="a24be-137">The `WriteEntry` and `WriteException` methods each have an overload that does not specify a severity level.</span></span> <span data-ttu-id="a24be-138">El nivel de gravedad implícito para la sobrecarga `WriteEntry` es "Information" y el nivel de gravedad implícito para la sobrecarga `WriteException` es "Error".</span><span class="sxs-lookup"><span data-stu-id="a24be-138">The implicit severity level for the `WriteEntry` overload is "Information", and the implicit severity level for the `WriteException` overload is "Error".</span></span>  
  
 <span data-ttu-id="a24be-139">En esta tabla se explica el resultado del registro que se muestra en el ejemplo anterior: con el valor `DefaultSwitch` predeterminado de "Information", solo la segunda llamada al método `WriteEntry` y la llamada al método `WriteException` generan un resultado del registro.</span><span class="sxs-lookup"><span data-stu-id="a24be-139">This table explains the log output shown in the previous example: with the default `DefaultSwitch` setting of "Information", only the second call to the `WriteEntry` method and the call to the `WriteException` method produce log output.</span></span>  
  
#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="a24be-140">Para registrar solo los eventos de seguimiento de la actividad</span><span class="sxs-lookup"><span data-stu-id="a24be-140">To log only activity tracing events</span></span>  
  
1.  <span data-ttu-id="a24be-141">Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a24be-141">Right-click app.config in the **Solution Explorer** and select **Open**.</span></span>  
  
     <span data-ttu-id="a24be-142">O bien</span><span class="sxs-lookup"><span data-stu-id="a24be-142">-or-</span></span>  
  
     <span data-ttu-id="a24be-143">Si no hay ningún archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="a24be-143">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="a24be-144">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a24be-144">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="a24be-145">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="a24be-145">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="a24be-146">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a24be-146">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="a24be-147">Busque la sección `<switches>`, en la sección `<system.diagnostics>`, que se encuentra en la sección de nivel superior `<configuration>`.</span><span class="sxs-lookup"><span data-stu-id="a24be-147">Locate the `<switches>` section, which is in the `<system.diagnostics>` section, which is in the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="a24be-148">Busque el elemento que agrega `DefaultSwitch` a la colección de modificadores.</span><span class="sxs-lookup"><span data-stu-id="a24be-148">Find the element that adds `DefaultSwitch` to the collection of switches.</span></span> <span data-ttu-id="a24be-149">Este elemento debe ser similar a este:</span><span class="sxs-lookup"><span data-stu-id="a24be-149">It should look similar to this element:</span></span>  
  
     `<add name="DefaultSwitch" value="Information" />`  
  
4.  <span data-ttu-id="a24be-150">Cambie el valor del atributo `value` a "ActivityTracing".</span><span class="sxs-lookup"><span data-stu-id="a24be-150">Change the value of the `value` attribute to "ActivityTracing".</span></span>  
  
5.  <span data-ttu-id="a24be-151">El contenido del archivo app.config debe ser similar al código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="a24be-151">The content of the app.config file should be similar to the following XML:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="ActivityTracing" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
6.  <span data-ttu-id="a24be-152">Ejecute la aplicación en el depurador.</span><span class="sxs-lookup"><span data-stu-id="a24be-152">Run the application in the debugger.</span></span>  
  
7.  <span data-ttu-id="a24be-153">Pulse **Button1**.</span><span class="sxs-lookup"><span data-stu-id="a24be-153">Press **Button1**.</span></span>  
  
     <span data-ttu-id="a24be-154">La aplicación escribe la siguiente información en el archivo de registro y de salida de la depuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="a24be-154">The application writes the following information to the application's debug output and log file:</span></span>  
  
     `DefaultSource Start: 4 : Entering Button1_Click`  
  
     `DefaultSource Stop: 5 : Leaving Button1_Click`  
  
8.  <span data-ttu-id="a24be-155">Cierre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a24be-155">Close the application.</span></span>  
  
9. <span data-ttu-id="a24be-156">Cambie el valor del atributo `value` de nuevo a "Information".</span><span class="sxs-lookup"><span data-stu-id="a24be-156">Change the value of the `value` attribute back to "Information".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a24be-157">La configuración del modificador `DefaultSwitch` solo controla `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="a24be-157">The `DefaultSwitch` switch setting controls only `My.Application.Log`.</span></span> <span data-ttu-id="a24be-158">No cambia el comportamiento de las clases [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=fullName> y <xref:System.Diagnostics.Debug?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="a24be-158">It does not change how the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.Diagnostics.Trace?displayProperty=fullName> and <xref:System.Diagnostics.Debug?displayProperty=fullName> classes behave.</span></span>  
  
## <a name="individual-filtering-for-myapplicationlog-listeners"></a><span data-ttu-id="a24be-159">Filtrado individual para los agentes de escucha de My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="a24be-159">Individual Filtering For My.Application.Log Listeners</span></span>  
 <span data-ttu-id="a24be-160">En el ejemplo anterior se muestra cómo cambiar el filtrado para todos los resultados de `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="a24be-160">The previous example shows how to change the filtering for all `My.Application.Log` output.</span></span> <span data-ttu-id="a24be-161">En este ejemplo se muestra cómo filtrar un agente de escucha de registro individual.</span><span class="sxs-lookup"><span data-stu-id="a24be-161">This example demonstrates how to filter an individual log listener.</span></span> <span data-ttu-id="a24be-162">De manera predeterminada, una aplicación tiene dos agentes de escucha que escriben en el archivo de registro y de salida de la depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a24be-162">By default, an application has two listeners that write to the application's debug output and the log file.</span></span>  
  
 <span data-ttu-id="a24be-163">El archivo de configuración controla el comportamiento de los agentes de escucha de registro permitiendo que cada uno tenga un filtro, que es similar a un modificador para `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="a24be-163">The configuration file controls the behavior of the log listeners by allowing each one to have a filter, which is similar to a switch for `My.Application.Log`.</span></span> <span data-ttu-id="a24be-164">Un agente de escucha de registro generará un mensaje solo si la gravedad de este se permite por el filtro del agente de escucha de registro y del `DefaultSwitch` del registro.</span><span class="sxs-lookup"><span data-stu-id="a24be-164">A log listener will output a message only if the message's severity is allowed by both the log's `DefaultSwitch` and the log listener's filter.</span></span>  
  
 <span data-ttu-id="a24be-165">En este ejemplo se muestra cómo configurar el filtrado para un nuevo agente de escucha de depuración y agregarlo al objeto `Log`.</span><span class="sxs-lookup"><span data-stu-id="a24be-165">This example demonstrates how to configure filtering for a new debug listener and add it to the `Log` object.</span></span> <span data-ttu-id="a24be-166">El agente de escucha de depuración predeterminado debe quitarse del objeto `Log`, por lo que es evidente que los mensajes de depuración provienen del nuevo agente de escucha de depuración.</span><span class="sxs-lookup"><span data-stu-id="a24be-166">The default debug listener should be removed from the `Log` object, so it is clear that the debug messages come from the new debug listener.</span></span>  
  
#### <a name="to-log-only-activity-tracing-events"></a><span data-ttu-id="a24be-167">Para registrar solo los eventos de seguimiento de la actividad</span><span class="sxs-lookup"><span data-stu-id="a24be-167">To log only activity-tracing events</span></span>  
  
1.  <span data-ttu-id="a24be-168">Haga clic con el botón derecho en app.config en el **Explorador de soluciones** y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a24be-168">Right-click app.config in the **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="a24be-169">O bien</span><span class="sxs-lookup"><span data-stu-id="a24be-169">-or-</span></span>  
  
     <span data-ttu-id="a24be-170">Si no hay ningún archivo app.config:</span><span class="sxs-lookup"><span data-stu-id="a24be-170">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="a24be-171">En el menú **Proyecto** , elija **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a24be-171">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="a24be-172">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **Archivo de configuración de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="a24be-172">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="a24be-173">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a24be-173">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="a24be-174">Haga clic con el botón derecho en app.config en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="a24be-174">Right-click app.config in **Solution Explorer**.</span></span> <span data-ttu-id="a24be-175">Pulse **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a24be-175">Choose **Open**.</span></span>  
  
3.  <span data-ttu-id="a24be-176">Busque la sección `<listeners>`, en la sección `<source>` con el atributo `name` "DefaultSource", que está en la sección `<sources>`.</span><span class="sxs-lookup"><span data-stu-id="a24be-176">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", which is under the `<sources>` section.</span></span> <span data-ttu-id="a24be-177">La sección `<sources>` está en la sección `<system.diagnostics>`, en la sección de nivel superior `<configuration>`.</span><span class="sxs-lookup"><span data-stu-id="a24be-177">The `<sources>` section is under the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
4.  <span data-ttu-id="a24be-178">Agregue este elemento a la sección `<listeners>`:</span><span class="sxs-lookup"><span data-stu-id="a24be-178">Add this element to the `<listeners>` section:</span></span>  
  
    ```xml  
    <!-- Remove the default debug listener. -->  
    <remove name="Default"/>  
    <!-- Add a filterable debug listener. -->  
    <add name="NewDefault"/>  
    ```  
  
5.  <span data-ttu-id="a24be-179">Busque la sección `<sharedListeners>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="a24be-179">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
6.  <span data-ttu-id="a24be-180">Agregue este elemento a dicha sección `<sharedListeners>` :</span><span class="sxs-lookup"><span data-stu-id="a24be-180">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="NewDefault"   
         type="System.Diagnostics.DefaultTraceListener,   
               System, Version=2.0.0.0, Culture=neutral,   
               PublicKeyToken=b77a5c561934e089,   
               processorArchitecture=MSIL">  
        <filter type="System.Diagnostics.EventTypeFilter"   
                initializeData="Error" />  
    </add>  
    ```  
  
     <span data-ttu-id="a24be-181">El filtro <xref:System.Diagnostics.EventTypeFilter> toma uno de los valores de enumeración <xref:System.Diagnostics.SourceLevels> como su atributo `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="a24be-181">The <xref:System.Diagnostics.EventTypeFilter> filter takes one of the <xref:System.Diagnostics.SourceLevels> enumeration values as its `initializeData` attribute.</span></span>  
  
7.  <span data-ttu-id="a24be-182">El contenido del archivo app.config debe ser similar al código XML siguiente:</span><span class="sxs-lookup"><span data-stu-id="a24be-182">The content of the app.config file should be similar to the following XML:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.diagnostics>  
        <sources>  
          <!-- This section configures My.Application.Log -->  
          <source name="DefaultSource" switchName="DefaultSwitch">  
            <listeners>  
              <add name="FileLog"/>  
              <!-- Remove the default debug listener. -->  
              <remove name="Default"/>  
              <!-- Add a filterable debug listener. -->  
              <add name="NewDefault"/>  
            </listeners>  
          </source>  
        </sources>  
        <switches>  
          <add name="DefaultSwitch" value="Information" />  
        </switches>  
        <sharedListeners>  
          <add name="FileLog"  
               type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
                     Microsoft.VisualBasic, Version=8.0.0.0,   
                     Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a,   
                     processorArchitecture=MSIL"   
               initializeData="FileLogWriter"/>  
          <add name="NewDefault"   
               type="System.Diagnostics.DefaultTraceListener,   
                     System, Version=2.0.0.0, Culture=neutral,   
                     PublicKeyToken=b77a5c561934e089,   
                     processorArchitecture=MSIL">  
            <filter type="System.Diagnostics.EventTypeFilter"   
                    initializeData="Error" />  
          </add>  
        </sharedListeners>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
8.  <span data-ttu-id="a24be-183">Ejecute la aplicación en el depurador.</span><span class="sxs-lookup"><span data-stu-id="a24be-183">Run the application in the debugger.</span></span>  
  
9. <span data-ttu-id="a24be-184">Pulse **Button1**.</span><span class="sxs-lookup"><span data-stu-id="a24be-184">Press **Button1**.</span></span>  
  
     <span data-ttu-id="a24be-185">La aplicación escribe la siguiente información en el archivo de registro de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="a24be-185">The application writes the following information to the application's log file:</span></span>  
  
     `Default Information: 0 : In Button1_Click`  
  
     `Default Error: 2 : Error in the application.`  
  
     <span data-ttu-id="a24be-186">La aplicación escribe menos información en el resultado de depuración de la aplicación porque el filtrado es más restrictivo.</span><span class="sxs-lookup"><span data-stu-id="a24be-186">The application writes less information to the application's debug output because of the more restrictive filtering.</span></span>  
  
     `Default Error   2   Error`  
  
10. <span data-ttu-id="a24be-187">Cierre la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a24be-187">Close the application.</span></span>  
  
 <span data-ttu-id="a24be-188">Para obtener más información sobre cómo cambiar la configuración del registro después de la implementación, vea [Trabajar con registros de aplicaciones en Visual Basic](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="a24be-188">For more information about changing log settings after deployment, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24be-189">Vea también</span><span class="sxs-lookup"><span data-stu-id="a24be-189">See Also</span></span>  
 <span data-ttu-id="a24be-190">[Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="a24be-190">[Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="a24be-191">[Tutorial: Cambiar el lugar donde My.Application.Log escribe información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="a24be-191">[Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="a24be-192">[Tutorial: Crear agentes de escucha de registro personalizados](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md) </span><span class="sxs-lookup"><span data-stu-id="a24be-192">[Walkthrough: Creating Custom Log Listeners](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md) </span></span>  
 <span data-ttu-id="a24be-193">[Cómo: Escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a24be-193">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 <span data-ttu-id="a24be-194">[Modificadores de seguimiento](../../../../framework/debug-trace-profile/trace-switches.md) </span><span class="sxs-lookup"><span data-stu-id="a24be-194">[Trace Switches](../../../../framework/debug-trace-profile/trace-switches.md) </span></span>  
 [<span data-ttu-id="a24be-195">Registrar información de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a24be-195">Logging Information from the Application</span></span>](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)

