---
description: 'Más información sobre: <activityStateQuery> de WCF'
title: <activityStateQuery> de WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: fff8f6ac793df9b0a355dfbed859b3a88178002a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725927"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="5cd81-103">\<activityStateQuery> de WCF</span><span class="sxs-lookup"><span data-stu-id="5cd81-103">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="5cd81-104">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5cd81-104">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="5cd81-105">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5cd81-105">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="5cd81-106">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="5cd81-106">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="5cd81-107">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="5cd81-107">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="5cd81-108">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5cd81-108">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="5cd81-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5cd81-109">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cd81-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5cd81-110">Attributes and elements</span></span>  

<span data-ttu-id="5cd81-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5cd81-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cd81-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5cd81-112">Attributes</span></span>  
  
|<span data-ttu-id="5cd81-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5cd81-113">Attribute</span></span>|<span data-ttu-id="5cd81-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cd81-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5cd81-115">activityName</span><span class="sxs-lookup"><span data-stu-id="5cd81-115">activityName</span></span>|<span data-ttu-id="5cd81-116">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="5cd81-116">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cd81-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5cd81-117">Child elements</span></span>  
  
|<span data-ttu-id="5cd81-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5cd81-118">Element</span></span>|<span data-ttu-id="5cd81-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cd81-119">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="5cd81-120">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="5cd81-120">A collection of arguments associated with this activity query.</span></span>|  
|[\<states>](../windows-workflow-foundation/states.md)|<span data-ttu-id="5cd81-121">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5cd81-121">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[\<states>](../windows-workflow-foundation/states.md)|<span data-ttu-id="5cd81-122">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="5cd81-122">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5cd81-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5cd81-123">Parent elements</span></span>  
  
|<span data-ttu-id="5cd81-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5cd81-124">Element</span></span>|<span data-ttu-id="5cd81-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5cd81-125">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="5cd81-126">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="5cd81-126">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="5cd81-127">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="5cd81-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cd81-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5cd81-128">Remarks</span></span>

<span data-ttu-id="5cd81-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5cd81-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="5cd81-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="5cd81-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="5cd81-131">Puede usar los [\<arguments>](../windows-workflow-foundation/arguments.md) elementos, [\<states>](../windows-workflow-foundation/states.md) y [\<states>](../windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5cd81-131">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="5cd81-132">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="5cd81-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="5cd81-133">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por tanto, se suscriben a dentro de un perfil de seguimiento mediante [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="5cd81-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="5cd81-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5cd81-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="5cd81-135">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5cd81-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5cd81-136">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5cd81-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
