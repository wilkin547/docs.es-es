---
description: 'Más información acerca de: <activityStateQueries>'
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: ad324d88c481016d85b8e58ccc0857b7773d8328
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748965"
---
# \<activityStateQueries>

<span data-ttu-id="fc6fa-102">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="fc6fa-103">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="fc6fa-104">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="fc6fa-105">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="fc6fa-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="fc6fa-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="fc6fa-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc6fa-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc6fa-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc6fa-108">Attributes and Elements</span></span>  

 <span data-ttu-id="fc6fa-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc6fa-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc6fa-110">Attributes</span></span>  

 <span data-ttu-id="fc6fa-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fc6fa-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc6fa-112">Child Elements</span></span>  
  
|<span data-ttu-id="fc6fa-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc6fa-113">Element</span></span>|<span data-ttu-id="fc6fa-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc6fa-114">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="fc6fa-115">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-115">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="fc6fa-116">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="fc6fa-116">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc6fa-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc6fa-117">Parent Elements</span></span>  
  
|<span data-ttu-id="fc6fa-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc6fa-118">Element</span></span>|<span data-ttu-id="fc6fa-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc6fa-119">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="fc6fa-120">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="fc6fa-120">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc6fa-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc6fa-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fc6fa-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="fc6fa-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fc6fa-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fc6fa-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
