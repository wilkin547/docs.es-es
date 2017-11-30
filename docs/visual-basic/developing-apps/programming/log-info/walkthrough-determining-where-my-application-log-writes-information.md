---
title: "Determinar el lugar en el que My.Application.Log escribe la información (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Log object, output location
- output, application log location
- My.Application.Log object, outpout location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4df7a80907b29a5eea79992f46c46603cbe2cc81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="fad3e-102">Tutorial: Determinar el lugar en el que My.Application.Log escribe la información (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fad3e-102">Walkthrough: Determining Where My.Application.Log Writes Information (Visual Basic)</span></span>
<span data-ttu-id="fad3e-103">El objeto `My.Application.Log` puede escribir información en varios agentes de escucha de registro.</span><span class="sxs-lookup"><span data-stu-id="fad3e-103">The `My.Application.Log` object can write information to several log listeners.</span></span> <span data-ttu-id="fad3e-104">Los agentes de escucha de registro se configuran por archivo de configuración del equipo y puede reemplazarlos una archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad3e-104">The log listeners are configured by the computer's configuration file and can be overridden by an application's configuration file.</span></span> <span data-ttu-id="fad3e-105">En este tema se describe la configuración predeterminada y cómo determinar la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad3e-105">This topic describes the default settings and how to determine the settings for your application.</span></span>  
  
 <span data-ttu-id="fad3e-106">Para obtener más información sobre las ubicaciones de salida predeterminadas, vea [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="fad3e-106">For more information about the default output locations, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
### <a name="to-determine-the-listeners-for-myapplicationlog"></a><span data-ttu-id="fad3e-107">Para determinar los agentes de escucha de My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="fad3e-107">To determine the listeners for My.Application.Log</span></span>  
  
1.  <span data-ttu-id="fad3e-108">Busque el archivo de configuración del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fad3e-108">Locate the assembly's configuration file.</span></span> <span data-ttu-id="fad3e-109">Si está desarrollando el ensamblado, puede acceder a app.config en [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] desde el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="fad3e-109">If you are developing the assembly, you can access the app.config in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] from the **Solution Explorer**.</span></span> <span data-ttu-id="fad3e-110">De lo contrario, el nombre del archivo de configuración es el nombre del ensamblado con ".config" anexado, que se encuentra en el mismo directorio que el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fad3e-110">Otherwise, the configuration file name is the assembly's name appended with ".config", and it is located in the same directory as the assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fad3e-111">No todos los ensamblados tienen un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="fad3e-111">Not every assembly has a configuration file.</span></span>  
  
     <span data-ttu-id="fad3e-112">El archivo de configuración es un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="fad3e-112">The configuration file is an XML file.</span></span>  
  
2.  <span data-ttu-id="fad3e-113">Busque la sección `<listeners>` , en la sección `<source>` con el atributo `name` el "DefaultSource", ubicada en la sección `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="fad3e-113">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="fad3e-114">La sección `<sources>` se encuentra en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="fad3e-114">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
     <span data-ttu-id="fad3e-115">Si estas secciones no existen, el archivo de configuración del equipo puede configurar los agentes de escucha de registro `My.Application.Log` .</span><span class="sxs-lookup"><span data-stu-id="fad3e-115">If these sections do not exist, then the computer's configuration file may configure the `My.Application.Log` log listeners.</span></span> <span data-ttu-id="fad3e-116">En los pasos siguientes se describe cómo determinar qué define el archivo de configuración del equipo:</span><span class="sxs-lookup"><span data-stu-id="fad3e-116">The following steps describe how to determine what the computer configuration file defines:</span></span>  
  
    1.  <span data-ttu-id="fad3e-117">Busque el archivo machine.config del equipo.</span><span class="sxs-lookup"><span data-stu-id="fad3e-117">Locate the computer's machine.config file.</span></span> <span data-ttu-id="fad3e-118">Normalmente, se encuentra en el directorio *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* , donde `SystemRoot` es el directorio del sistema operativo y `frameworkVersion` es la versión de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fad3e-118">Typically, it is located in the *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* directory, where `SystemRoot` is the operating system directory, and `frameworkVersion` is the version of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
         <span data-ttu-id="fad3e-119">La configuración de machine.config puede reemplazarse por un archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fad3e-119">The settings in machine.config can be overridden by an application's configuration file.</span></span>  
  
         <span data-ttu-id="fad3e-120">Si los elementos opcionales que se enumeran a continuación no existen, puede crearlos.</span><span class="sxs-lookup"><span data-stu-id="fad3e-120">If the optional elements listed below do not exist, you can create them.</span></span>  
  
    2.  <span data-ttu-id="fad3e-121">Busque la sección `<listeners>` , en la sección `<source>` con el atributo `name` el "DefaultSource", en la sección `<sources>` , en la sección `<system.diagnostics>` , en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="fad3e-121">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
         <span data-ttu-id="fad3e-122">Si estas secciones no existen, `My.Application.Log` solo tiene los agentes de escucha de registro predeterminados.</span><span class="sxs-lookup"><span data-stu-id="fad3e-122">If these sections do not exist, then the `My.Application.Log` has only the default log listeners.</span></span>  
  
3.  <span data-ttu-id="fad3e-123">Busque los elementos <`add>` en la sección <`listeners>`.</span><span class="sxs-lookup"><span data-stu-id="fad3e-123">Locate the <`add>` elements in the <`listeners>` section.</span></span>  
  
     <span data-ttu-id="fad3e-124">Estos elementos agregan los agentes de escucha de registro con nombre al origen `My.Application.Log` .</span><span class="sxs-lookup"><span data-stu-id="fad3e-124">These elements add the named log listeners to `My.Application.Log` source.</span></span>  
  
4.  <span data-ttu-id="fad3e-125">Busque los elementos `<add>` con los nombres de los agentes de escucha de registro en la sección `<sharedListeners>` , en la `<system.diagnostics>` sección, en la sección de nivel superior `<configuration>` .</span><span class="sxs-lookup"><span data-stu-id="fad3e-125">Locate the `<add>` elements with the names of the log listeners in the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="fad3e-126">Para muchos tipos de agentes de escucha compartidos, los datos de inicialización del agente de escucha incluyen una descripción de la ubicación a la que el agente de escucha dirige los datos:</span><span class="sxs-lookup"><span data-stu-id="fad3e-126">For many types of shared listeners, the listener's initialization data includes a description of where the listener directs the data:</span></span>  
  
    -   <span data-ttu-id="fad3e-127">Un agente de escucha <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> escribe en un registro de archivos, como se describe en la introducción.</span><span class="sxs-lookup"><span data-stu-id="fad3e-127">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=nameWithType> listener writes to a file log, as described in the introduction.</span></span>  
  
    -   <span data-ttu-id="fad3e-128">Un agente de escucha <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> escribe información en el registro de eventos del equipo especificado por el parámetro `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="fad3e-128">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType> listener writes information to the computer event log specified by the `initializeData` parameter.</span></span> <span data-ttu-id="fad3e-129">Para ver un registro de eventos, puede usar el **Explorador de servidores** o el **Visor de eventos de Windows**.</span><span class="sxs-lookup"><span data-stu-id="fad3e-129">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="fad3e-130">Para obtener más información, consulta [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span><span class="sxs-lookup"><span data-stu-id="fad3e-130">For more information, see [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span></span>  
  
    -   <span data-ttu-id="fad3e-131">Los agentes de escucha <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> y <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> escriben en el archivo especificado en el parámetro `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="fad3e-131">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> listeners write to the file specified in the `initializeData` parameter.</span></span>  
  
    -   <span data-ttu-id="fad3e-132">Un agente de escucha <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> escribe en la consola de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="fad3e-132">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType> listener writes to the command-line console.</span></span>  
  
    -   <span data-ttu-id="fad3e-133">Para obtener información sobre dónde escriben información otros tipos de agentes de escucha de registro, consulte la documentación de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="fad3e-133">For information about where other types of log listeners write information, consult that type's documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad3e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="fad3e-134">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.DelimitedListTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics>  
 [<span data-ttu-id="fad3e-135">Trabajar con registros de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="fad3e-135">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [<span data-ttu-id="fad3e-136">Registrar excepciones</span><span class="sxs-lookup"><span data-stu-id="fad3e-136">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)  
 [<span data-ttu-id="fad3e-137">Escribir mensajes de registro</span><span class="sxs-lookup"><span data-stu-id="fad3e-137">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)  
 [<span data-ttu-id="fad3e-138">Tutorial: Cambiar el lugar donde My.Application.Log escribe información</span><span class="sxs-lookup"><span data-stu-id="fad3e-138">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)  
 [<span data-ttu-id="fad3e-139">Eventos ETW en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fad3e-139">ETW Events in the .NET Framework</span></span>](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299)  
 [<span data-ttu-id="fad3e-140">Solución de problemas: Agentes de escucha de registro</span><span class="sxs-lookup"><span data-stu-id="fad3e-140">Troubleshooting: Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
