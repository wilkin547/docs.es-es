---
title: <activityStateQueries>de WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 249ac3d91f6251a943dd856e4122b8b54f691702
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850575"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="6f04b-102">\<activityStateQueries>de WCF</span><span class="sxs-lookup"><span data-stu-id="6f04b-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="6f04b-103">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6f04b-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="6f04b-104">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6f04b-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="6f04b-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="6f04b-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="6f04b-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="6f04b-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="6f04b-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6f04b-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="6f04b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f04b-108">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="6f04b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6f04b-109">Attributes and elements</span></span>

<span data-ttu-id="6f04b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6f04b-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="6f04b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="6f04b-111">Attributes</span></span>  

<span data-ttu-id="6f04b-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6f04b-112">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="6f04b-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6f04b-113">Child elements</span></span>

|<span data-ttu-id="6f04b-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f04b-114">Element</span></span>|<span data-ttu-id="6f04b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f04b-115">Description</span></span>|
|-------------|-----------------|
|[\<activityStateQuery>](activitystatequery-of-wcf.md)|<span data-ttu-id="6f04b-116">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="6f04b-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="6f04b-117">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="6f04b-117">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6f04b-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6f04b-118">Parent elements</span></span>

|<span data-ttu-id="6f04b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f04b-119">Element</span></span>|<span data-ttu-id="6f04b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f04b-120">Description</span></span>|
|-------------|-----------------|
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="6f04b-121">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="6f04b-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="6f04b-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6f04b-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="6f04b-123">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6f04b-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6f04b-124">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6f04b-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
