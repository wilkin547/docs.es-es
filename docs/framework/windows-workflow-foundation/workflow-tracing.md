---
title: Traza del flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: 8dba5706ee37f243c15befb483ab4f9f2a8e3b9c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655719"
---
# <a name="workflow-tracing"></a><span data-ttu-id="4f26a-102">Traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4f26a-102">Workflow Tracing</span></span>
<span data-ttu-id="4f26a-103">La traza del flujo de trabajo ofrece una forma de capturar la información de diagnóstico con los agentes de escucha de seguimiento de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f26a-103">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="4f26a-104">Se puede habilitar la traza si se detecta un problema con la aplicación y se deshabilita de nuevo una vez resuelto el problema.</span><span class="sxs-lookup"><span data-stu-id="4f26a-104">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="4f26a-105">Hay dos maneras de poder habilitar la traza de depuración para los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f26a-105">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="4f26a-106">Puede configurarlo con el visor del seguimiento de eventos o puede usar <xref:System.Diagnostics> para enviar los eventos de seguimiento a un archivo.</span><span class="sxs-lookup"><span data-stu-id="4f26a-106">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="4f26a-107">Habilitar la traza de depuración en ETW</span><span class="sxs-lookup"><span data-stu-id="4f26a-107">Enabling Debug Tracing in ETW</span></span>  
 <span data-ttu-id="4f26a-108">Para habilitar la traza mediante ETW, habilite el canal de depuración en el visor de eventos:</span><span class="sxs-lookup"><span data-stu-id="4f26a-108">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1. <span data-ttu-id="4f26a-109">Desplácese hasta el nodo de registros analíticos y de depuración en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="4f26a-109">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2. <span data-ttu-id="4f26a-110">En la vista de árbol en el Visor de eventos, vaya a **aplicaciones -> el Visor de eventos y registros de servicios -> Microsoft -> Windows -> servidor de aplicaciones-aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="4f26a-110">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="4f26a-111">Haga clic en **aplicaciones de servidor-aplicaciones** y seleccione **Ver -> Mostrar registros analíticos y depuración**.</span><span class="sxs-lookup"><span data-stu-id="4f26a-111">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="4f26a-112">Haga clic en **depurar** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="4f26a-112">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3. <span data-ttu-id="4f26a-113">Cuando un flujo de trabajo ejecuta la depuración y los seguimientos se emiten en el canal de depuración de ETW, se pueden ver en el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="4f26a-113">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="4f26a-114">Vaya a **aplicaciones -> el Visor de eventos y registros de servicios -> Microsoft -> Windows -> servidor de aplicaciones-aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="4f26a-114">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="4f26a-115">Haga clic en **depurar** y seleccione **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="4f26a-115">Right-click **Debug** and select **Refresh**.</span></span>  
  
4. <span data-ttu-id="4f26a-116">El tamaño predeterminado del búfer de traza analítica es solo de 4 kilobytes (KB); se recomienda aumentar el tamaño a 32 KB.</span><span class="sxs-lookup"><span data-stu-id="4f26a-116">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="4f26a-117">Para ello, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="4f26a-117">To do this, perform the following steps.</span></span>  
  
    1. <span data-ttu-id="4f26a-118">Ejecute el siguiente comando en el directorio de .NET Framework actual (por ejemplo, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="4f26a-118">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
    2. <span data-ttu-id="4f26a-119">Cambiar el \<bufferSize > valor en el archivo Windows.ApplicationServer.Applications.man a 32.</span><span class="sxs-lookup"><span data-stu-id="4f26a-119">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3. <span data-ttu-id="4f26a-120">Ejecute el siguiente comando en el directorio de .NET Framework actual (por ejemplo, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="4f26a-120">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f26a-121">Si usa .NET Framework 4 Client Profile, primero debe registrar el manifiesto ETW ejecutando el siguiente comando desde el directorio de .NET Framework 4: `ServiceModelReg.exe –i –c:etw`</span><span class="sxs-lookup"><span data-stu-id="4f26a-121">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory: `ServiceModelReg.exe –i –c:etw`</span></span>  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="4f26a-122">Habilitar el seguimiento de depuración con System.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="4f26a-122">Enabling Debug Tracing using System.Diagnostics</span></span>  
 <span data-ttu-id="4f26a-123">Se pueden configurar estos agentes de escucha en el archivo App.config de la aplicación de flujo de trabajo o Web.config para un servicio del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f26a-123">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="4f26a-124">En este ejemplo, un [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424) está configurado para guardar información de seguimiento en el archivo MyTraceLog.txt del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="4f26a-124">In this example, a [TextWriterTraceListener](https://go.microsoft.com/fwlink/?LinkId=165424) is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f26a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f26a-125">See also</span></span>

- [<span data-ttu-id="4f26a-126">Supervisión de Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="4f26a-126">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="4f26a-127">Supervisión de aplicaciones con App Fabric</span><span class="sxs-lookup"><span data-stu-id="4f26a-127">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
