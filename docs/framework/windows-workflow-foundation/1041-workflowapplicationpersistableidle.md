---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 9995823753fc78ca3f278cd635fcf6c7d2b84325
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238943"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="73269-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="73269-102">1041 - WorkflowApplicationPersistableIdle</span></span>

## <a name="properties"></a><span data-ttu-id="73269-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="73269-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73269-104">ID</span><span class="sxs-lookup"><span data-stu-id="73269-104">ID</span></span>|<span data-ttu-id="73269-105">1041</span><span class="sxs-lookup"><span data-stu-id="73269-105">1041</span></span>|  
|<span data-ttu-id="73269-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="73269-106">Keywords</span></span>|<span data-ttu-id="73269-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="73269-107">WFRuntime</span></span>|  
|<span data-ttu-id="73269-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="73269-108">Level</span></span>|<span data-ttu-id="73269-109">Información</span><span class="sxs-lookup"><span data-stu-id="73269-109">Information</span></span>|  
|<span data-ttu-id="73269-110">Canal</span><span class="sxs-lookup"><span data-stu-id="73269-110">Channel</span></span>|<span data-ttu-id="73269-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="73269-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="73269-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="73269-112">Description</span></span>  

 <span data-ttu-id="73269-113">Indica que una aplicación de flujo de trabajo está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="73269-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="73269-114">La aplicación de flujo de trabajo estará inactiva o se conservará.</span><span class="sxs-lookup"><span data-stu-id="73269-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="73269-115">Message</span><span class="sxs-lookup"><span data-stu-id="73269-115">Message</span></span>  

 <span data-ttu-id="73269-116">WorkflowApplication ID: ' %1 ' está inactivo y es persistente.</span><span class="sxs-lookup"><span data-stu-id="73269-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="73269-117">Se realizará la siguiente acción: %2.</span><span class="sxs-lookup"><span data-stu-id="73269-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="73269-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="73269-118">Details</span></span>  
  
|<span data-ttu-id="73269-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="73269-119">Data Item Name</span></span>|<span data-ttu-id="73269-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="73269-120">Data Item Type</span></span>|<span data-ttu-id="73269-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="73269-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="73269-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="73269-122">WorkflowApplicationId</span></span>|<span data-ttu-id="73269-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="73269-123">xs:string</span></span>|<span data-ttu-id="73269-124">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73269-124">The workflow application id</span></span>|  
|<span data-ttu-id="73269-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="73269-125">ActionTaken</span></span>|<span data-ttu-id="73269-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="73269-126">xs:string</span></span>|<span data-ttu-id="73269-127">La acción que se adoptará en la aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="73269-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="73269-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="73269-128">AppDomain</span></span>|<span data-ttu-id="73269-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="73269-129">xs:string</span></span>|<span data-ttu-id="73269-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="73269-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
