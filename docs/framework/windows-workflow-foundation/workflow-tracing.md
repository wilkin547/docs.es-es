---
title: Traza del flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: 972520aae7a2af950ed1ba079769861173784148
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837511"
---
# <a name="workflow-tracing"></a>Traza del flujo de trabajo
La traza del flujo de trabajo ofrece una forma de capturar la información de diagnóstico con los agentes de escucha de seguimiento de .NET Framework. Se puede habilitar la traza si se detecta un problema con la aplicación y se deshabilita de nuevo una vez resuelto el problema. Hay dos maneras de poder habilitar la traza de depuración para los flujos de trabajo. Puede configurarlo con el visor del seguimiento de eventos o puede usar <xref:System.Diagnostics> para enviar los eventos de seguimiento a un archivo.  
  
## <a name="enabling-debug-tracing-in-etw"></a>Habilitar la traza de depuración en ETW  
 Para habilitar la traza mediante ETW, habilite el canal de depuración en el visor de eventos:  
  
1. Desplácese hasta el nodo de registros analíticos y de depuración en el visor de eventos.  
  
2. En la vista de árbol de Visor de eventos, vaya a **visor de eventos-> registros de aplicaciones y servicios-> servidor de aplicaciones de Microsoft > Windows->: aplicaciones**. Haga clic con el botón derecho en **servidor de aplicaciones-aplicaciones** y seleccione **Ver-> Mostrar registros analíticos y de depuración**. Haga clic con el botón secundario en **depurar** y seleccione **Habilitar registro**.  
  
3. Cuando un flujo de trabajo ejecuta la depuración y los seguimientos se emiten en el canal de depuración de ETW, se pueden ver en el Visor de eventos. Vaya a **visor de eventos-> registros de aplicaciones y servicios-> servidor de aplicaciones de Microsoft > Windows->: aplicaciones**. Haga clic con el botón secundario en **depurar** y seleccione **Actualizar**.  
  
4. El tamaño predeterminado del búfer de traza analítica es solo de 4 kilobytes (KB); se recomienda aumentar el tamaño a 32 KB. Para ello, realice los pasos siguientes.  
  
    1. Ejecute el siguiente comando en el directorio de .NET Framework actual (por ejemplo, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2. Cambie el valor de \<bufferSize > en el archivo Windows. ApplicationServer. Applications. Man a 32.  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3. Ejecute el siguiente comando en el directorio de .NET Framework actual (por ejemplo, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
> Si usa el perfil de cliente de .NET Framework 4, primero debe registrar el manifiesto ETW ejecutando el siguiente comando desde el directorio .NET Framework 4: `ServiceModelReg.exe –i –c:etw`  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a>Habilitar el seguimiento de depuración con System.Diagnostics  
 Se pueden configurar estos agentes de escucha en el archivo App.config de la aplicación de flujo de trabajo o Web.config para un servicio del flujo de trabajo. En este ejemplo, se configura un <xref:System.Diagnostics.TextWriterTraceListener> para guardar la información de seguimiento en el archivo MyTraceLog. txt del directorio actual.  
  
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
  
## <a name="see-also"></a>Vea también

- [Supervisión de Windows Server App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Supervisión de aplicaciones con App fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
