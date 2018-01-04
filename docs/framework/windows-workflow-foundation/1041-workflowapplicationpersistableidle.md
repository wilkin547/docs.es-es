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
ms.workload: dotnet
ms.openlocfilehash: 1efc32ed0304d5b0d222054e5c65abe279ef93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="15a25-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="15a25-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="15a25-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="15a25-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15a25-104">Id.</span><span class="sxs-lookup"><span data-stu-id="15a25-104">ID</span></span>|<span data-ttu-id="15a25-105">1041</span><span class="sxs-lookup"><span data-stu-id="15a25-105">1041</span></span>|  
|<span data-ttu-id="15a25-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="15a25-106">Keywords</span></span>|<span data-ttu-id="15a25-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="15a25-107">WFRuntime</span></span>|  
|<span data-ttu-id="15a25-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="15a25-108">Level</span></span>|<span data-ttu-id="15a25-109">Información</span><span class="sxs-lookup"><span data-stu-id="15a25-109">Information</span></span>|  
|<span data-ttu-id="15a25-110">Canal</span><span class="sxs-lookup"><span data-stu-id="15a25-110">Channel</span></span>|<span data-ttu-id="15a25-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="15a25-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="15a25-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="15a25-112">Description</span></span>  
 <span data-ttu-id="15a25-113">Indica que una aplicación de flujo de trabajo está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="15a25-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="15a25-114">La aplicación de flujo de trabajo estará inactiva o se conservará.</span><span class="sxs-lookup"><span data-stu-id="15a25-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="15a25-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="15a25-115">Message</span></span>  
 <span data-ttu-id="15a25-116">WorkflowApplication Id: '%1' está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="15a25-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="15a25-117">Se realizará la acción siguiente: %2.</span><span class="sxs-lookup"><span data-stu-id="15a25-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="15a25-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="15a25-118">Details</span></span>  
  
|<span data-ttu-id="15a25-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="15a25-119">Data Item Name</span></span>|<span data-ttu-id="15a25-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="15a25-120">Data Item Type</span></span>|<span data-ttu-id="15a25-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="15a25-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="15a25-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="15a25-122">WorkflowApplicationId</span></span>|<span data-ttu-id="15a25-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="15a25-123">xs:string</span></span>|<span data-ttu-id="15a25-124">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="15a25-124">The workflow application id</span></span>|  
|<span data-ttu-id="15a25-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="15a25-125">ActionTaken</span></span>|<span data-ttu-id="15a25-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="15a25-126">xs:string</span></span>|<span data-ttu-id="15a25-127">La acción que se adoptará en la aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="15a25-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="15a25-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="15a25-128">AppDomain</span></span>|<span data-ttu-id="15a25-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="15a25-129">xs:string</span></span>|<span data-ttu-id="15a25-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="15a25-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
