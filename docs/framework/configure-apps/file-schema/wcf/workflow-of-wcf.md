---
description: 'Más información sobre: <workflow> de WCF'
title: <workflow> de WCF
ms.date: 03/30/2017
ms.assetid: c0443eba-d3b4-4fae-886e-9878daf77691
ms.openlocfilehash: 44391017b98bdbe76981c695c22ae68b048c3050
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682389"
---
# <a name="workflow-of-wcf"></a><span data-ttu-id="a0cba-103">\<workflow> de WCF</span><span class="sxs-lookup"><span data-stu-id="a0cba-103">\<workflow> of WCF</span></span>

<span data-ttu-id="a0cba-104">Configure un participante del seguimiento que escucha los registros de seguimiento que se emiten del tiempo de ejecución directamente y los procesa del modo en que cada uno esté configurado.</span><span class="sxs-lookup"><span data-stu-id="a0cba-104">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="a0cba-105">Esto incluye la escritura en un resultado concreto (p. ej., un archivo, la consola o ETW), procesar o agregar los registros, o cualquier otra combinación que pueda resultar necesaria.</span><span class="sxs-lookup"><span data-stu-id="a0cba-105">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="a0cba-106">Para obtener más información sobre los participantes de seguimiento y seguimiento de flujos de trabajo, vea seguimiento y seguimiento de [flujos de trabajo](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) y [participantes](../../../windows-workflow-foundation/tracking-participants.md)de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a0cba-106">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
 \<system.serviceModel>  
\<tracking>  
\<participants>  
\<add>  
  
## <a name="syntax"></a><span data-ttu-id="a0cba-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0cba-107">Syntax</span></span>  
  
```xml  
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0cba-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0cba-108">Attributes and Elements</span></span>  

 <span data-ttu-id="a0cba-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0cba-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0cba-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0cba-110">Attributes</span></span>  
  
|<span data-ttu-id="a0cba-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0cba-111">Element</span></span>|<span data-ttu-id="a0cba-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0cba-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0cba-113">name</span><span class="sxs-lookup"><span data-stu-id="a0cba-113">name</span></span>|<span data-ttu-id="a0cba-114">Cadena que especifica el nombre de un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a0cba-114">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="a0cba-115">profileName</span><span class="sxs-lookup"><span data-stu-id="a0cba-115">profileName</span></span>|<span data-ttu-id="a0cba-116">Una cadena que especifica el nombre del perfil de seguimiento que define los registros de seguimiento a los que se ha suscrito el participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a0cba-116">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="a0cba-117">type</span><span class="sxs-lookup"><span data-stu-id="a0cba-117">type</span></span>|<span data-ttu-id="a0cba-118">Una cadena que especifica el tipo de un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a0cba-118">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0cba-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0cba-119">Child Elements</span></span>  

 <span data-ttu-id="a0cba-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a0cba-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0cba-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0cba-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a0cba-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0cba-122">Element</span></span>|<span data-ttu-id="a0cba-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a0cba-123">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="a0cba-124">Una lista de los participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a0cba-124">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0cba-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a0cba-125">Remarks</span></span>  

 <span data-ttu-id="a0cba-126">Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.</span><span class="sxs-lookup"><span data-stu-id="a0cba-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="a0cba-127">Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a0cba-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="a0cba-128">Varios participantes de seguimiento pueden utilizar los eventos de seguimiento de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="a0cba-128">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="a0cba-129">Cada participante de seguimiento puede asociarse con un perfil de seguimiento distinto.</span><span class="sxs-lookup"><span data-stu-id="a0cba-129">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="a0cba-130">Se proporciona un participante de seguimiento estándar que escribe los registros de seguimiento en una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="a0cba-130">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="a0cba-131">El participante se configura en un servicio de flujo de trabajo agregando un comportamiento específico del seguimiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a0cba-131">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="a0cba-132">Habilitar un participante de seguimiento de ETW permite realizar un seguimiento de los registros que se van a ver en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="a0cba-132">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="a0cba-133">Si eso no cumple sus requisitos, también puede escribir un participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="a0cba-133">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0cba-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a0cba-134">Example</span></span>  

 <span data-ttu-id="a0cba-135">El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="a0cba-135">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="a0cba-136">El Id. del proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se definen en la sección `<diagnostics>`.</span><span class="sxs-lookup"><span data-stu-id="a0cba-136">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the `<diagnostics>` section.</span></span> <span data-ttu-id="a0cba-137">El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="a0cba-137">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="a0cba-138">Esto viene definido por el atributo `profileName` del elemento `<add>`.</span><span class="sxs-lookup"><span data-stu-id="a0cba-138">This is defined by the `profileName` attribute of the `<add>` element.</span></span> <span data-ttu-id="a0cba-139">Una vez definidos, el participante de seguimiento se agrega al comportamiento del servicio `<etwTracking>`.</span><span class="sxs-lookup"><span data-stu-id="a0cba-139">Once these are defined, the Tracking Participant is added to the `<etwTracking>` service behavior.</span></span> <span data-ttu-id="a0cba-140">Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a0cba-140">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
             profileName="HealthMonitoring_Tracking_Profile" />
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="a0cba-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0cba-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="a0cba-142">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a0cba-142">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a0cba-143">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a0cba-143">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
