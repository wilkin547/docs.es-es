---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b321f8c20fbd79b5e748601ee06f975dc75a7d56
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="02519-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="02519-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="02519-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="02519-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02519-104">Id.</span><span class="sxs-lookup"><span data-stu-id="02519-104">ID</span></span>|<span data-ttu-id="02519-105">1041</span><span class="sxs-lookup"><span data-stu-id="02519-105">1041</span></span>|  
|<span data-ttu-id="02519-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="02519-106">Keywords</span></span>|<span data-ttu-id="02519-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="02519-107">WFRuntime</span></span>|  
|<span data-ttu-id="02519-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="02519-108">Level</span></span>|<span data-ttu-id="02519-109">Información</span><span class="sxs-lookup"><span data-stu-id="02519-109">Information</span></span>|  
|<span data-ttu-id="02519-110">Canal</span><span class="sxs-lookup"><span data-stu-id="02519-110">Channel</span></span>|<span data-ttu-id="02519-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="02519-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="02519-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="02519-112">Description</span></span>  
 <span data-ttu-id="02519-113">Indica que una aplicación de flujo de trabajo está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="02519-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="02519-114">La aplicación de flujo de trabajo estará inactiva o se conservará.</span><span class="sxs-lookup"><span data-stu-id="02519-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="02519-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="02519-115">Message</span></span>  
 <span data-ttu-id="02519-116">WorkflowApplication Id: '%1' está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="02519-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="02519-117">Se realizará la acción siguiente: %2.</span><span class="sxs-lookup"><span data-stu-id="02519-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="02519-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="02519-118">Details</span></span>  
  
|<span data-ttu-id="02519-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="02519-119">Data Item Name</span></span>|<span data-ttu-id="02519-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="02519-120">Data Item Type</span></span>|<span data-ttu-id="02519-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="02519-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="02519-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="02519-122">WorkflowApplicationId</span></span>|<span data-ttu-id="02519-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="02519-123">xs:string</span></span>|<span data-ttu-id="02519-124">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02519-124">The workflow application id</span></span>|  
|<span data-ttu-id="02519-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="02519-125">ActionTaken</span></span>|<span data-ttu-id="02519-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="02519-126">xs:string</span></span>|<span data-ttu-id="02519-127">La acción que se adoptará en la aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="02519-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="02519-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="02519-128">AppDomain</span></span>|<span data-ttu-id="02519-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="02519-129">xs:string</span></span>|<span data-ttu-id="02519-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="02519-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
