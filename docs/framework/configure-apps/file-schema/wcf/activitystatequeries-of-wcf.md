---
description: 'Más información sobre: <activityStateQueries> de WCF'
title: <activityStateQueries> de WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 00795a26a37f62fae8aa884b5a4188be79453186
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782239"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="0915b-103">\<activityStateQueries> de WCF</span><span class="sxs-lookup"><span data-stu-id="0915b-103">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="0915b-104">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0915b-104">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="0915b-105">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0915b-105">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="0915b-106">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="0915b-106">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="0915b-107">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="0915b-107">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="0915b-108">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0915b-108">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="0915b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0915b-109">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="0915b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0915b-110">Attributes and elements</span></span>

<span data-ttu-id="0915b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0915b-111">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="0915b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="0915b-112">Attributes</span></span>  

<span data-ttu-id="0915b-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0915b-113">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="0915b-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0915b-114">Child elements</span></span>

|<span data-ttu-id="0915b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="0915b-115">Element</span></span>|<span data-ttu-id="0915b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="0915b-116">Description</span></span>|
|-------------|-----------------|
|[\<activityStateQuery>](activitystatequery-of-wcf.md)|<span data-ttu-id="0915b-117">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="0915b-117">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0915b-118">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="0915b-118">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0915b-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0915b-119">Parent elements</span></span>

|<span data-ttu-id="0915b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="0915b-120">Element</span></span>|<span data-ttu-id="0915b-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="0915b-121">Description</span></span>|
|-------------|-----------------|
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="0915b-122">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="0915b-122">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="0915b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="0915b-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="0915b-124">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="0915b-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0915b-125">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0915b-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
