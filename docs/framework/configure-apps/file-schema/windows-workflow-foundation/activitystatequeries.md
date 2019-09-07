---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 58e3752be81609e32eee631e46d10c0a7d704248
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398955"
---
# <a name="activitystatequeries"></a><span data-ttu-id="ccbfc-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="ccbfc-101">\<activityStateQueries></span></span>
<span data-ttu-id="ccbfc-102">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ccbfc-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="ccbfc-103">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ccbfc-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="ccbfc-104">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="ccbfc-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="ccbfc-105">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="ccbfc-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="ccbfc-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ccbfc-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ccbfc-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ccbfc-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ccbfc-108">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ccbfc-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="ccbfc-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="ccbfc-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="ccbfc-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="ccbfc-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="ccbfc-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="ccbfc-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="ccbfc-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityStateQueries**</span><span class="sxs-lookup"><span data-stu-id="ccbfc-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccbfc-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ccbfc-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ccbfc-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ccbfc-114">Attributes and Elements</span></span>  
 <span data-ttu-id="ccbfc-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ccbfc-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ccbfc-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="ccbfc-116">Attributes</span></span>  
 <span data-ttu-id="ccbfc-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ccbfc-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ccbfc-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ccbfc-118">Child Elements</span></span>  
  
|<span data-ttu-id="ccbfc-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ccbfc-119">Element</span></span>|<span data-ttu-id="ccbfc-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ccbfc-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccbfc-121">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ccbfc-121">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="ccbfc-122">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="ccbfc-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="ccbfc-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="ccbfc-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ccbfc-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ccbfc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ccbfc-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="ccbfc-125">Element</span></span>|<span data-ttu-id="ccbfc-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ccbfc-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ccbfc-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ccbfc-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="ccbfc-128">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="ccbfc-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ccbfc-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ccbfc-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ccbfc-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="ccbfc-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ccbfc-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ccbfc-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
