---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: c76a2dab6a95bda7f3969af07f814aba30071c7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509774"
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="fdec7-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="fdec7-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="fdec7-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fdec7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fdec7-104">Id.</span><span class="sxs-lookup"><span data-stu-id="fdec7-104">ID</span></span>|<span data-ttu-id="fdec7-105">1003</span><span class="sxs-lookup"><span data-stu-id="fdec7-105">1003</span></span>|  
|<span data-ttu-id="fdec7-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="fdec7-106">Keywords</span></span>|<span data-ttu-id="fdec7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fdec7-107">WFRuntime</span></span>|  
|<span data-ttu-id="fdec7-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="fdec7-108">Level</span></span>|<span data-ttu-id="fdec7-109">Información</span><span class="sxs-lookup"><span data-stu-id="fdec7-109">Information</span></span>|  
|<span data-ttu-id="fdec7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="fdec7-110">Channel</span></span>|<span data-ttu-id="fdec7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fdec7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fdec7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdec7-112">Description</span></span>  
 <span data-ttu-id="fdec7-113">Indica que una instancia de flujo de trabajo ha finalizado en el estado Canceled.</span><span class="sxs-lookup"><span data-stu-id="fdec7-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fdec7-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="fdec7-114">Message</span></span>  
 <span data-ttu-id="fdec7-115">WorkflowInstance Id: '%1' se completó en el estado Canceled.</span><span class="sxs-lookup"><span data-stu-id="fdec7-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fdec7-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="fdec7-116">Details</span></span>  
  
|<span data-ttu-id="fdec7-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fdec7-117">Data Item Name</span></span>|<span data-ttu-id="fdec7-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fdec7-118">Data Item Type</span></span>|<span data-ttu-id="fdec7-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdec7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fdec7-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="fdec7-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="fdec7-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdec7-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="fdec7-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fdec7-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fdec7-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fdec7-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
