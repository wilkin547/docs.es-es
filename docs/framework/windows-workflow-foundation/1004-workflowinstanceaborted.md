---
title: 1004 - WorkflowInstanceAborted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc940e1781f821f12efb42c5198e77eb0451a164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="63220-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="63220-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="63220-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="63220-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="63220-104">Id.</span><span class="sxs-lookup"><span data-stu-id="63220-104">ID</span></span>|<span data-ttu-id="63220-105">1004</span><span class="sxs-lookup"><span data-stu-id="63220-105">1004</span></span>|  
|<span data-ttu-id="63220-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="63220-106">Keywords</span></span>|<span data-ttu-id="63220-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="63220-107">WFRuntime</span></span>|  
|<span data-ttu-id="63220-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="63220-108">Level</span></span>|<span data-ttu-id="63220-109">Información</span><span class="sxs-lookup"><span data-stu-id="63220-109">Information</span></span>|  
|<span data-ttu-id="63220-110">Canal</span><span class="sxs-lookup"><span data-stu-id="63220-110">Channel</span></span>|<span data-ttu-id="63220-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="63220-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="63220-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="63220-112">Description</span></span>  
 <span data-ttu-id="63220-113">Indica que una instancia de flujo de trabajo se ha anulado con una excepción.</span><span class="sxs-lookup"><span data-stu-id="63220-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="63220-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="63220-114">Message</span></span>  
 <span data-ttu-id="63220-115">WorkflowInstance Id: '%1' se anuló con una excepción.</span><span class="sxs-lookup"><span data-stu-id="63220-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="63220-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="63220-116">Details</span></span>  
  
|<span data-ttu-id="63220-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="63220-117">Data Item Name</span></span>|<span data-ttu-id="63220-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="63220-118">Data Item Type</span></span>|<span data-ttu-id="63220-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="63220-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="63220-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="63220-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="63220-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="63220-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="63220-122">Excepción</span><span class="sxs-lookup"><span data-stu-id="63220-122">Exception</span></span>|`xs:string`|<span data-ttu-id="63220-123">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="63220-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="63220-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="63220-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="63220-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="63220-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
