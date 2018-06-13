---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509672"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="fa058-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="fa058-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="fa058-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fa058-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa058-104">Id.</span><span class="sxs-lookup"><span data-stu-id="fa058-104">ID</span></span>|<span data-ttu-id="fa058-105">1041</span><span class="sxs-lookup"><span data-stu-id="fa058-105">1041</span></span>|  
|<span data-ttu-id="fa058-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="fa058-106">Keywords</span></span>|<span data-ttu-id="fa058-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fa058-107">WFRuntime</span></span>|  
|<span data-ttu-id="fa058-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="fa058-108">Level</span></span>|<span data-ttu-id="fa058-109">Información</span><span class="sxs-lookup"><span data-stu-id="fa058-109">Information</span></span>|  
|<span data-ttu-id="fa058-110">Canal</span><span class="sxs-lookup"><span data-stu-id="fa058-110">Channel</span></span>|<span data-ttu-id="fa058-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fa058-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fa058-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa058-112">Description</span></span>  
 <span data-ttu-id="fa058-113">Indica que una aplicación de flujo de trabajo está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="fa058-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="fa058-114">La aplicación de flujo de trabajo estará inactiva o se conservará.</span><span class="sxs-lookup"><span data-stu-id="fa058-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fa058-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="fa058-115">Message</span></span>  
 <span data-ttu-id="fa058-116">WorkflowApplication Id: '%1' está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="fa058-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="fa058-117">Se realizará la acción siguiente: %2.</span><span class="sxs-lookup"><span data-stu-id="fa058-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fa058-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="fa058-118">Details</span></span>  
  
|<span data-ttu-id="fa058-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fa058-119">Data Item Name</span></span>|<span data-ttu-id="fa058-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fa058-120">Data Item Type</span></span>|<span data-ttu-id="fa058-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa058-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fa058-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="fa058-122">WorkflowApplicationId</span></span>|<span data-ttu-id="fa058-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa058-123">xs:string</span></span>|<span data-ttu-id="fa058-124">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fa058-124">The workflow application id</span></span>|  
|<span data-ttu-id="fa058-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="fa058-125">ActionTaken</span></span>|<span data-ttu-id="fa058-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa058-126">xs:string</span></span>|<span data-ttu-id="fa058-127">La acción que se adoptará en la aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fa058-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="fa058-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fa058-128">AppDomain</span></span>|<span data-ttu-id="fa058-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="fa058-129">xs:string</span></span>|<span data-ttu-id="fa058-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fa058-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
