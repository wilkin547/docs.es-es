---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: e6e996bd1cc32258167e30287e9338a4773ce921
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152033"
---
# <a name="participants"></a><span data-ttu-id="63f4d-101">\<participantes></span><span class="sxs-lookup"><span data-stu-id="63f4d-101">\<participants></span></span>
<span data-ttu-id="63f4d-102">Configure una lista de participantes de seguimiento que escuchen los registros de seguimiento que se emiten desde el tiempo de ejecución directamente y los procesan del modo en que cada uno esté configurado.</span><span class="sxs-lookup"><span data-stu-id="63f4d-102">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="63f4d-103">Esto incluye la escritura en un resultado concreto (p. ej., un archivo, la consola o ETW), procesar o agregar los registros, o cualquier otra combinación que pueda resultar necesaria.</span><span class="sxs-lookup"><span data-stu-id="63f4d-103">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="63f4d-104">Para obtener más información sobre el seguimiento del flujo de trabajo y el seguimiento de los participantes, consulte Seguimiento del flujo de [trabajo y Seguimiento](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) y seguimiento de [participantes](../../../windows-workflow-foundation/tracking-participants.md).</span><span class="sxs-lookup"><span data-stu-id="63f4d-104">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
<span data-ttu-id="63f4d-105">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="63f4d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="63f4d-106">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="63f4d-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="63f4d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<seguimiento>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="63f4d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="63f4d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<participantes>**</span><span class="sxs-lookup"><span data-stu-id="63f4d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<participants>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63f4d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63f4d-109">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63f4d-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="63f4d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="63f4d-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="63f4d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63f4d-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="63f4d-112">Attributes</span></span>  
 <span data-ttu-id="63f4d-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="63f4d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="63f4d-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="63f4d-114">Child Elements</span></span>  
  
|<span data-ttu-id="63f4d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="63f4d-115">Element</span></span>|<span data-ttu-id="63f4d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="63f4d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63f4d-117">\<añadir></span><span class="sxs-lookup"><span data-stu-id="63f4d-117">\<add></span></span>](add-of-participants.md)|<span data-ttu-id="63f4d-118">Contiene los valores para un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="63f4d-118">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="63f4d-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="63f4d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="63f4d-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="63f4d-120">Element</span></span>|<span data-ttu-id="63f4d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="63f4d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63f4d-122">\<seguimiento></span><span class="sxs-lookup"><span data-stu-id="63f4d-122">\<tracking></span></span>](tracking.md)|<span data-ttu-id="63f4d-123">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="63f4d-123">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63f4d-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="63f4d-124">Remarks</span></span>  
 <span data-ttu-id="63f4d-125">Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.</span><span class="sxs-lookup"><span data-stu-id="63f4d-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="63f4d-126">Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="63f4d-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="63f4d-127">Varios participantes de seguimiento pueden utilizar los eventos de seguimiento de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="63f4d-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="63f4d-128">Cada participante de seguimiento puede asociarse con un perfil de seguimiento distinto.</span><span class="sxs-lookup"><span data-stu-id="63f4d-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="63f4d-129">Se proporciona un participante de seguimiento estándar que escribe los registros de seguimiento en una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="63f4d-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="63f4d-130">El participante se configura en un servicio de flujo de trabajo agregando un comportamiento específico del seguimiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="63f4d-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="63f4d-131">Habilitar un participante de seguimiento de ETW permite realizar un seguimiento de los registros que se van a ver en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="63f4d-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="63f4d-132">Si eso no cumple sus requisitos, también puede escribir un participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="63f4d-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63f4d-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63f4d-133">Example</span></span>  
 <span data-ttu-id="63f4d-134">El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="63f4d-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="63f4d-135">El identificador de proveedor que el participante de seguimiento de ETW \*\* \<\*\* utiliza para escribir los registros de seguimiento en ETW se define en la sección de diagnóstico>.</span><span class="sxs-lookup"><span data-stu-id="63f4d-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="63f4d-136">El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="63f4d-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="63f4d-137">Esto se define mediante el atributo **profileName** del \*\* \<\*\* elemento add>.</span><span class="sxs-lookup"><span data-stu-id="63f4d-137">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="63f4d-138">Una vez definidos, el participante de seguimiento se agrega al comportamiento del servicio \*\* \<etwTracking>.\*\*</span><span class="sxs-lookup"><span data-stu-id="63f4d-138">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="63f4d-139">Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="63f4d-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="63f4d-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63f4d-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="63f4d-141">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="63f4d-141">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="63f4d-142">Seguimiento de los participantes</span><span class="sxs-lookup"><span data-stu-id="63f4d-142">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
