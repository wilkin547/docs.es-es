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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea6b31a83df6e15fe34f9e4be31a4eb53bc5bb51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="aee44-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="aee44-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="aee44-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="aee44-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aee44-104">Id.</span><span class="sxs-lookup"><span data-stu-id="aee44-104">ID</span></span>|<span data-ttu-id="aee44-105">1041</span><span class="sxs-lookup"><span data-stu-id="aee44-105">1041</span></span>|  
|<span data-ttu-id="aee44-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="aee44-106">Keywords</span></span>|<span data-ttu-id="aee44-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="aee44-107">WFRuntime</span></span>|  
|<span data-ttu-id="aee44-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="aee44-108">Level</span></span>|<span data-ttu-id="aee44-109">Información</span><span class="sxs-lookup"><span data-stu-id="aee44-109">Information</span></span>|  
|<span data-ttu-id="aee44-110">Canal</span><span class="sxs-lookup"><span data-stu-id="aee44-110">Channel</span></span>|<span data-ttu-id="aee44-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="aee44-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aee44-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="aee44-112">Description</span></span>  
 <span data-ttu-id="aee44-113">Indica que una aplicación de flujo de trabajo está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="aee44-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="aee44-114">La aplicación de flujo de trabajo estará inactiva o se conservará.</span><span class="sxs-lookup"><span data-stu-id="aee44-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aee44-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="aee44-115">Message</span></span>  
 <span data-ttu-id="aee44-116">WorkflowApplication Id: '%1' está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="aee44-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="aee44-117">Se realizará la acción siguiente: %2.</span><span class="sxs-lookup"><span data-stu-id="aee44-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aee44-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="aee44-118">Details</span></span>  
  
|<span data-ttu-id="aee44-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="aee44-119">Data Item Name</span></span>|<span data-ttu-id="aee44-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="aee44-120">Data Item Type</span></span>|<span data-ttu-id="aee44-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="aee44-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aee44-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="aee44-122">WorkflowApplicationId</span></span>|<span data-ttu-id="aee44-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="aee44-123">xs:string</span></span>|<span data-ttu-id="aee44-124">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="aee44-124">The workflow application id</span></span>|  
|<span data-ttu-id="aee44-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="aee44-125">ActionTaken</span></span>|<span data-ttu-id="aee44-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="aee44-126">xs:string</span></span>|<span data-ttu-id="aee44-127">La acción que se adoptará en la aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="aee44-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="aee44-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aee44-128">AppDomain</span></span>|<span data-ttu-id="aee44-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="aee44-129">xs:string</span></span>|<span data-ttu-id="aee44-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="aee44-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
