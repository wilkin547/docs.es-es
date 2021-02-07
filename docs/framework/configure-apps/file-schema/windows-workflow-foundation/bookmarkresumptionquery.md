---
description: 'Más información acerca de: <bookmarkResumptionQuery>'
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 4e6637b6edd54d9c1cf1a44986b362eb616bf14d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725251"
---
# \<bookmarkResumptionQuery>

<span data-ttu-id="76619-102">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="76619-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="76619-103">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="76619-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="76619-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="76619-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="76619-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76619-105">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76619-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="76619-106">Attributes and Elements</span></span>  

 <span data-ttu-id="76619-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="76619-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76619-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="76619-108">Attributes</span></span>  
  
|<span data-ttu-id="76619-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="76619-109">Attribute</span></span>|<span data-ttu-id="76619-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="76619-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76619-111">name</span><span class="sxs-lookup"><span data-stu-id="76619-111">name</span></span>|<span data-ttu-id="76619-112">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="76619-112">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76619-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="76619-113">Child Elements</span></span>  

 <span data-ttu-id="76619-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="76619-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76619-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="76619-115">Parent Elements</span></span>  
  
|<span data-ttu-id="76619-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="76619-116">Element</span></span>|<span data-ttu-id="76619-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="76619-117">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="76619-118">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="76619-118">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76619-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="76619-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="76619-120">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="76619-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="76619-121">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="76619-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
