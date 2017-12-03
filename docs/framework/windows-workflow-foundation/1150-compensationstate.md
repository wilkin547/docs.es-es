---
title: 1150 - CompensationState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc5de180030b8c07cb5ade268205e94079e0fbb9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1150---compensationstate"></a><span data-ttu-id="93368-102">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="93368-102">1150 - CompensationState</span></span>
## <a name="properties"></a><span data-ttu-id="93368-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="93368-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93368-104">Id.</span><span class="sxs-lookup"><span data-stu-id="93368-104">ID</span></span>|<span data-ttu-id="93368-105">1150</span><span class="sxs-lookup"><span data-stu-id="93368-105">1150</span></span>|  
|<span data-ttu-id="93368-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="93368-106">Keywords</span></span>|<span data-ttu-id="93368-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="93368-107">WFActivities</span></span>|  
|<span data-ttu-id="93368-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="93368-108">Level</span></span>|<span data-ttu-id="93368-109">Información</span><span class="sxs-lookup"><span data-stu-id="93368-109">Information</span></span>|  
|<span data-ttu-id="93368-110">Canal</span><span class="sxs-lookup"><span data-stu-id="93368-110">Channel</span></span>|<span data-ttu-id="93368-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="93368-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="93368-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="93368-112">Description</span></span>  
 <span data-ttu-id="93368-113">Indica un cambio de estado en un CompensableActivity.</span><span class="sxs-lookup"><span data-stu-id="93368-113">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="93368-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="93368-114">Message</span></span>  
 <span data-ttu-id="93368-115">CompensableActivity '%1' no tiene el estado '%2'.</span><span class="sxs-lookup"><span data-stu-id="93368-115">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="93368-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="93368-116">Details</span></span>  
  
|<span data-ttu-id="93368-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="93368-117">Data Item Name</span></span>|<span data-ttu-id="93368-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="93368-118">Data Item Type</span></span>|<span data-ttu-id="93368-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="93368-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="93368-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="93368-120">DisplayName</span></span>|<span data-ttu-id="93368-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="93368-121">xs:string</span></span>|<span data-ttu-id="93368-122">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="93368-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="93368-123">Estado</span><span class="sxs-lookup"><span data-stu-id="93368-123">State</span></span>|<span data-ttu-id="93368-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="93368-124">xs:string</span></span>|<span data-ttu-id="93368-125">Estado de compensación.</span><span class="sxs-lookup"><span data-stu-id="93368-125">The compensation state.</span></span>|  
|<span data-ttu-id="93368-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="93368-126">AppDomain</span></span>|<span data-ttu-id="93368-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="93368-127">xs:string</span></span>|<span data-ttu-id="93368-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="93368-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
