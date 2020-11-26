---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: bd8abf173ab6588d4a35ba59c6cd14fb53445e9f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239905"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="1e471-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="1e471-102">1003 - WorkflowInstanceCanceled</span></span>

## <a name="properties"></a><span data-ttu-id="1e471-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1e471-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e471-104">ID</span><span class="sxs-lookup"><span data-stu-id="1e471-104">ID</span></span>|<span data-ttu-id="1e471-105">1003</span><span class="sxs-lookup"><span data-stu-id="1e471-105">1003</span></span>|  
|<span data-ttu-id="1e471-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1e471-106">Keywords</span></span>|<span data-ttu-id="1e471-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1e471-107">WFRuntime</span></span>|  
|<span data-ttu-id="1e471-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="1e471-108">Level</span></span>|<span data-ttu-id="1e471-109">Información</span><span class="sxs-lookup"><span data-stu-id="1e471-109">Information</span></span>|  
|<span data-ttu-id="1e471-110">Canal</span><span class="sxs-lookup"><span data-stu-id="1e471-110">Channel</span></span>|<span data-ttu-id="1e471-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="1e471-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1e471-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e471-112">Description</span></span>  

 <span data-ttu-id="1e471-113">Indica que una instancia de flujo de trabajo ha finalizado en el estado Canceled.</span><span class="sxs-lookup"><span data-stu-id="1e471-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1e471-114">Message</span><span class="sxs-lookup"><span data-stu-id="1e471-114">Message</span></span>  

 <span data-ttu-id="1e471-115">WorkflowInstance Id: '%1' se completó en el estado Canceled.</span><span class="sxs-lookup"><span data-stu-id="1e471-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1e471-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="1e471-116">Details</span></span>  
  
|<span data-ttu-id="1e471-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="1e471-117">Data Item Name</span></span>|<span data-ttu-id="1e471-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="1e471-118">Data Item Type</span></span>|<span data-ttu-id="1e471-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e471-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1e471-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="1e471-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="1e471-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1e471-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="1e471-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1e471-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1e471-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1e471-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
