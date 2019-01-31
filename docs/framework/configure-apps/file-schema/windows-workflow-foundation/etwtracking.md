---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: 12589ab7c6cb65618a5f53a3e4be49d85a2ffbb7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277206"
---
# <a name="etwtracking"></a><span data-ttu-id="87b9e-101">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="87b9e-101">\<etwTracking></span></span>
<span data-ttu-id="87b9e-102">Un comportamiento del servicio que permite que un servicio usar el seguimiento de ETW utilizando un <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="87b9e-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="87b9e-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="87b9e-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="87b9e-104">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="87b9e-104">\<behaviors></span></span>  
<span data-ttu-id="87b9e-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="87b9e-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="87b9e-106">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="87b9e-106">\<behavior></span></span>  
<span data-ttu-id="87b9e-107">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="87b9e-107">\<etwTracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87b9e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87b9e-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87b9e-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="87b9e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="87b9e-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="87b9e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87b9e-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="87b9e-111">Attributes</span></span>  
  
|<span data-ttu-id="87b9e-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="87b9e-112">Attribute</span></span>|<span data-ttu-id="87b9e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="87b9e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87b9e-114">profileName</span><span class="sxs-lookup"><span data-stu-id="87b9e-114">profileName</span></span>|<span data-ttu-id="87b9e-115">Una cadena que especifica el nombre del perfil de seguimiento asociado a este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="87b9e-115">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87b9e-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="87b9e-116">Child Elements</span></span>  
 <span data-ttu-id="87b9e-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="87b9e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87b9e-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="87b9e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="87b9e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="87b9e-119">Element</span></span>|<span data-ttu-id="87b9e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="87b9e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87b9e-121">\<comportamiento > de \<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="87b9e-121">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="87b9e-122">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="87b9e-122">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87b9e-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="87b9e-123">Remarks</span></span>  
 <span data-ttu-id="87b9e-124">Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración configura un participante de seguimiento en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="87b9e-124">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="87b9e-125">Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.</span><span class="sxs-lookup"><span data-stu-id="87b9e-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="87b9e-126">Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="87b9e-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87b9e-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87b9e-127">Example</span></span>  
 <span data-ttu-id="87b9e-128">El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="87b9e-128">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="87b9e-129">El identificador del proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se define en el  **\<diagnósticos >** sección.</span><span class="sxs-lookup"><span data-stu-id="87b9e-129">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="87b9e-130">El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="87b9e-130">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="87b9e-131">Esto viene definido por el **profileName** atributo de la  **\<Agregar >** elemento.</span><span class="sxs-lookup"><span data-stu-id="87b9e-131">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="87b9e-132">Una vez que se definen, el participante de seguimiento se agrega a la  **\<etwTracking >** comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="87b9e-132">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="87b9e-133">Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="87b9e-133">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="87b9e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="87b9e-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="87b9e-135">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="87b9e-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="87b9e-136">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="87b9e-136">Tracking Participants</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
