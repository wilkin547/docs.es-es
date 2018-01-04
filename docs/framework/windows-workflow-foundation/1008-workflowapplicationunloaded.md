---
title: 1008 - WorkflowApplicationUnloaded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26491c1e2b20f4285aaedbcd12947cad3562f041
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="5dcd7-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="5dcd7-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="5dcd7-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5dcd7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5dcd7-104">Id.</span><span class="sxs-lookup"><span data-stu-id="5dcd7-104">ID</span></span>|<span data-ttu-id="5dcd7-105">1008</span><span class="sxs-lookup"><span data-stu-id="5dcd7-105">1008</span></span>|  
|<span data-ttu-id="5dcd7-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5dcd7-106">Keywords</span></span>|<span data-ttu-id="5dcd7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5dcd7-107">WFRuntime</span></span>|  
|<span data-ttu-id="5dcd7-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="5dcd7-108">Level</span></span>|<span data-ttu-id="5dcd7-109">Información</span><span class="sxs-lookup"><span data-stu-id="5dcd7-109">Information</span></span>|  
|<span data-ttu-id="5dcd7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5dcd7-110">Channel</span></span>|<span data-ttu-id="5dcd7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5dcd7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5dcd7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5dcd7-112">Description</span></span>  
 <span data-ttu-id="5dcd7-113">Indica que una aplicación de flujo de trabajo se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="5dcd7-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5dcd7-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="5dcd7-114">Message</span></span>  
 <span data-ttu-id="5dcd7-115">WorkflowInstance Id: '%1' se descargó.</span><span class="sxs-lookup"><span data-stu-id="5dcd7-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5dcd7-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="5dcd7-116">Details</span></span>  
  
|<span data-ttu-id="5dcd7-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5dcd7-117">Data Item Name</span></span>|<span data-ttu-id="5dcd7-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5dcd7-118">Data Item Type</span></span>|<span data-ttu-id="5dcd7-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5dcd7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5dcd7-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="5dcd7-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="5dcd7-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5dcd7-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="5dcd7-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5dcd7-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5dcd7-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5dcd7-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
