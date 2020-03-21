---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: d562bd4e3d46a1bdf41fc4065fee926850a49aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152176"
---
# <a name="etwtracking"></a><span data-ttu-id="3c60a-101">\<etwTracking></span><span class="sxs-lookup"><span data-stu-id="3c60a-101">\<etwTracking></span></span>
<span data-ttu-id="3c60a-102">Un comportamiento del servicio que permite a un servicio usar el seguimiento de ETW utilizando un objeto <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="3c60a-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
<span data-ttu-id="3c60a-103">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3c60a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3c60a-104">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3c60a-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="3c60a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamientos>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3c60a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="3c60a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3c60a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="3c60a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comportamiento>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3c60a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="3c60a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**</span><span class="sxs-lookup"><span data-stu-id="3c60a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c60a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c60a-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c60a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3c60a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3c60a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3c60a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c60a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="3c60a-112">Attributes</span></span>  
  
|<span data-ttu-id="3c60a-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="3c60a-113">Attribute</span></span>|<span data-ttu-id="3c60a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c60a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3c60a-115">profileName</span><span class="sxs-lookup"><span data-stu-id="3c60a-115">profileName</span></span>|<span data-ttu-id="3c60a-116">Una cadena que especifica el nombre del perfil de seguimiento asociado a este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3c60a-116">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c60a-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3c60a-117">Child Elements</span></span>  
 <span data-ttu-id="3c60a-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3c60a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c60a-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c60a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3c60a-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c60a-120">Element</span></span>|<span data-ttu-id="3c60a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c60a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c60a-122">\<comportamiento> \<de serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="3c60a-122">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="3c60a-123">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3c60a-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c60a-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c60a-124">Remarks</span></span>  
 <span data-ttu-id="3c60a-125">Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración configura un participante de seguimiento en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3c60a-125">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="3c60a-126">Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.</span><span class="sxs-lookup"><span data-stu-id="3c60a-126">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="3c60a-127">Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3c60a-127">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c60a-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c60a-128">Example</span></span>  
 <span data-ttu-id="3c60a-129">El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="3c60a-129">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="3c60a-130">El identificador de proveedor que el participante de seguimiento de ETW \*\* \<\*\* utiliza para escribir los registros de seguimiento en ETW se define en la sección de diagnóstico>.</span><span class="sxs-lookup"><span data-stu-id="3c60a-130">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="3c60a-131">El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="3c60a-131">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="3c60a-132">Esto se define mediante el atributo **profileName** del \*\* \<\*\* elemento add>.</span><span class="sxs-lookup"><span data-stu-id="3c60a-132">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="3c60a-133">Una vez definidos, el participante de seguimiento se agrega al comportamiento del servicio \*\* \<etwTracking>.\*\*</span><span class="sxs-lookup"><span data-stu-id="3c60a-133">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="3c60a-134">Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3c60a-134">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3c60a-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c60a-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="3c60a-136">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3c60a-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3c60a-137">Seguimiento de los participantes</span><span class="sxs-lookup"><span data-stu-id="3c60a-137">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
