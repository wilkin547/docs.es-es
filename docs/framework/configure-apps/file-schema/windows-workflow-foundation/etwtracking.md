---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: e7614f158826e3522ac8e17d60c1ea65fefc8612
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174452"
---
# <a name="etwtracking"></a><span data-ttu-id="68272-101">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="68272-101">\<etwTracking></span></span>
<span data-ttu-id="68272-102">Un comportamiento del servicio que permite que un servicio usar el seguimiento de ETW utilizando un <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="68272-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="68272-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="68272-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="68272-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="68272-104">\<behaviors></span></span>  
<span data-ttu-id="68272-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="68272-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="68272-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="68272-106">\<behavior></span></span>  
<span data-ttu-id="68272-107">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="68272-107">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68272-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68272-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68272-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="68272-109">Attributes and Elements</span></span>  
 <span data-ttu-id="68272-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="68272-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68272-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="68272-111">Attributes</span></span>  
  
|<span data-ttu-id="68272-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="68272-112">Attribute</span></span>|<span data-ttu-id="68272-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="68272-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68272-114">profileName</span><span class="sxs-lookup"><span data-stu-id="68272-114">profileName</span></span>|<span data-ttu-id="68272-115">Una cadena que especifica el nombre del perfil de seguimiento asociado a este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="68272-115">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68272-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="68272-116">Child Elements</span></span>  
 <span data-ttu-id="68272-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="68272-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68272-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="68272-118">Parent Elements</span></span>  
  
|<span data-ttu-id="68272-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="68272-119">Element</span></span>|<span data-ttu-id="68272-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="68272-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68272-121">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="68272-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="68272-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="68272-122">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68272-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="68272-123">Remarks</span></span>  
 <span data-ttu-id="68272-124">Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración configura un participante de seguimiento en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68272-124">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="68272-125">Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.</span><span class="sxs-lookup"><span data-stu-id="68272-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="68272-126">Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="68272-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68272-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68272-127">Example</span></span>  
 <span data-ttu-id="68272-128">El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="68272-128">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="68272-129">El identificador del proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se define en el  **\<diagnósticos >** sección.</span><span class="sxs-lookup"><span data-stu-id="68272-129">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="68272-130">El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="68272-130">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="68272-131">Esto viene definido por el **profileName** atributo de la  **\<Agregar >** elemento.</span><span class="sxs-lookup"><span data-stu-id="68272-131">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="68272-132">Una vez que se definen, el participante de seguimiento se agrega a la  **\<etwTracking >** comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="68272-132">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="68272-133">Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="68272-133">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
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
  
## <a name="see-also"></a><span data-ttu-id="68272-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="68272-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="68272-135">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="68272-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="68272-136">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="68272-136">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
