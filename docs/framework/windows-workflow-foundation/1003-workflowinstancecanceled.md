---
title: 1003 - WorkflowInstanceCanceled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b287c99453724f855a51e9a1b8068337dd5e373
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="ccd3a-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="ccd3a-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="ccd3a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ccd3a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ccd3a-104">Id.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-104">ID</span></span>|<span data-ttu-id="ccd3a-105">1003</span><span class="sxs-lookup"><span data-stu-id="ccd3a-105">1003</span></span>|  
|<span data-ttu-id="ccd3a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ccd3a-106">Keywords</span></span>|<span data-ttu-id="ccd3a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ccd3a-107">WFRuntime</span></span>|  
|<span data-ttu-id="ccd3a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ccd3a-108">Level</span></span>|<span data-ttu-id="ccd3a-109">Información</span><span class="sxs-lookup"><span data-stu-id="ccd3a-109">Information</span></span>|  
|<span data-ttu-id="ccd3a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ccd3a-110">Channel</span></span>|<span data-ttu-id="ccd3a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ccd3a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ccd3a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccd3a-112">Description</span></span>  
 <span data-ttu-id="ccd3a-113">Indica que una instancia de flujo de trabajo ha finalizado en el estado Canceled.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ccd3a-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ccd3a-114">Message</span></span>  
 <span data-ttu-id="ccd3a-115">WorkflowInstance Id: '%1' se completó en el estado Canceled.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ccd3a-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="ccd3a-116">Details</span></span>  
  
|<span data-ttu-id="ccd3a-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ccd3a-117">Data Item Name</span></span>|<span data-ttu-id="ccd3a-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ccd3a-118">Data Item Type</span></span>|<span data-ttu-id="ccd3a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ccd3a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ccd3a-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="ccd3a-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="ccd3a-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="ccd3a-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ccd3a-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ccd3a-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
