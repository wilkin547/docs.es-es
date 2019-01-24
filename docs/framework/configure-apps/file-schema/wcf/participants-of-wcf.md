---
title: '&lt;participants&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: d99dbddc-0057-4e18-8e42-f91411d39970
ms.openlocfilehash: 892392454b9969e0c63e0ad7eb15f788466ad963
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630975"
---
# <a name="ltparticipantsgt-of-wcf"></a><span data-ttu-id="4fe88-102">&lt;participants&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="4fe88-102">&lt;participants&gt; of WCF</span></span>
<span data-ttu-id="4fe88-103">Configure una lista de participantes de seguimiento que escuchen los registros de seguimiento que se emiten desde el tiempo de ejecución directamente y los procesan del modo en que cada uno esté configurado.</span><span class="sxs-lookup"><span data-stu-id="4fe88-103">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="4fe88-104">Esto incluye la escritura en un resultado concreto (p. ej., un archivo, la consola o ETW), procesar o agregar los registros, o cualquier otra combinación que pueda resultar necesaria.</span><span class="sxs-lookup"><span data-stu-id="4fe88-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="4fe88-105">Para obtener más información de seguimiento de flujo de trabajo y los participantes de seguimiento, vea [seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) y [participantes de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="4fe88-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 <span data-ttu-id="4fe88-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4fe88-106">\<system.serviceModel></span></span>  
<span data-ttu-id="4fe88-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="4fe88-107">\<tracking></span></span>  
<span data-ttu-id="4fe88-108">\<participants></span><span class="sxs-lookup"><span data-stu-id="4fe88-108">\<participants></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fe88-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fe88-109">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fe88-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4fe88-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4fe88-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4fe88-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fe88-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="4fe88-112">Attributes</span></span>  
 <span data-ttu-id="4fe88-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4fe88-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4fe88-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4fe88-114">Child Elements</span></span>  
  
|<span data-ttu-id="4fe88-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fe88-115">Element</span></span>|<span data-ttu-id="4fe88-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fe88-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fe88-117">\<add></span><span class="sxs-lookup"><span data-stu-id="4fe88-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|<span data-ttu-id="4fe88-118">Contiene los valores para un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4fe88-118">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fe88-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4fe88-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4fe88-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fe88-120">Element</span></span>|<span data-ttu-id="4fe88-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fe88-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fe88-122">\<tracking></span><span class="sxs-lookup"><span data-stu-id="4fe88-122">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="4fe88-123">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4fe88-123">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fe88-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4fe88-124">Remarks</span></span>  
 <span data-ttu-id="4fe88-125">Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.</span><span class="sxs-lookup"><span data-stu-id="4fe88-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="4fe88-126">Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4fe88-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="4fe88-127">Varios participantes de seguimiento pueden utilizar los eventos de seguimiento de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="4fe88-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="4fe88-128">Cada participante de seguimiento puede asociarse con un perfil de seguimiento distinto.</span><span class="sxs-lookup"><span data-stu-id="4fe88-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="4fe88-129">Se proporciona un participante de seguimiento estándar que escribe los registros de seguimiento en una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="4fe88-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="4fe88-130">El participante se configura en un servicio de flujo de trabajo agregando un comportamiento específico del seguimiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4fe88-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="4fe88-131">Habilitar un participante de seguimiento de ETW permite realizar un seguimiento de los registros que se van a ver en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="4fe88-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="4fe88-132">Si eso no cumple sus requisitos, también puede escribir un participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="4fe88-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fe88-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fe88-133">Example</span></span>  
 <span data-ttu-id="4fe88-134">El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="4fe88-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="4fe88-135">El Id. del proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se definen en la sección `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="4fe88-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="4fe88-136">El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="4fe88-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="4fe88-137">Esto viene definido por el atributo `profileName` del elemento `<add>`.</span><span class="sxs-lookup"><span data-stu-id="4fe88-137">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="4fe88-138">Una vez definidos, el participante de seguimiento se agrega al comportamiento del servicio `<etwTracking>`.</span><span class="sxs-lookup"><span data-stu-id="4fe88-138">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="4fe88-139">Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4fe88-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0" />
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile"/>
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile"/>
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="4fe88-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fe88-140">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- [<span data-ttu-id="4fe88-141">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="4fe88-141">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4fe88-142">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4fe88-142">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
