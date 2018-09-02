---
title: Configurar seguimiento para un flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 905adcc9-30a0-4918-acd6-563f86db988a
ms.openlocfilehash: ae6b61bf572da1757920b737b03861c891637f51
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43468585"
---
# <a name="configuring-tracking-for-a-workflow"></a>Configurar seguimiento para un flujo de trabajo
Un flujo de trabajo se puede ejecutar de tres maneras:  
  
-   Hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
-   Ejecutado como <xref:System.Activities.WorkflowApplication>  
  
-   Ejecutado directamente utilizando <xref:System.Activities.WorkflowInvoker>  
  
 Dependiendo de la opción de hospedaje de flujo de trabajo, se puede agregar un participante de seguimiento, ya sea a través de código o de un archivo de configuración. En este tema se describe cómo configurar el seguimiento agregando un participante de seguimiento a <xref:System.Activities.WorkflowApplication> y a <xref:System.ServiceModel.Activities.WorkflowServiceHost> y cómo habilitar el seguimiento al utilizar <xref:System.Activities.WorkflowInvoker>.  
  
## <a name="configuring-workflow-application-tracking"></a>Configurar seguimiento de aplicación de flujo de trabajo  
 Un flujo de trabajo se puede ejecutar mediante la clase <xref:System.Activities.WorkflowApplication>. En este tema se muestra cómo configurar el seguimiento de una aplicación de flujo de trabajo de [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] al agregar un participante de seguimiento al host de flujo de trabajo <xref:System.Activities.WorkflowApplication>. En este caso, el flujo de trabajo se ejecuta como una aplicación de flujo de trabajo. Configure una aplicación de flujo de trabajo mediante código (en lugar de utilizar un archivo de configuración), que es un archivo .exe auto-hospedado usando la clase <xref:System.Activities.WorkflowApplication>. El participante de seguimiento se agrega como una extensión a la instancia <xref:System.Activities.WorkflowApplication>. Esto se realiza agregando <xref:System.Activities.Tracking.TrackingParticipant> a la colección de las extensiones para la instancia de WorkflowApplication.  
  
 Para una aplicación de flujo de trabajo, puede agregar la extensión de comportamiento <xref:System.Activities.Tracking.EtwTrackingParticipant> tal y como se muestra en el siguiente código.  
  
```csharp  
LogActivity activity = new LogActivity();  
  
WorkflowApplication instance = new WorkflowApplication(activity);  
EtwTrackingParticipant trackingParticipant =  
    new EtwTrackingParticipant  
{  
  
        TrackingProfile = new TrackingProfile  
           {  
               Name = "SampleTrackingProfile",  
               ActivityDefinitionId = "ProcessOrder",  
               Queries = new WorkflowInstanceQuery  
               {  
                  States = { "*" }  
              }  
          }  
       };  
instance.Extensions.Add(trackingParticipant);  
```  
  
### <a name="configuring-workflow-service-tracking"></a>Configurar el seguimiento de servicio de flujo de trabajo  
 Un flujo de trabajo puede exponerse como un servicio WCF cuando se hospeda en el <xref:System.ServiceModel.Activities.WorkflowServiceHost> host de servicio. <xref:System.ServiceModel.Activities.WorkflowServiceHost> es una implementación especializada de .NET ServiceHost para un servicio basado en flujo de trabajo. En esta sección se explica cómo configurar el seguimiento para un servicio de flujo de trabajo de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] que se ejecuta en <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Se configura mediante un archivo Web.config (para un servicio hospedado en web) o un archivo App.config (para un servicio hospedado en una aplicación independiente, como una aplicación de consola) especificando un comportamiento de servicio o mediante código agregando un comportamiento específico de seguimiento a la colección <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> del host de servicio.  
  
 En el caso de un servicio de host hospedado en <xref:System.ServiceModel.WorkflowServiceHost>, puede agregar <xref:System.Activities.Tracking.EtwTrackingParticipant> mediante el elemento <`behavior`> en un archivo de configuración, tal y como se muestra en el siguiente ejemplo.  
  
```xml  
<behaviors>  
   <serviceBehaviors>  
        <behavior>  
          <etwTracking profileName="Sample Tracking Profile" />  
        </behavior>              
   </serviceBehaviors>  
<behaviors>  
```  
  
 Por otra parte, en el caso de un servicio de flujo de trabajo hospedado en <xref:System.ServiceModel.WorkflowServiceHost>, puede agregar la extensión de comportamiento <xref:System.Activities.Tracking.EtwTrackingParticipant> a través del código. Para agregar un participante de seguimiento personalizado, cree una nueva extensión de comportamiento y agréguela a <xref:System.ServiceModel.ServiceHost> tal y como se muestra en el siguiente código de ejemplo.  
  
> [!NOTE]
>  Si desea ver el código de ejemplo que muestra cómo crear un elemento de comportamiento personalizado que agrega un participante de seguimiento personalizado, consulte el [seguimiento](../../../docs/framework/windows-workflow-foundation/samples/tracking.md) ejemplos.  
  
```  
ServiceHost svcHost = new ServiceHost(typeof(WorkflowService), new   
                                 Uri("http://localhost:8001/Sample"));  
EtwTrackingBehavior trackingBehavior =   
    new EtwTrackingBehavior  
    {  
        ProfileName = "Sample Tracking Profile"  
    };  
svcHost.Description.Behaviors.Add(trackingBehavior);  
svcHost.Open();  
```  
  
 El participante del seguimiento se agrega al host de servicio de flujo de trabajo como una extensión al comportamiento.  
  
 El siguiente código de ejemplo muestra cómo leer un perfil de seguimiento del archivo de configuración.  
  
```  
TrackingProfile GetProfile(string profileName, string displayName)  
        {  
            TrackingProfile trackingProfile = null;  
            TrackingSection trackingSection = (TrackingSection)WebConfigurationManager.GetSection("system.serviceModel/tracking");  
            if (trackingSection == null)   
            {  
                return null;  
            }  
  
            if (profileName == null)   
            {  
                profileName = "";  
            }  
  
            //Find the profile with the specified profile name in the list of profile found in config  
            var match = from p in new List<TrackingProfile>(trackingSection.TrackingProfiles)  
                        where (p.Name == profileName) && ((p.ActivityDefinitionId == displayName) || (p.ActivityDefinitionId == "*"))  
                        select p;  
  
            if (match.Count() == 0)  
            {  
                //return an empty profile  
                trackingProfile = new TrackingProfile()  
                {  
                    ActivityDefinitionId = displayName  
                };  
  
            }  
            else  
            {  
                trackingProfile = match.First();  
            }  
  
            return trackingProfile;  
```  
  
 Este código de ejemplo muestra cómo agregar un perfil de seguimiento a un host del flujo de trabajo.  
  
```  
WorkflowServiceHost workflowServiceHost = serviceHostBase as WorkflowServiceHost;  
if (null != workflowServiceHost)  
{  
              string workflowDisplayName = workflowServiceHost.Activity.DisplayName;  
               TrackingProfile trackingProfile = GetProfile(this.profileName, workflowDisplayName);  
                workflowServiceHost.WorkflowExtensions.Add(()  => new EtwTrackingParticipant  {  
               TrackingProfile = trackingProfile  
                        });  
 }  
```  
  
> [!NOTE]
>  Para obtener más información sobre los perfiles de seguimiento, consulte [perfiles de seguimiento](https://go.microsoft.com/fwlink/?LinkId=201310).  
  
### <a name="configuring-tracking-using-workflowinvoker"></a>Configurar el seguimiento mediante WorkflowInvoker  
 Para configurar el seguimiento para un flujo de trabajo ejecutado utilizando <xref:System.Activities.WorkflowInvoker>, agregue el proveedor del seguimiento como una extensión de una instancia de <xref:System.Activities.WorkflowInvoker>. El ejemplo de código siguiente procede del [seguimiento personalizado](../../../docs/framework/windows-workflow-foundation/samples/custom-tracking.md) ejemplo.  
  
```  
WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());  
invoker.Extensions.Add(customTrackingParticipant);  
invoker.Invoke();  
```  
  
### <a name="viewing-tracking-records-in-event-viewer"></a>Visualizar los registros de seguimiento en el Visor de eventos  
 Hay dos registros del Visor de eventos que resultan de especial interés para ver la ejecución del seguimiento de WF: el registro analítico y el registro de depuración. Residen en el Microsoft&#124;Windows&#124;nodo de servidor de aplicaciones-aplicaciones.  Los registros de esta sección contienen eventos de una única aplicación en lugar de los eventos que afectan a todo el sistema.  
  
 Los eventos de seguimiento de depuración se escriben en el registro de depuración. Para recopilar eventos de seguimiento de depuración de WF en el Visor de eventos, habilite el registro de depuración.  
  
1.  Para abrir el Visor de eventos, haga clic en **iniciar**y, a continuación, haga clic en **ejecutar.** En el cuadro de diálogo Ejecutar, escriba `eventvwr`.  
  
2.  En el cuadro de diálogo Visor de eventos, expanda el **registros de aplicaciones y servicios** nodo.  
  
3.  Expanda el **Microsoft**, **Windows**, y **aplicaciones de servidor-aplicaciones** nodos.  
  
4.  Haga clic en el **depurar** nodo bajo el **aplicaciones de servidor-aplicaciones** nodo y seleccione **Habilitar registro**.  
  
5.  Ejecute la aplicación habilitada para realizar seguimientos con el fin de generar eventos de seguimiento.  
  
6.  Haga clic en el **depurar** nodo y seleccione **actualizar.** Los eventos de seguimiento deben estar visibles en el panel central.  
  
 WF 4 proporciona un participante de seguimiento que escribe registros de seguimiento en una sesión de ETW (Seguimiento de eventos para Windows). El participante de seguimiento de ETW se configura con un perfil de seguimiento para suscribirse a registros de seguimiento.  Cuando se habilita el seguimiento, los registros de seguimiento de errores se emiten en ETW. Los eventos de seguimiento de ETW (entre el intervalo de 100-113) correspondientes a los eventos de seguimiento emitidos por el participante de seguimiento de ETW se escriben en el registro analítico.  
  
 Para ver los registros de seguimiento, siga estos pasos.  
  
1.  Para abrir el Visor de eventos, haga clic en **iniciar**y, a continuación, haga clic en **ejecutar.** En el cuadro de diálogo Ejecutar, escriba `eventvwr`.  
  
2.  En el cuadro de diálogo Visor de eventos, expanda el **registros de aplicaciones y servicios** nodo.  
  
3.  Expanda el **Microsoft**, **Windows**, y **aplicaciones de servidor-aplicaciones** nodos.  
  
4.  Haga clic en el **analítico** nodo bajo el **aplicaciones de servidor-aplicaciones** nodo y seleccione **Habilitar registro**.  
  
5.  Ejecute la aplicación habilitada para realizar seguimientos a fin de generar los registros de seguimiento.  
  
6.  Haga clic en el **analítico** nodo y seleccione **actualizar.** Los registros de seguimiento deben estar visibles en el panel central.  
  
 La siguiente imagen muestra eventos de seguimiento en el Visor de eventos.  
  
 ![Los registros de seguimiento que muestra de Visor de eventos](../../../docs/framework/windows-workflow-foundation/media/trackingeventviewer.PNG "TrackingEventViewer")  
  
### <a name="registering-an-application-specific-provider-id"></a>Registrar un identificador de proveedor específico de la aplicación  
 Si es necesario escribir eventos en un determinado registro de aplicaciones, siga estos pasos para registrar el nuevo manifiesto del proveedor.  
  
1.  Declare el Id. de proveedor en el archivo de configuración de la aplicación.  
  
    ```xml  
    <system.serviceModel>  
        <diagnostics etwProviderId="2720e974-9fe9-477a-bb60-81fe3bf91eec"/>  
    </system.serviceModel>  
    ```  
  
2.  Copie el archivo de manifiesto de %windir%\Microsoft.NET\Framework\\< versión más reciente de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]> \Microsoft.Windows.ApplicationServer.Applications.man en una ubicación temporal y cámbiele el nombre a Microsoft.Windows.ApplicationServer.Applications_Provider1.man  
  
3.  Cambie el GUID del archivo de manifiesto por el nuevo GUID.  
  
    ```xml  
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}"  
    ```  
  
4.  Cambie el nombre de proveedor si no desea desinstalar el proveedor predeterminado.  
  
    ```xml  
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}"  
    ```  
  
5.  Si ha cambiado el nombre de proveedor en el paso anterior, cambie los nombres de canal del archivo de manifiesto al nuevo nombre de proveedor.  
  
    ```xml  
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Admin" chid="ADMIN_CHANNEL" symbol="ADMIN_CHANNEL" type="Admin" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ADMIN_CHANNEL.message)" />  
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Operational" chid="OPERATIONAL_CHANNEL" symbol="OPERATIONAL_CHANNEL" type="Operational" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.OPERATIONAL_CHANNEL.message)" />  
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" />  
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Debug" chid="DEBUG_CHANNEL" symbol="DEBUG_CHANNEL" type="Debug" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.DEBUG_CHANNEL.message)" />  
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Perf" chid="PERF_CHANNEL" symbol="PERF_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.PERF_CHANNEL.message)" />  
    ```  
  
6.  Genere el archivo DLL de recursos siguiendo estos pasos.  
  
    1.  Instale el SDK de Windows. El SDK de Windows incluye el compilador de mensajes ([mc.exe](https://go.microsoft.com/fwlink/?LinkId=184606)) y el compilador de recursos ([rc.exe](https://go.microsoft.com/fwlink/?LinkId=184605)).  
  
    2.  En un símbolo del sistema de Windows SDK, ejecute mc.exe en el archivo de manifiesto nuevo.  
  
        ```  
        mc.exe Microsoft.Windows.ApplicationServer.Applications_Provider1.man  
        ```  
  
    3.  Ejecute rc.exe en el archivo de recursos generado en el paso anterior.  
  
        ```  
        rc.exe  Microsoft.Windows.ApplicationServer.Applications_Provider1.rc  
        ```  
  
    4.  Cree un archivo cs vacío denominado NewProviderReg.cs.  
  
    5.  Cree un archivo DLL de recursos mediante el compilador de C#.  
  
        ```  
        csc /target:library /win32res:Microsoft.Windows.ApplicationServer.Applications_Provider1.res NewProviderReg.cs /out:Microsoft.Windows.ApplicationServer.Applications_Provider1.dll  
        ```  
  
    6.  Cambie el nombre del archivo DLL de mensajes y de recursos en el archivo de manifiesto de `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` por el nuevo nombre de archivo DLL.  
  
        ```xml  
        <provider name="Microsoft-Windows-Application Server-Applications_Provider1" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" symbol="Microsoft_Windows_ApplicationServer_ApplicationEvents" resourceFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll" messageFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll">  
        ```  
  
    7.  Use [wevtutil](https://go.microsoft.com/fwlink/?LinkId=184608) para registrar el manifiesto.  
  
        ```  
        wevtutil im Microsoft.Windows.ApplicationServer.Applications_Provider1.man  
        ```  
  
## <a name="see-also"></a>Vea también  
 [Supervisión de Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201273)  
 [Supervisión de aplicaciones con App Fabric](https://go.microsoft.com/fwlink/?LinkId=201275)
