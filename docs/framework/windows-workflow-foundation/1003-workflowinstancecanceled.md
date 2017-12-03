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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6930aeed8c3cd224d5d37dcecf357195e78390ed
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="9b788-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="9b788-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="9b788-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9b788-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9b788-104">Id.</span><span class="sxs-lookup"><span data-stu-id="9b788-104">ID</span></span>|<span data-ttu-id="9b788-105">1003</span><span class="sxs-lookup"><span data-stu-id="9b788-105">1003</span></span>|  
|<span data-ttu-id="9b788-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9b788-106">Keywords</span></span>|<span data-ttu-id="9b788-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9b788-107">WFRuntime</span></span>|  
|<span data-ttu-id="9b788-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="9b788-108">Level</span></span>|<span data-ttu-id="9b788-109">Información</span><span class="sxs-lookup"><span data-stu-id="9b788-109">Information</span></span>|  
|<span data-ttu-id="9b788-110">Canal</span><span class="sxs-lookup"><span data-stu-id="9b788-110">Channel</span></span>|<span data-ttu-id="9b788-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9b788-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9b788-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b788-112">Description</span></span>  
 <span data-ttu-id="9b788-113">Indica que una instancia de flujo de trabajo ha finalizado en el estado Canceled.</span><span class="sxs-lookup"><span data-stu-id="9b788-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9b788-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="9b788-114">Message</span></span>  
 <span data-ttu-id="9b788-115">WorkflowInstance Id: '%1' se completó en el estado Canceled.</span><span class="sxs-lookup"><span data-stu-id="9b788-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9b788-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="9b788-116">Details</span></span>  
  
|<span data-ttu-id="9b788-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9b788-117">Data Item Name</span></span>|<span data-ttu-id="9b788-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9b788-118">Data Item Type</span></span>|<span data-ttu-id="9b788-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b788-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9b788-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="9b788-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="9b788-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9b788-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="9b788-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9b788-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9b788-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9b788-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
