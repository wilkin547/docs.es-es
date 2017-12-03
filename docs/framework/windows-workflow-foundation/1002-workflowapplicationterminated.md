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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93a6a400576df84faae3cd58940462255b0073c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="df411-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="df411-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="df411-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="df411-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="df411-104">Id.</span><span class="sxs-lookup"><span data-stu-id="df411-104">ID</span></span>|<span data-ttu-id="df411-105">1002</span><span class="sxs-lookup"><span data-stu-id="df411-105">1002</span></span>|  
|<span data-ttu-id="df411-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="df411-106">Keywords</span></span>|<span data-ttu-id="df411-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="df411-107">WFRuntime</span></span>|  
|<span data-ttu-id="df411-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="df411-108">Level</span></span>|<span data-ttu-id="df411-109">Información</span><span class="sxs-lookup"><span data-stu-id="df411-109">Information</span></span>|  
|<span data-ttu-id="df411-110">Canal</span><span class="sxs-lookup"><span data-stu-id="df411-110">Channel</span></span>|<span data-ttu-id="df411-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="df411-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="df411-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="df411-112">Description</span></span>  
 <span data-ttu-id="df411-113">Indica que una aplicación de flujo de trabajo ha finalizado en el estado Faulted con una excepción.</span><span class="sxs-lookup"><span data-stu-id="df411-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="df411-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="df411-114">Message</span></span>  
 <span data-ttu-id="df411-115">WorkflowApplication Id: '%1' se terminó.</span><span class="sxs-lookup"><span data-stu-id="df411-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="df411-116">Se ha completado con el estado Faulted y con una excepción.</span><span class="sxs-lookup"><span data-stu-id="df411-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="df411-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="df411-117">Details</span></span>  
  
|<span data-ttu-id="df411-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="df411-118">Data Item Name</span></span>|<span data-ttu-id="df411-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="df411-119">Data Item Type</span></span>|<span data-ttu-id="df411-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="df411-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="df411-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="df411-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="df411-122">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="df411-122">The workflow application id</span></span>|  
|<span data-ttu-id="df411-123">Excepción</span><span class="sxs-lookup"><span data-stu-id="df411-123">Exception</span></span>|`xs:string`|<span data-ttu-id="df411-124">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="df411-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="df411-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="df411-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="df411-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="df411-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
