---
title: Configurar seguimiento para un flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 905adcc9-30a0-4918-acd6-563f86db988a
ms.openlocfilehash: 098b295be00b1b8283e26e79ea14e78634fdb504
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557559"
---
# <a name="configuring-tracking-for-a-workflow"></a><span data-ttu-id="a5241-102">Configurar seguimiento para un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a5241-102">Configuring Tracking for a Workflow</span></span>

<span data-ttu-id="a5241-103">Un flujo de trabajo se puede ejecutar de tres maneras:</span><span class="sxs-lookup"><span data-stu-id="a5241-103">A workflow can execute in three ways:</span></span>

- <span data-ttu-id="a5241-104">Se hospeda en <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="a5241-104">Hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>

- <span data-ttu-id="a5241-105">Ejecutado como <xref:System.Activities.WorkflowApplication></span><span class="sxs-lookup"><span data-stu-id="a5241-105">Executed as a <xref:System.Activities.WorkflowApplication></span></span>

- <span data-ttu-id="a5241-106">Ejecutado directamente utilizando <xref:System.Activities.WorkflowInvoker></span><span class="sxs-lookup"><span data-stu-id="a5241-106">Executed directly using <xref:System.Activities.WorkflowInvoker></span></span>

<span data-ttu-id="a5241-107">Dependiendo de la opción de hospedaje de flujo de trabajo, se puede agregar un participante de seguimiento, ya sea a través de código o de un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a5241-107">Depending on the workflow hosting option, a tracking participant can be added either through code or through a configuration file.</span></span> <span data-ttu-id="a5241-108">En este tema se describe cómo configurar el seguimiento agregando un participante de seguimiento a <xref:System.Activities.WorkflowApplication> y a <xref:System.ServiceModel.Activities.WorkflowServiceHost> y cómo habilitar el seguimiento al utilizar <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="a5241-108">This topic describes how tracking is configured by adding a tracking participant to a <xref:System.Activities.WorkflowApplication> and to a <xref:System.ServiceModel.Activities.WorkflowServiceHost>, and how to enable tracking when using <xref:System.Activities.WorkflowInvoker>.</span></span>

## <a name="configuring-workflow-application-tracking"></a><span data-ttu-id="a5241-109">Configurar seguimiento de aplicación de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a5241-109">Configuring Workflow Application Tracking</span></span>

<span data-ttu-id="a5241-110">Un flujo de trabajo se puede ejecutar mediante la clase <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="a5241-110">A workflow can run using the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="a5241-111">En este tema se muestra cómo configurar el seguimiento de una aplicación de flujo de trabajo de [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] al agregar un participante de seguimiento al host de flujo de trabajo <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="a5241-111">This topic demonstrates how tracking is configured for a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] workflow application by adding a tracking participant to the <xref:System.Activities.WorkflowApplication> workflow host.</span></span> <span data-ttu-id="a5241-112">En este caso, el flujo de trabajo se ejecuta como una aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5241-112">In this case, the workflow runs as a workflow application.</span></span> <span data-ttu-id="a5241-113">Configure una aplicación de flujo de trabajo mediante código (en lugar de utilizar un archivo de configuración), que es un archivo .exe auto-hospedado usando la clase <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="a5241-113">You configure a workflow application through code (rather than by using a configuration file), which is a self-hosted .exe file using the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="a5241-114">El participante de seguimiento se agrega como una extensión a la instancia <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="a5241-114">The tracking participant is added as an extension to the <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="a5241-115">Esto se realiza agregando <xref:System.Activities.Tracking.TrackingParticipant> a la colección de las extensiones para la instancia de WorkflowApplication.</span><span class="sxs-lookup"><span data-stu-id="a5241-115">This is done by adding the <xref:System.Activities.Tracking.TrackingParticipant> to the extensions collection for the WorkflowApplication instance.</span></span>

<span data-ttu-id="a5241-116">Para una aplicación de flujo de trabajo, puede agregar la extensión de comportamiento <xref:System.Activities.Tracking.EtwTrackingParticipant> tal y como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="a5241-116">For a workflow application, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> behavior extension as shown in the following code.</span></span>

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

### <a name="configuring-workflow-service-tracking"></a><span data-ttu-id="a5241-117">Configurar el seguimiento de servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a5241-117">Configuring Workflow Service Tracking</span></span>

<span data-ttu-id="a5241-118">Un flujo de trabajo se puede exponer como un servicio WCF cuando se hospeda en el <xref:System.ServiceModel.Activities.WorkflowServiceHost> host del servicio.</span><span class="sxs-lookup"><span data-stu-id="a5241-118">A workflow can be exposed as a WCF service when hosted in the <xref:System.ServiceModel.Activities.WorkflowServiceHost> service host.</span></span> <span data-ttu-id="a5241-119"><xref:System.ServiceModel.Activities.WorkflowServiceHost> es una implementación especializada de .NET ServiceHost para un servicio basado en flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5241-119"><xref:System.ServiceModel.Activities.WorkflowServiceHost> is a specialized .NET ServiceHost implementation for a workflow-based service.</span></span> <span data-ttu-id="a5241-120">En esta sección se explica cómo configurar el seguimiento para un servicio de flujo de trabajo de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] que se ejecuta en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="a5241-120">This section explains how to configure tracking for a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow service running in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="a5241-121">Se configura mediante un archivo Web.config (para un servicio hospedado en web) o un archivo App.config (para un servicio hospedado en una aplicación independiente, como una aplicación de consola) especificando un comportamiento de servicio o mediante código agregando un comportamiento específico de seguimiento a la colección <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> del host de servicio.</span><span class="sxs-lookup"><span data-stu-id="a5241-121">It is configured through a Web.config file (for a Web-hosted service) or an App.config file (for a service hosted in a stand-alone application, such as a console application) by specifying a service behavior or through code by adding a tracking-specific behavior to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection for the service host.</span></span>

<span data-ttu-id="a5241-122">Para un servicio de flujo de trabajo hospedado en <xref:System.ServiceModel.WorkflowServiceHost> , puede agregar <xref:System.Activities.Tracking.EtwTrackingParticipant> mediante el <`behavior` elemento> en un archivo de configuración, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a5241-122">For a workflow service hosted in <xref:System.ServiceModel.WorkflowServiceHost>, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>

```xml
<behaviors>
   <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
   </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="a5241-123">Por otra parte, en el caso de un servicio de flujo de trabajo hospedado en <xref:System.ServiceModel.WorkflowServiceHost>, puede agregar la extensión de comportamiento <xref:System.Activities.Tracking.EtwTrackingParticipant> a través del código.</span><span class="sxs-lookup"><span data-stu-id="a5241-123">Alternatively, for a workflow service hosted in <xref:System.ServiceModel.WorkflowServiceHost>, you can add the <xref:System.Activities.Tracking.EtwTrackingParticipant> behavior extension through code.</span></span> <span data-ttu-id="a5241-124">Para agregar un participante de seguimiento personalizado, cree una nueva extensión de comportamiento y agréguela a <xref:System.ServiceModel.ServiceHost> tal y como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a5241-124">To add a custom tracking participant, create a new behavior extension and add it to the <xref:System.ServiceModel.ServiceHost> as shown in the following example code.</span></span>

> [!NOTE]
> <span data-ttu-id="a5241-125">Si desea ver el código de ejemplo que muestra cómo crear un elemento de comportamiento personalizado que agrega un participante de seguimiento personalizado, consulte los ejemplos de [seguimiento](./samples/tracking.md) .</span><span class="sxs-lookup"><span data-stu-id="a5241-125">If you want to view sample code that shows how to create a custom behavior element that adds a custom tracking participant, refer to the [Tracking](./samples/tracking.md) samples.</span></span>

```csharp
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

<span data-ttu-id="a5241-126">El participante del seguimiento se agrega al host de servicio de flujo de trabajo como una extensión al comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a5241-126">The tracking participant is added to the workflow service host as an extension to the behavior.</span></span>

<span data-ttu-id="a5241-127">El siguiente código de ejemplo muestra cómo leer un perfil de seguimiento del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a5241-127">This sample code below shows how to read a tracking profile from configuration file.</span></span>

```csharp
TrackingProfile GetProfile(string profileName, string displayName)
        {
            TrackingProfile trackingProfile = null;
            TrackingSection trackingSection = (TrackingSection)WebConfigurationManager.GetSection("system.serviceModel/tracking");
            if (trackingSection == null)
            {
                return null;
            }

            profileName ??= "";

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

<span data-ttu-id="a5241-128">Este código de ejemplo muestra cómo agregar un perfil de seguimiento a un host del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5241-128">This sample code shows how to add a tracking profile to a workflow host.</span></span>

```csharp
WorkflowServiceHost workflowServiceHost = serviceHostBase as WorkflowServiceHost;
if (null != workflowServiceHost)
{
    string workflowDisplayName = workflowServiceHost.Activity.DisplayName;
    TrackingProfile trackingProfile = GetProfile(this.profileName, workflowDisplayName);
    workflowServiceHost.WorkflowExtensions.Add(()  => new EtwTrackingParticipant {
        TrackingProfile = trackingProfile
    });
 }
```

> [!NOTE]
> <span data-ttu-id="a5241-129">Para obtener más información sobre los perfiles de seguimiento, consulte [perfiles de seguimiento](tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a5241-129">For more information on tracking profiles, refer to [Tracking Profiles](tracking-profiles.md).</span></span>

### <a name="configuring-tracking-using-workflowinvoker"></a><span data-ttu-id="a5241-130">Configurar el seguimiento mediante WorkflowInvoker</span><span class="sxs-lookup"><span data-stu-id="a5241-130">Configuring tracking using WorkflowInvoker</span></span>

<span data-ttu-id="a5241-131">Para configurar el seguimiento para un flujo de trabajo ejecutado utilizando <xref:System.Activities.WorkflowInvoker>, agregue el proveedor del seguimiento como una extensión de una instancia de <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="a5241-131">To configure tracking for a workflow executed using <xref:System.Activities.WorkflowInvoker>, add the tracking provider as an extension to a <xref:System.Activities.WorkflowInvoker> instance.</span></span> <span data-ttu-id="a5241-132">El ejemplo de código siguiente procede del ejemplo de [seguimiento personalizado](./samples/custom-tracking.md) .</span><span class="sxs-lookup"><span data-stu-id="a5241-132">The following code example is from the [Custom Tracking](./samples/custom-tracking.md) sample.</span></span>

```csharp
WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
invoker.Invoke();
```

### <a name="viewing-tracking-records-in-event-viewer"></a><span data-ttu-id="a5241-133">Visualizar los registros de seguimiento en el Visor de eventos</span><span class="sxs-lookup"><span data-stu-id="a5241-133">Viewing tracking records in Event Viewer</span></span>

<span data-ttu-id="a5241-134">Hay dos registros del Visor de eventos que resultan de especial interés para ver la ejecución del seguimiento de WF: el registro analítico y el registro de depuración.</span><span class="sxs-lookup"><span data-stu-id="a5241-134">There are two Event Viewer logs of particular interest to view when tracking WF execution - the Analytic log and the Debug log.</span></span> <span data-ttu-id="a5241-135">Ambos residen en el nodo servidor de aplicaciones de Microsoft&#124;Windows&#124;-aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a5241-135">Both reside under the Microsoft&#124;Windows&#124;Application Server-Applications node.</span></span> <span data-ttu-id="a5241-136">Los registros de esta sección contienen eventos de una única aplicación en lugar de los eventos que afectan a todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="a5241-136">Logs within this section contain events from a single application rather than events that have an impact on the entire system.</span></span>

<span data-ttu-id="a5241-137">Los eventos de seguimiento de depuración se escriben en el registro de depuración.</span><span class="sxs-lookup"><span data-stu-id="a5241-137">Debug trace events are written to the Debug Log.</span></span> <span data-ttu-id="a5241-138">Para recopilar eventos de seguimiento de depuración de WF en el Visor de eventos, habilite el registro de depuración.</span><span class="sxs-lookup"><span data-stu-id="a5241-138">To collect WF debug trace events in the Event Viewer, enable the Debug Log.</span></span>

1. <span data-ttu-id="a5241-139">Para abrir Visor de eventos, haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar.**</span><span class="sxs-lookup"><span data-stu-id="a5241-139">To open Event Viewer, click **Start**, and then click **Run.**</span></span> <span data-ttu-id="a5241-140">En el cuadro de diálogo Ejecutar, escriba `eventvwr` .</span><span class="sxs-lookup"><span data-stu-id="a5241-140">In the Run dialog, type `eventvwr`.</span></span>

2. <span data-ttu-id="a5241-141">En el cuadro de diálogo Visor de eventos, expanda el nodo **registros de aplicaciones y servicios** .</span><span class="sxs-lookup"><span data-stu-id="a5241-141">In the Event Viewer dialog, expand the **Applications and Services Logs** node.</span></span>

3. <span data-ttu-id="a5241-142">Expanda los nodos **Microsoft**, **Windows**y **servidor de aplicaciones-aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="a5241-142">Expand the **Microsoft**, **Windows**, and **Application Server-Applications** nodes.</span></span>

4. <span data-ttu-id="a5241-143">Haga clic con el botón secundario en el nodo **depurar** del nodo **servidor de aplicaciones-aplicaciones** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="a5241-143">Right-click the **Debug** node under the **Application Server-Applications** node, and select **Enable Log**.</span></span>

5. <span data-ttu-id="a5241-144">Ejecute la aplicación habilitada para realizar seguimientos con el fin de generar eventos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a5241-144">Execute your tracing-enabled application to generate tracing events.</span></span>

6. <span data-ttu-id="a5241-145">Haga clic con el botón secundario en el nodo **depurar** y seleccione **Actualizar.**</span><span class="sxs-lookup"><span data-stu-id="a5241-145">Right-click the **Debug** node and select **Refresh.**</span></span> <span data-ttu-id="a5241-146">Los eventos de seguimiento deben estar visibles en el panel central.</span><span class="sxs-lookup"><span data-stu-id="a5241-146">Tracing events should be visible in the center pane.</span></span>

<span data-ttu-id="a5241-147">WF 4 proporciona un participante de seguimiento que escribe registros de seguimiento en una sesión de ETW (Seguimiento de eventos para Windows).</span><span class="sxs-lookup"><span data-stu-id="a5241-147">WF 4 provides a tracking participant that writes tracking records to an ETW (Event Tracing for Windows) session.</span></span> <span data-ttu-id="a5241-148">El participante de seguimiento de ETW se configura con un perfil de seguimiento para suscribirse a registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a5241-148">The ETW tracking participant is configured with a tracking profile to subscribe to tracking records.</span></span> <span data-ttu-id="a5241-149">Cuando se habilita el seguimiento, los registros de seguimiento de errores se emiten en ETW.</span><span class="sxs-lookup"><span data-stu-id="a5241-149">When tracking is enabled, errors tracking records are emitted to ETW.</span></span> <span data-ttu-id="a5241-150">Los eventos de seguimiento de ETW (entre el intervalo de 100-113) correspondientes a los eventos de seguimiento emitidos por el participante de seguimiento de ETW se escriben en el registro analítico.</span><span class="sxs-lookup"><span data-stu-id="a5241-150">ETW tracking events (between the range of 100-113) corresponding to the tracking events emitted by the ETW tracking participant are written to the Analytic Log.</span></span>

<span data-ttu-id="a5241-151">Para ver los registros de seguimiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a5241-151">To view tracking records, follow these steps.</span></span>

1. <span data-ttu-id="a5241-152">Para abrir Visor de eventos, haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar.**</span><span class="sxs-lookup"><span data-stu-id="a5241-152">To open Event Viewer, click **Start**, and then click **Run.**</span></span> <span data-ttu-id="a5241-153">En el cuadro de diálogo Ejecutar, escriba `eventvwr` .</span><span class="sxs-lookup"><span data-stu-id="a5241-153">In the Run dialog, type `eventvwr`.</span></span>

2. <span data-ttu-id="a5241-154">En el cuadro de diálogo Visor de eventos, expanda el nodo **registros de aplicaciones y servicios** .</span><span class="sxs-lookup"><span data-stu-id="a5241-154">In the Event Viewer dialog, expand the **Applications and Services Logs** node.</span></span>

3. <span data-ttu-id="a5241-155">Expanda los nodos **Microsoft**, **Windows**y **servidor de aplicaciones-aplicaciones** .</span><span class="sxs-lookup"><span data-stu-id="a5241-155">Expand the **Microsoft**, **Windows**, and **Application Server-Applications** nodes.</span></span>

4. <span data-ttu-id="a5241-156">Haga clic con el botón secundario en el nodo **análisis** del nodo **servidor de aplicaciones-aplicaciones** y seleccione **Habilitar registro**.</span><span class="sxs-lookup"><span data-stu-id="a5241-156">Right-click the **Analytic** node under the **Application Server-Applications** node, and select **Enable Log**.</span></span>

5. <span data-ttu-id="a5241-157">Ejecute la aplicación habilitada para realizar seguimientos a fin de generar los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a5241-157">Execute your tracking-enabled application to generate tracking records.</span></span>

6. <span data-ttu-id="a5241-158">Haga clic con el botón secundario en el nodo **analítico** y seleccione **Actualizar.**</span><span class="sxs-lookup"><span data-stu-id="a5241-158">Right-click the **Analytic** node and select **Refresh.**</span></span> <span data-ttu-id="a5241-159">Los registros de seguimiento deben estar visibles en el panel central.</span><span class="sxs-lookup"><span data-stu-id="a5241-159">Tracking records should be visible in the center pane.</span></span>

<span data-ttu-id="a5241-160">En la imagen siguiente se muestran los eventos de seguimiento en el visor de eventos:</span><span class="sxs-lookup"><span data-stu-id="a5241-160">The following image shows tracking events in the event viewer:</span></span>

![Captura de pantalla del Visor de eventos que muestra los registros de seguimiento.](./media/configuring-tracking-for-a-workflow/tracking-event-viewer.png)

### <a name="registering-an-application-specific-provider-id"></a><span data-ttu-id="a5241-162">Registrar un identificador de proveedor específico de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a5241-162">Registering an application-specific provider ID</span></span>

<span data-ttu-id="a5241-163">Si es necesario escribir eventos en un determinado registro de aplicaciones, siga estos pasos para registrar el nuevo manifiesto del proveedor.</span><span class="sxs-lookup"><span data-stu-id="a5241-163">If events need to be written to a specific application log, follow these steps to register the new provider manifest.</span></span>

1. <span data-ttu-id="a5241-164">Declare el Id. de proveedor en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5241-164">Declare the provider ID in the application configuration file.</span></span>

    ```xml
    <system.serviceModel>
        <diagnostics etwProviderId="2720e974-9fe9-477a-bb60-81fe3bf91eec"/>
    </system.serviceModel>
    ```

2. <span data-ttu-id="a5241-165">Copie el archivo de manifiesto de%windir%\Microsoft.NET\Framework \\ \<latest version of [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]> \Microsoft.Windows.ApplicationServer.Applications.Man en una ubicación temporal y cambie su nombre a Microsoft. Windows. ApplicationServer. Applications_Provider1. Man.</span><span class="sxs-lookup"><span data-stu-id="a5241-165">Copy the manifest file from %windir%\Microsoft.NET\Framework\\\<latest version of [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]>\Microsoft.Windows.ApplicationServer.Applications.man to a temporary location, and rename it to Microsoft.Windows.ApplicationServer.Applications_Provider1.man</span></span>

3. <span data-ttu-id="a5241-166">Cambie el GUID del archivo de manifiesto por el nuevo GUID.</span><span class="sxs-lookup"><span data-stu-id="a5241-166">Change the GUID in the manifest file to the new GUID.</span></span>

    ```xml
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" />
    ```

4. <span data-ttu-id="a5241-167">Cambie el nombre de proveedor si no desea desinstalar el proveedor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a5241-167">Change the provider name if you do not want to uninstall the default provider.</span></span>

    ```xml
    <provider name="Microsoft-Windows-Application Server-Applications" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" />
    ```

5. <span data-ttu-id="a5241-168">Si ha cambiado el nombre de proveedor en el paso anterior, cambie los nombres de canal del archivo de manifiesto al nuevo nombre de proveedor.</span><span class="sxs-lookup"><span data-stu-id="a5241-168">If you changed the provider name in the previous step, change the channel names in the manifest file to the new provider name.</span></span>

    ```xml
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Admin" chid="ADMIN_CHANNEL" symbol="ADMIN_CHANNEL" type="Admin" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ADMIN_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Operational" chid="OPERATIONAL_CHANNEL" symbol="OPERATIONAL_CHANNEL" type="Operational" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.OPERATIONAL_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Debug" chid="DEBUG_CHANNEL" symbol="DEBUG_CHANNEL" type="Debug" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.DEBUG_CHANNEL.message)" />
    <channel name="Microsoft-Windows-Application Server-Applications_Provider1/Perf" chid="PERF_CHANNEL" symbol="PERF_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.PERF_CHANNEL.message)" />
    ```

6. <span data-ttu-id="a5241-169">Genere el archivo DLL de recursos siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a5241-169">Generate the resource DLL by following these steps.</span></span>

    1. <span data-ttu-id="a5241-170">Instale el SDK de Windows.</span><span class="sxs-lookup"><span data-stu-id="a5241-170">Install the Windows SDK.</span></span> <span data-ttu-id="a5241-171">El Windows SDK incluye el compilador de mensajes ([mc.exe](/windows/win32/wes/message-compiler--mc-exe-)) y el compilador de recursos ([rc.exe](/windows/win32/menurc/using-rc-the-rc-command-line-)).</span><span class="sxs-lookup"><span data-stu-id="a5241-171">The Windows SDK includes the message compiler ([mc.exe](/windows/win32/wes/message-compiler--mc-exe-)) and resource compiler ([rc.exe](/windows/win32/menurc/using-rc-the-rc-command-line-)).</span></span>

    2. <span data-ttu-id="a5241-172">En un símbolo del sistema de Windows SDK, ejecute mc.exe en el archivo de manifiesto nuevo.</span><span class="sxs-lookup"><span data-stu-id="a5241-172">In a Windows SDK command prompt, run mc.exe on the new manifest file.</span></span>

        ```console
        mc.exe Microsoft.Windows.ApplicationServer.Applications_Provider1.man
        ```

    3. <span data-ttu-id="a5241-173">Ejecute rc.exe en el archivo de recursos generado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="a5241-173">Run rc.exe on the resource file generated in the previous step.</span></span>

        ```console
        rc.exe  Microsoft.Windows.ApplicationServer.Applications_Provider1.rc
        ```

    4. <span data-ttu-id="a5241-174">Cree un archivo cs vacío denominado NewProviderReg.cs.</span><span class="sxs-lookup"><span data-stu-id="a5241-174">Create an empty cs file called NewProviderReg.cs.</span></span>

    5. <span data-ttu-id="a5241-175">Cree un archivo DLL de recursos mediante el compilador de C#.</span><span class="sxs-lookup"><span data-stu-id="a5241-175">Create a resource DLL using the C# compiler.</span></span>

        ```console
        csc /target:library /win32res:Microsoft.Windows.ApplicationServer.Applications_Provider1.res NewProviderReg.cs /out:Microsoft.Windows.ApplicationServer.Applications_Provider1.dll
        ```

    6. <span data-ttu-id="a5241-176">Cambie el nombre de la dll del recurso y del mensaje en el archivo de manifiesto del `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` nombre del nuevo archivo dll.</span><span class="sxs-lookup"><span data-stu-id="a5241-176">Change the resource and message dll name in the manifest file from `Microsoft.Windows.ApplicationServer.Applications.Provider1.man` to the new dll name.</span></span>

        ```xml
        <provider name="Microsoft-Windows-Application Server-Applications_Provider1" guid="{2720e974-9fe9-477a-bb60-81fe3bf91eec}" symbol="Microsoft_Windows_ApplicationServer_ApplicationEvents" resourceFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll" messageFileName="<dll directory>\Microsoft.Windows.ApplicationServer.Applications_Provider1.dll" />
        ```

    7. <span data-ttu-id="a5241-177">Use [wevtutil](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732848(v=ws.10)) para registrar el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="a5241-177">Use [wevtutil](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732848(v=ws.10)) to register the manifest.</span></span>

        ```console
        wevtutil im Microsoft.Windows.ApplicationServer.Applications_Provider1.man
        ```

## <a name="see-also"></a><span data-ttu-id="a5241-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5241-178">See also</span></span>

- <span data-ttu-id="a5241-179">[Supervisión de Windows Server App fabric](/previous-versions/appfabric/ee677251(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a5241-179">[Windows Server App Fabric Monitoring](/previous-versions/appfabric/ee677251(v=azure.10))</span></span>
- <span data-ttu-id="a5241-180">[Supervisión de aplicaciones con App fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="a5241-180">[Monitoring Applications with App Fabric](/previous-versions/appfabric/ee677276(v=azure.10))</span></span>
