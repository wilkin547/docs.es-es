---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 4663ccedcafb6b151de75568afd3743c83c75224
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189830"
---
# \<activityStateQueries>

<span data-ttu-id="d5b87-101">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5b87-101">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="d5b87-102">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5b87-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="d5b87-103">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="d5b87-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="d5b87-104">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="d5b87-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="d5b87-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d5b87-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="d5b87-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5b87-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5b87-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d5b87-107">Attributes and Elements</span></span>  

 <span data-ttu-id="d5b87-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d5b87-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5b87-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5b87-109">Attributes</span></span>  

 <span data-ttu-id="d5b87-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d5b87-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d5b87-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d5b87-111">Child Elements</span></span>  
  
|<span data-ttu-id="d5b87-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5b87-112">Element</span></span>|<span data-ttu-id="d5b87-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5b87-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="d5b87-114">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="d5b87-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d5b87-115">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="d5b87-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5b87-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d5b87-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d5b87-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5b87-117">Element</span></span>|<span data-ttu-id="d5b87-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5b87-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="d5b87-119">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="d5b87-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5b87-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5b87-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d5b87-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d5b87-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d5b87-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d5b87-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
