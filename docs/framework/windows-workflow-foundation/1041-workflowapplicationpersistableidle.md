---
description: 'Más información acerca de: 1041-WorkflowApplicationPersistableIdle'
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: eb004077a36ed3e78229df92a73972ed5feda665
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667764"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="3cfcb-103">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="3cfcb-103">1041 - WorkflowApplicationPersistableIdle</span></span>

## <a name="properties"></a><span data-ttu-id="3cfcb-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3cfcb-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3cfcb-105">Id.</span><span class="sxs-lookup"><span data-stu-id="3cfcb-105">ID</span></span>|<span data-ttu-id="3cfcb-106">1041</span><span class="sxs-lookup"><span data-stu-id="3cfcb-106">1041</span></span>|  
|<span data-ttu-id="3cfcb-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3cfcb-107">Keywords</span></span>|<span data-ttu-id="3cfcb-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3cfcb-108">WFRuntime</span></span>|  
|<span data-ttu-id="3cfcb-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="3cfcb-109">Level</span></span>|<span data-ttu-id="3cfcb-110">Información</span><span class="sxs-lookup"><span data-stu-id="3cfcb-110">Information</span></span>|  
|<span data-ttu-id="3cfcb-111">Canal</span><span class="sxs-lookup"><span data-stu-id="3cfcb-111">Channel</span></span>|<span data-ttu-id="3cfcb-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3cfcb-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3cfcb-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cfcb-113">Description</span></span>  

 <span data-ttu-id="3cfcb-114">Indica que una aplicación de flujo de trabajo está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="3cfcb-114">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="3cfcb-115">La aplicación de flujo de trabajo estará inactiva o se conservará.</span><span class="sxs-lookup"><span data-stu-id="3cfcb-115">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3cfcb-116">Message</span><span class="sxs-lookup"><span data-stu-id="3cfcb-116">Message</span></span>  

 <span data-ttu-id="3cfcb-117">WorkflowApplication ID: ' %1 ' está inactivo y es persistente.</span><span class="sxs-lookup"><span data-stu-id="3cfcb-117">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="3cfcb-118">Se realizará la siguiente acción: %2.</span><span class="sxs-lookup"><span data-stu-id="3cfcb-118">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3cfcb-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="3cfcb-119">Details</span></span>  
  
|<span data-ttu-id="3cfcb-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3cfcb-120">Data Item Name</span></span>|<span data-ttu-id="3cfcb-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3cfcb-121">Data Item Type</span></span>|<span data-ttu-id="3cfcb-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cfcb-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3cfcb-123">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="3cfcb-123">WorkflowApplicationId</span></span>|<span data-ttu-id="3cfcb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cfcb-124">xs:string</span></span>|<span data-ttu-id="3cfcb-125">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3cfcb-125">The workflow application id</span></span>|  
|<span data-ttu-id="3cfcb-126">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="3cfcb-126">ActionTaken</span></span>|<span data-ttu-id="3cfcb-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cfcb-127">xs:string</span></span>|<span data-ttu-id="3cfcb-128">La acción que se adoptará en la aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3cfcb-128">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="3cfcb-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3cfcb-129">AppDomain</span></span>|<span data-ttu-id="3cfcb-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cfcb-130">xs:string</span></span>|<span data-ttu-id="3cfcb-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3cfcb-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
