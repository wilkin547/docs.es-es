---
title: <add> de <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c730850-6f8e-4102-acb8-8effb4e09463
ms.openlocfilehash: 84177f62e6f1ce0cb89bdf85e1ba5a2a1e82fa21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189804"
---
# <a name="add-of-participants"></a><span data-ttu-id="a18dd-102">\<add> de \<participants></span><span class="sxs-lookup"><span data-stu-id="a18dd-102">\<add> of \<participants></span></span>

<span data-ttu-id="a18dd-103">Configure un participante del seguimiento que escucha los registros de seguimiento que se emiten del tiempo de ejecución directamente y los procesa del modo en que cada uno esté configurado.</span><span class="sxs-lookup"><span data-stu-id="a18dd-103">Configure a tracking participant that listens to the tracking records being emitted from the runtime directly and process them in whatever way it was configured.</span></span> <span data-ttu-id="a18dd-104">Esto incluye la escritura en un resultado concreto (p. ej., un archivo, la consola o ETW), procesar o agregar los registros, o cualquier otra combinación que pueda resultar necesaria.</span><span class="sxs-lookup"><span data-stu-id="a18dd-104">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="a18dd-105">Para obtener más información sobre los participantes de seguimiento y seguimiento de flujos de trabajo, vea seguimiento y seguimiento de [flujos de trabajo](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) y [participantes](../../../windows-workflow-foundation/tracking-participants.md)de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a18dd-105">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<participants>**](participants.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="a18dd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a18dd-106">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String" profileName="String" type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a18dd-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a18dd-107">Attributes and Elements</span></span>  

 <span data-ttu-id="a18dd-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a18dd-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a18dd-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a18dd-109">Attributes</span></span>  
  
|<span data-ttu-id="a18dd-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="a18dd-110">Element</span></span>|<span data-ttu-id="a18dd-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a18dd-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a18dd-112">name</span><span class="sxs-lookup"><span data-stu-id="a18dd-112">name</span></span>|<span data-ttu-id="a18dd-113">Cadena que especifica el nombre de un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a18dd-113">A string that specifies the name of a tracking participant.</span></span>|  
|<span data-ttu-id="a18dd-114">profileName</span><span class="sxs-lookup"><span data-stu-id="a18dd-114">profileName</span></span>|<span data-ttu-id="a18dd-115">Una cadena que especifica el nombre del perfil de seguimiento que define los registros de seguimiento a los que se ha suscrito el participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a18dd-115">A string that specifies the name of the tracking profile which defines the tracking records the tracking participant has subscribed to.</span></span>|  
|<span data-ttu-id="a18dd-116">type</span><span class="sxs-lookup"><span data-stu-id="a18dd-116">type</span></span>|<span data-ttu-id="a18dd-117">Una cadena que especifica el tipo de un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a18dd-117">A string that specifies the type of a tracking participant.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a18dd-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a18dd-118">Child Elements</span></span>  

 <span data-ttu-id="a18dd-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a18dd-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a18dd-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a18dd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a18dd-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="a18dd-121">Element</span></span>|<span data-ttu-id="a18dd-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="a18dd-122">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](participants.md)|<span data-ttu-id="a18dd-123">Una lista de los participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a18dd-123">A list of tracking participants</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a18dd-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a18dd-124">Remarks</span></span>  

 <span data-ttu-id="a18dd-125">Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.</span><span class="sxs-lookup"><span data-stu-id="a18dd-125">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="a18dd-126">Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a18dd-126">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="a18dd-127">Varios participantes de seguimiento pueden utilizar los eventos de seguimiento de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="a18dd-127">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="a18dd-128">Cada participante de seguimiento puede asociarse con un perfil de seguimiento distinto.</span><span class="sxs-lookup"><span data-stu-id="a18dd-128">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="a18dd-129">Se proporciona un participante de seguimiento estándar que escribe los registros de seguimiento en una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="a18dd-129">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="a18dd-130">El participante se configura en un servicio de flujo de trabajo agregando un comportamiento específico del seguimiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a18dd-130">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="a18dd-131">Habilitar un participante de seguimiento de ETW permite realizar un seguimiento de los registros que se van a ver en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="a18dd-131">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="a18dd-132">Si eso no cumple sus requisitos, también puede escribir un participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="a18dd-132">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a18dd-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a18dd-133">Example</span></span>  

 <span data-ttu-id="a18dd-134">El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="a18dd-134">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="a18dd-135">El identificador de proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se define en la **\<diagnostics>** sección.</span><span class="sxs-lookup"><span data-stu-id="a18dd-135">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="a18dd-136">El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="a18dd-136">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="a18dd-137">Se define mediante el atributo **ProfileName** del **\<add>** elemento.</span><span class="sxs-lookup"><span data-stu-id="a18dd-137">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="a18dd-138">Una vez definidos, el participante de seguimiento se agrega al **\<etwTracking>** comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="a18dd-138">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="a18dd-139">Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a18dd-139">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a18dd-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a18dd-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="a18dd-141">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a18dd-141">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a18dd-142">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a18dd-142">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
