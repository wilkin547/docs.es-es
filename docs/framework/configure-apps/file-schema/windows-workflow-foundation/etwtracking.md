---
description: 'Más información acerca de: <etwTracking>'
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: b89d832e73440d5b60a05477ccf85178c2f43a2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795084"
---
# \<etwTracking>

<span data-ttu-id="a5309-102">Un comportamiento del servicio que permite a un servicio usar el seguimiento de ETW utilizando un objeto <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="a5309-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**  
  
## <a name="syntax"></a><span data-ttu-id="a5309-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5309-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5309-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a5309-104">Attributes and Elements</span></span>  

 <span data-ttu-id="a5309-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a5309-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5309-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="a5309-106">Attributes</span></span>  
  
|<span data-ttu-id="a5309-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="a5309-107">Attribute</span></span>|<span data-ttu-id="a5309-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5309-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5309-109">profileName</span><span class="sxs-lookup"><span data-stu-id="a5309-109">profileName</span></span>|<span data-ttu-id="a5309-110">Una cadena que especifica el nombre del perfil de seguimiento asociado a este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a5309-110">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5309-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a5309-111">Child Elements</span></span>  

 <span data-ttu-id="a5309-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a5309-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5309-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a5309-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a5309-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5309-114">Element</span></span>|<span data-ttu-id="a5309-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5309-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5309-116">\<behavior> de \<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a5309-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="a5309-117">Especifica un elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a5309-117">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5309-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a5309-118">Remarks</span></span>  

 <span data-ttu-id="a5309-119">Cuando se agrega a la configuración de comportamiento del servicio, este elemento de configuración configura un participante de seguimiento en un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a5309-119">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="a5309-120">Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.</span><span class="sxs-lookup"><span data-stu-id="a5309-120">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="a5309-121">Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a5309-121">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5309-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5309-122">Example</span></span>  

 <span data-ttu-id="a5309-123">El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="a5309-123">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="a5309-124">El identificador de proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se define en la **\<diagnostics>** sección.</span><span class="sxs-lookup"><span data-stu-id="a5309-124">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="a5309-125">El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="a5309-125">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="a5309-126">Se define mediante el atributo **ProfileName** del **\<add>** elemento.</span><span class="sxs-lookup"><span data-stu-id="a5309-126">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="a5309-127">Una vez definidos, el participante de seguimiento se agrega al **\<etwTracking>** comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="a5309-127">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="a5309-128">Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a5309-128">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a5309-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5309-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="a5309-130">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a5309-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a5309-131">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a5309-131">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
