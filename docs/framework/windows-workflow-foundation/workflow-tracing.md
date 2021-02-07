---
description: 'Más información acerca de: seguimiento de flujo de trabajo'
title: Traza del flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: 6d976cce1310a072f8d1c98db138696921b382c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754854"
---
# <a name="workflow-tracing"></a><span data-ttu-id="02be3-103">Traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="02be3-103">Workflow Tracing</span></span>

<span data-ttu-id="02be3-104">La traza del flujo de trabajo ofrece una forma de capturar la información de diagnóstico con los agentes de escucha de seguimiento de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="02be3-104">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="02be3-105">Se puede habilitar la traza si se detecta un problema con la aplicación y se deshabilita de nuevo una vez resuelto el problema.</span><span class="sxs-lookup"><span data-stu-id="02be3-105">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="02be3-106">Hay dos maneras de poder habilitar la traza de depuración para los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02be3-106">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="02be3-107">Puede configurarlo con el visor del seguimiento de eventos o puede usar <xref:System.Diagnostics> para enviar los eventos de seguimiento a un archivo.</span><span class="sxs-lookup"><span data-stu-id="02be3-107">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="02be3-108">Habilitar la traza de depuración en ETW</span><span class="sxs-lookup"><span data-stu-id="02be3-108">Enabling Debug Tracing in ETW</span></span>  

 <span data-ttu-id="02be3-109">Para habilitar la traza mediante ETW, habilite el canal de depuración en el visor de eventos:</span><span class="sxs-lookup"><span data-stu-id="02be3-109">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1. <span data-ttu-id="02be3-110">Desplácese hasta el nodo de registros analíticos y de depuración en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="02be3-110">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2. <span data-ttu-id="02be3-111">En la vista de árbol de Visor de eventos, vaya a **visor de eventos->registros de aplicaciones y servicios->servidor de aplicaciones de Microsoft >Windows->: aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="02be3-111">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="02be3-112">Haga clic con el botón derecho en **servidor de aplicaciones-aplicaciones** y seleccione **Ver->Mostrar registros analíticos y de depuración**.</span><span class="sxs-lookup"><span data-stu-id="02be3-112">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="02be3-113">Haga clic con el botón secundario en **depurar** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="02be3-113">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3. <span data-ttu-id="02be3-114">Cuando un flujo de trabajo ejecuta la depuración y los seguimientos se emiten en el canal de depuración de ETW, se pueden ver en el Visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="02be3-114">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="02be3-115">Vaya a **visor de eventos->registros de aplicaciones y servicios->servidor de aplicaciones de Microsoft >Windows->: aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="02be3-115">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="02be3-116">Haga clic con el botón secundario en **depurar** y seleccione **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="02be3-116">Right-click **Debug** and select **Refresh**.</span></span>  
  
4. <span data-ttu-id="02be3-117">El tamaño predeterminado del búfer de traza analítica es solo de 4 kilobytes (KB); se recomienda aumentar el tamaño a 32 KB.</span><span class="sxs-lookup"><span data-stu-id="02be3-117">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="02be3-118">Para ello, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="02be3-118">To do this, perform the following steps.</span></span>  
  
    1. <span data-ttu-id="02be3-119">Ejecute el siguiente comando en el directorio de .NET Framework actual (por ejemplo, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="02be3-119">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
    2. <span data-ttu-id="02be3-120">Cambie el \<bufferSize> valor del archivo Windows. ApplicationServer. Applications. Man a 32.</span><span class="sxs-lookup"><span data-stu-id="02be3-120">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3. <span data-ttu-id="02be3-121">Ejecute el siguiente comando en el directorio de .NET Framework actual (por ejemplo, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="02be3-121">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
> [!NOTE]
> <span data-ttu-id="02be3-122">Si usa el perfil de cliente de .NET Framework 4, primero debe registrar el manifiesto ETW ejecutando el siguiente comando desde el directorio .NET Framework 4: `ServiceModelReg.exe –i –c:etw`</span><span class="sxs-lookup"><span data-stu-id="02be3-122">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory: `ServiceModelReg.exe –i –c:etw`</span></span>  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="02be3-123">Habilitar el seguimiento de depuración con System.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="02be3-123">Enabling Debug Tracing using System.Diagnostics</span></span>  

 <span data-ttu-id="02be3-124">Se pueden configurar estos agentes de escucha en el archivo App.config de la aplicación de flujo de trabajo o Web.config para un servicio del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02be3-124">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="02be3-125">En este ejemplo, <xref:System.Diagnostics.TextWriterTraceListener> se configura un para guardar información de seguimiento en el archivo de MyTraceLog.txt en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="02be3-125">In this example, a <xref:System.Diagnostics.TextWriterTraceListener> is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02be3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="02be3-126">See also</span></span>

- <span data-ttu-id="02be3-127">[Supervisión de Windows Server App fabric](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="02be3-127">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="02be3-128">[Supervisión de aplicaciones con App fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="02be3-128">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
