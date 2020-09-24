---
title: <participants>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
ms.openlocfilehash: 51c7824a4dcbd95eac098d25e9a971514e2a1e0b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167046"
---
# \<participants>

<span data-ttu-id="8ae9a-101">Configure una lista de participantes de seguimiento que escuchen los registros de seguimiento que se emiten desde el tiempo de ejecución directamente y los procesan del modo en que cada uno esté configurado.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-101">Configure a list of tracking participants that listen to the tracking records being emitted from the runtime directly and process them in whatever way they are configured.</span></span> <span data-ttu-id="8ae9a-102">Esto incluye la escritura en un resultado concreto (p. ej., un archivo, la consola o ETW), procesar o agregar los registros, o cualquier otra combinación que pueda resultar necesaria.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-102">This includes writing to a specific output (e.g., file, Console, ETW), processing/aggregating the records, or any other combination that might be required.</span></span>  
  
 <span data-ttu-id="8ae9a-103">Para obtener más información sobre los participantes de seguimiento y seguimiento de flujos de trabajo, vea seguimiento y seguimiento de [flujos de trabajo](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) y [participantes](../../../windows-workflow-foundation/tracking-participants.md)de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-103">For more information in workflow tracking and tracking participants, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Participants](../../../windows-workflow-foundation/tracking-participants.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<participants>**  
  
## <a name="syntax"></a><span data-ttu-id="8ae9a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ae9a-104">Syntax</span></span>  
  
```xml
<tracking>
  <participants>
    <add name="String"
         profileName="String"
         type="String" />
  </participants>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ae9a-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8ae9a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8ae9a-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ae9a-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="8ae9a-107">Attributes</span></span>  

 <span data-ttu-id="8ae9a-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8ae9a-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8ae9a-109">Child Elements</span></span>  
  
|<span data-ttu-id="8ae9a-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ae9a-110">Element</span></span>|<span data-ttu-id="8ae9a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ae9a-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-participants.md)|<span data-ttu-id="8ae9a-112">Contiene los valores para un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-112">Contains settings for a tracking participant.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ae9a-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8ae9a-113">Parent Elements</span></span>  
  
|<span data-ttu-id="8ae9a-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ae9a-114">Element</span></span>|<span data-ttu-id="8ae9a-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ae9a-115">Description</span></span>|  
|-------------|-----------------|  
|[\<tracking>](tracking.md)|<span data-ttu-id="8ae9a-116">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-116">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ae9a-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8ae9a-117">Remarks</span></span>  

 <span data-ttu-id="8ae9a-118">Los participantes de seguimiento se usan para obtener los datos de seguimiento emitidos del flujo de trabajo y almacenarlos en los distintos medios.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-118">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="8ae9a-119">Del mismo modo, cualquier procesamiento posterior en los Registros de seguimiento también puede realizarse dentro del participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-119">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
 <span data-ttu-id="8ae9a-120">Varios participantes de seguimiento pueden utilizar los eventos de seguimiento de forma simultánea.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-120">Multiple tracking participants can consume the tracking events simultaneously.</span></span> <span data-ttu-id="8ae9a-121">Cada participante de seguimiento puede asociarse con un perfil de seguimiento distinto.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-121">Each tracking participant can be associated with a different tracking profile.</span></span>  
  
 <span data-ttu-id="8ae9a-122">Se proporciona un participante de seguimiento estándar que escribe los registros de seguimiento en una sesión de ETW.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-122">A standard tracking participant is provided which writes the tracking records to an ETW session.</span></span> <span data-ttu-id="8ae9a-123">El participante se configura en un servicio de flujo de trabajo agregando un comportamiento específico del seguimiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-123">The participant is configured on a workflow service by adding a tracking-specific behavior in a configuration file.</span></span> <span data-ttu-id="8ae9a-124">Habilitar un participante de seguimiento de ETW permite realizar un seguimiento de los registros que se van a ver en el visor de eventos.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-124">Enabling an ETW tracking participant allows tracking records to be viewed in the event viewer.</span></span> <span data-ttu-id="8ae9a-125">Si eso no cumple sus requisitos, también puede escribir un participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-125">If that does not meet your requirements, you can also write a custom tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ae9a-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ae9a-126">Example</span></span>  

 <span data-ttu-id="8ae9a-127">El siguiente ejemplo de configuración muestra el participante de seguimiento de ETW estándar que se está configurando en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-127">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="8ae9a-128">El identificador de proveedor que el participante de seguimiento de ETW usa para escribir los registros de seguimiento en ETW se define en la **\<diagnostics>** sección.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-128">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="8ae9a-129">El participante de seguimiento tiene un perfil asociado para especificar los registros de seguimiento a los que se ha suscrito.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-129">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="8ae9a-130">Se define mediante el atributo **ProfileName** del **\<add>** elemento.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-130">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="8ae9a-131">Una vez definidos, el participante de seguimiento se agrega al **\<etwTracking>** comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-131">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="8ae9a-132">Esto agregará los participantes de seguimiento seleccionados a las extensiones de la instancia de flujo de trabajo para que puedan empezar a recibir los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8ae9a-132">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8ae9a-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ae9a-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>
- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="8ae9a-134">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="8ae9a-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8ae9a-135">Participantes de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8ae9a-135">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
