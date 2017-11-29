---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 54ef06c3aded628e18325b78f55e80e4470ecd01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="ca345-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="ca345-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="ca345-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ca345-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ca345-104">Id.</span><span class="sxs-lookup"><span data-stu-id="ca345-104">ID</span></span>|<span data-ttu-id="ca345-105">1002</span><span class="sxs-lookup"><span data-stu-id="ca345-105">1002</span></span>|  
|<span data-ttu-id="ca345-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ca345-106">Keywords</span></span>|<span data-ttu-id="ca345-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ca345-107">WFRuntime</span></span>|  
|<span data-ttu-id="ca345-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ca345-108">Level</span></span>|<span data-ttu-id="ca345-109">Información</span><span class="sxs-lookup"><span data-stu-id="ca345-109">Information</span></span>|  
|<span data-ttu-id="ca345-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ca345-110">Channel</span></span>|<span data-ttu-id="ca345-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ca345-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ca345-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca345-112">Description</span></span>  
 <span data-ttu-id="ca345-113">Indica que una aplicación de flujo de trabajo ha finalizado en el estado Faulted con una excepción.</span><span class="sxs-lookup"><span data-stu-id="ca345-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ca345-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ca345-114">Message</span></span>  
 <span data-ttu-id="ca345-115">WorkflowApplication Id: '%1' se terminó.</span><span class="sxs-lookup"><span data-stu-id="ca345-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="ca345-116">Se ha completado con el estado Faulted y con una excepción.</span><span class="sxs-lookup"><span data-stu-id="ca345-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ca345-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="ca345-117">Details</span></span>  
  
|<span data-ttu-id="ca345-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ca345-118">Data Item Name</span></span>|<span data-ttu-id="ca345-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ca345-119">Data Item Type</span></span>|<span data-ttu-id="ca345-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca345-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ca345-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="ca345-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="ca345-122">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ca345-122">The workflow application id</span></span>|  
|<span data-ttu-id="ca345-123">Excepción</span><span class="sxs-lookup"><span data-stu-id="ca345-123">Exception</span></span>|`xs:string`|<span data-ttu-id="ca345-124">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="ca345-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="ca345-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ca345-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="ca345-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ca345-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
