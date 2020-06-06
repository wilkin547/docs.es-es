---
title: <faultPropagationQueries>de WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855267"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="38820-102">\<faultPropagationQueries>de WCF</span><span class="sxs-lookup"><span data-stu-id="38820-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="38820-103">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="38820-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="38820-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="38820-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="38820-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="38820-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="38820-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="38820-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="38820-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="38820-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="38820-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38820-108">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38820-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="38820-109">Attributes and elements</span></span>

<span data-ttu-id="38820-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="38820-110">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="38820-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="38820-111">Attributes</span></span>

<span data-ttu-id="38820-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="38820-112">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="38820-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="38820-113">Child elements</span></span>

|<span data-ttu-id="38820-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="38820-114">Element</span></span>|<span data-ttu-id="38820-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="38820-115">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="38820-116">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="38820-116">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="38820-117">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="38820-117">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38820-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="38820-118">Parent elements</span></span>  
  
|<span data-ttu-id="38820-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="38820-119">Element</span></span>|<span data-ttu-id="38820-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="38820-120">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="38820-121">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="38820-121">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38820-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38820-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="38820-123">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="38820-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="38820-124">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="38820-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
