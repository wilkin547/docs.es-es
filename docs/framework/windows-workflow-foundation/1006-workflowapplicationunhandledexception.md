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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a03809be5e5d61c505e295e2f769a0298f770f7f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="48bda-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="48bda-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="48bda-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="48bda-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48bda-104">Id.</span><span class="sxs-lookup"><span data-stu-id="48bda-104">ID</span></span>|<span data-ttu-id="48bda-105">1006</span><span class="sxs-lookup"><span data-stu-id="48bda-105">1006</span></span>|  
|<span data-ttu-id="48bda-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="48bda-106">Keywords</span></span>|<span data-ttu-id="48bda-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="48bda-107">WFRuntime</span></span>|  
|<span data-ttu-id="48bda-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="48bda-108">Level</span></span>|<span data-ttu-id="48bda-109">Error</span><span class="sxs-lookup"><span data-stu-id="48bda-109">Error</span></span>|  
|<span data-ttu-id="48bda-110">Canal</span><span class="sxs-lookup"><span data-stu-id="48bda-110">Channel</span></span>|<span data-ttu-id="48bda-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="48bda-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48bda-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="48bda-112">Description</span></span>  
 <span data-ttu-id="48bda-113">Indica que una aplicación de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="48bda-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48bda-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="48bda-114">Message</span></span>  
 <span data-ttu-id="48bda-115">WorkflowInstance Id: '%1' ha encontrado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="48bda-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="48bda-116">La excepción que se originó desde la actividad '%2', DisplayName: '%3'.</span><span class="sxs-lookup"><span data-stu-id="48bda-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="48bda-117">Se realizará la acción siguiente: %4.</span><span class="sxs-lookup"><span data-stu-id="48bda-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="48bda-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="48bda-118">Details</span></span>  
  
|<span data-ttu-id="48bda-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="48bda-119">Data Item Name</span></span>|<span data-ttu-id="48bda-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="48bda-120">Data Item Type</span></span>|<span data-ttu-id="48bda-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="48bda-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48bda-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="48bda-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="48bda-123">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="48bda-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="48bda-124">Excepción</span><span class="sxs-lookup"><span data-stu-id="48bda-124">Exception</span></span>|`xs:string`|<span data-ttu-id="48bda-125">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="48bda-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="48bda-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="48bda-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="48bda-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="48bda-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
