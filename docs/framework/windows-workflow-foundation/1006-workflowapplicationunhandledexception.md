---
title: 1006 - WorkflowApplicationUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 842d6bb6172eed5f7382633119045ea7507fb955
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="91107-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="91107-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="91107-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="91107-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="91107-104">Id.</span><span class="sxs-lookup"><span data-stu-id="91107-104">ID</span></span>|<span data-ttu-id="91107-105">1006</span><span class="sxs-lookup"><span data-stu-id="91107-105">1006</span></span>|  
|<span data-ttu-id="91107-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="91107-106">Keywords</span></span>|<span data-ttu-id="91107-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="91107-107">WFRuntime</span></span>|  
|<span data-ttu-id="91107-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="91107-108">Level</span></span>|<span data-ttu-id="91107-109">Error</span><span class="sxs-lookup"><span data-stu-id="91107-109">Error</span></span>|  
|<span data-ttu-id="91107-110">Canal</span><span class="sxs-lookup"><span data-stu-id="91107-110">Channel</span></span>|<span data-ttu-id="91107-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="91107-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="91107-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="91107-112">Description</span></span>  
 <span data-ttu-id="91107-113">Indica que una aplicación de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="91107-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="91107-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="91107-114">Message</span></span>  
 <span data-ttu-id="91107-115">WorkflowInstance Id: '%1' ha encontrado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="91107-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="91107-116">La excepción que se originó desde la actividad '%2', DisplayName: '%3'.</span><span class="sxs-lookup"><span data-stu-id="91107-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="91107-117">Se realizará la acción siguiente: %4.</span><span class="sxs-lookup"><span data-stu-id="91107-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="91107-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="91107-118">Details</span></span>  
  
|<span data-ttu-id="91107-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="91107-119">Data Item Name</span></span>|<span data-ttu-id="91107-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="91107-120">Data Item Type</span></span>|<span data-ttu-id="91107-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="91107-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="91107-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="91107-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="91107-123">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="91107-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="91107-124">Excepción</span><span class="sxs-lookup"><span data-stu-id="91107-124">Exception</span></span>|`xs:string`|<span data-ttu-id="91107-125">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="91107-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="91107-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="91107-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="91107-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="91107-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
