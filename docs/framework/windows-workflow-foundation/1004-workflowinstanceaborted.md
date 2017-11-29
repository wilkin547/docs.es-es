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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7394ebbcb14850af89d906b0b573c4f677346825
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="0ea7e-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="0ea7e-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="0ea7e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0ea7e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ea7e-104">Id.</span><span class="sxs-lookup"><span data-stu-id="0ea7e-104">ID</span></span>|<span data-ttu-id="0ea7e-105">1004</span><span class="sxs-lookup"><span data-stu-id="0ea7e-105">1004</span></span>|  
|<span data-ttu-id="0ea7e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0ea7e-106">Keywords</span></span>|<span data-ttu-id="0ea7e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0ea7e-107">WFRuntime</span></span>|  
|<span data-ttu-id="0ea7e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0ea7e-108">Level</span></span>|<span data-ttu-id="0ea7e-109">Información</span><span class="sxs-lookup"><span data-stu-id="0ea7e-109">Information</span></span>|  
|<span data-ttu-id="0ea7e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0ea7e-110">Channel</span></span>|<span data-ttu-id="0ea7e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0ea7e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0ea7e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ea7e-112">Description</span></span>  
 <span data-ttu-id="0ea7e-113">Indica que una instancia de flujo de trabajo se ha anulado con una excepción.</span><span class="sxs-lookup"><span data-stu-id="0ea7e-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0ea7e-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0ea7e-114">Message</span></span>  
 <span data-ttu-id="0ea7e-115">WorkflowInstance Id: '%1' se anuló con una excepción.</span><span class="sxs-lookup"><span data-stu-id="0ea7e-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0ea7e-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="0ea7e-116">Details</span></span>  
  
|<span data-ttu-id="0ea7e-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0ea7e-117">Data Item Name</span></span>|<span data-ttu-id="0ea7e-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0ea7e-118">Data Item Type</span></span>|<span data-ttu-id="0ea7e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ea7e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0ea7e-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="0ea7e-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="0ea7e-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0ea7e-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="0ea7e-122">Excepción</span><span class="sxs-lookup"><span data-stu-id="0ea7e-122">Exception</span></span>|`xs:string`|<span data-ttu-id="0ea7e-123">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="0ea7e-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="0ea7e-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0ea7e-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0ea7e-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0ea7e-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
