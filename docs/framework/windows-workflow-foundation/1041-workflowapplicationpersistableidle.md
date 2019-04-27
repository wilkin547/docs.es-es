---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924194"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="e1778-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="e1778-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="e1778-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e1778-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1778-104">ID</span><span class="sxs-lookup"><span data-stu-id="e1778-104">ID</span></span>|<span data-ttu-id="e1778-105">1041</span><span class="sxs-lookup"><span data-stu-id="e1778-105">1041</span></span>|  
|<span data-ttu-id="e1778-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e1778-106">Keywords</span></span>|<span data-ttu-id="e1778-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e1778-107">WFRuntime</span></span>|  
|<span data-ttu-id="e1778-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e1778-108">Level</span></span>|<span data-ttu-id="e1778-109">Información</span><span class="sxs-lookup"><span data-stu-id="e1778-109">Information</span></span>|  
|<span data-ttu-id="e1778-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e1778-110">Channel</span></span>|<span data-ttu-id="e1778-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e1778-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e1778-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1778-112">Description</span></span>  
 <span data-ttu-id="e1778-113">Indica que una aplicación de flujo de trabajo está inactiva y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="e1778-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="e1778-114">La aplicación de flujo de trabajo estará inactiva o se conservará.</span><span class="sxs-lookup"><span data-stu-id="e1778-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e1778-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="e1778-115">Message</span></span>  
 <span data-ttu-id="e1778-116">WorkflowApplication Id: '%1' está inactivo y con persistencia.</span><span class="sxs-lookup"><span data-stu-id="e1778-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="e1778-117">Se realizará la acción siguiente: %2.</span><span class="sxs-lookup"><span data-stu-id="e1778-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e1778-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="e1778-118">Details</span></span>  
  
|<span data-ttu-id="e1778-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e1778-119">Data Item Name</span></span>|<span data-ttu-id="e1778-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e1778-120">Data Item Type</span></span>|<span data-ttu-id="e1778-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1778-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e1778-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="e1778-122">WorkflowApplicationId</span></span>|<span data-ttu-id="e1778-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1778-123">xs:string</span></span>|<span data-ttu-id="e1778-124">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1778-124">The workflow application id</span></span>|  
|<span data-ttu-id="e1778-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="e1778-125">ActionTaken</span></span>|<span data-ttu-id="e1778-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1778-126">xs:string</span></span>|<span data-ttu-id="e1778-127">La acción que se adoptará en la aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1778-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="e1778-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e1778-128">AppDomain</span></span>|<span data-ttu-id="e1778-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="e1778-129">xs:string</span></span>|<span data-ttu-id="e1778-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e1778-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
