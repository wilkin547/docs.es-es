---
description: 'Más información acerca de: 1003-WorkflowInstanceCanceled'
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: ef7b7c6849e96866204fe53deadce8302d18e0d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703373"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="aac2b-103">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="aac2b-103">1003 - WorkflowInstanceCanceled</span></span>

## <a name="properties"></a><span data-ttu-id="aac2b-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="aac2b-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aac2b-105">Id.</span><span class="sxs-lookup"><span data-stu-id="aac2b-105">ID</span></span>|<span data-ttu-id="aac2b-106">1003</span><span class="sxs-lookup"><span data-stu-id="aac2b-106">1003</span></span>|  
|<span data-ttu-id="aac2b-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="aac2b-107">Keywords</span></span>|<span data-ttu-id="aac2b-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="aac2b-108">WFRuntime</span></span>|  
|<span data-ttu-id="aac2b-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="aac2b-109">Level</span></span>|<span data-ttu-id="aac2b-110">Información</span><span class="sxs-lookup"><span data-stu-id="aac2b-110">Information</span></span>|  
|<span data-ttu-id="aac2b-111">Canal</span><span class="sxs-lookup"><span data-stu-id="aac2b-111">Channel</span></span>|<span data-ttu-id="aac2b-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="aac2b-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aac2b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="aac2b-113">Description</span></span>  

 <span data-ttu-id="aac2b-114">Indica que una instancia de flujo de trabajo ha finalizado en el estado Canceled.</span><span class="sxs-lookup"><span data-stu-id="aac2b-114">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aac2b-115">Message</span><span class="sxs-lookup"><span data-stu-id="aac2b-115">Message</span></span>  

 <span data-ttu-id="aac2b-116">WorkflowInstance Id: '%1' se completó en el estado Canceled.</span><span class="sxs-lookup"><span data-stu-id="aac2b-116">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aac2b-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="aac2b-117">Details</span></span>  
  
|<span data-ttu-id="aac2b-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="aac2b-118">Data Item Name</span></span>|<span data-ttu-id="aac2b-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="aac2b-119">Data Item Type</span></span>|<span data-ttu-id="aac2b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="aac2b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aac2b-121">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="aac2b-121">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="aac2b-122">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="aac2b-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="aac2b-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aac2b-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="aac2b-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aac2b-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
