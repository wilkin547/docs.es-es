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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5debccf664768b84a7b213cd012b484df8fe3ef8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1150---compensationstate"></a><span data-ttu-id="8a598-102">1150 - CompensationState</span><span class="sxs-lookup"><span data-stu-id="8a598-102">1150 - CompensationState</span></span>
## <a name="properties"></a><span data-ttu-id="8a598-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8a598-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a598-104">Id.</span><span class="sxs-lookup"><span data-stu-id="8a598-104">ID</span></span>|<span data-ttu-id="8a598-105">1150</span><span class="sxs-lookup"><span data-stu-id="8a598-105">1150</span></span>|  
|<span data-ttu-id="8a598-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8a598-106">Keywords</span></span>|<span data-ttu-id="8a598-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="8a598-107">WFActivities</span></span>|  
|<span data-ttu-id="8a598-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="8a598-108">Level</span></span>|<span data-ttu-id="8a598-109">Información</span><span class="sxs-lookup"><span data-stu-id="8a598-109">Information</span></span>|  
|<span data-ttu-id="8a598-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8a598-110">Channel</span></span>|<span data-ttu-id="8a598-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8a598-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8a598-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a598-112">Description</span></span>  
 <span data-ttu-id="8a598-113">Indica un cambio de estado en un CompensableActivity.</span><span class="sxs-lookup"><span data-stu-id="8a598-113">Indicates a change of state in a CompensableActivity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8a598-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="8a598-114">Message</span></span>  
 <span data-ttu-id="8a598-115">CompensableActivity '%1' no tiene el estado '%2'.</span><span class="sxs-lookup"><span data-stu-id="8a598-115">CompensableActivity '%1' is in the '%2' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8a598-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="8a598-116">Details</span></span>  
  
|<span data-ttu-id="8a598-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8a598-117">Data Item Name</span></span>|<span data-ttu-id="8a598-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8a598-118">Data Item Type</span></span>|<span data-ttu-id="8a598-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a598-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8a598-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8a598-120">DisplayName</span></span>|<span data-ttu-id="8a598-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a598-121">xs:string</span></span>|<span data-ttu-id="8a598-122">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8a598-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="8a598-123">Estado</span><span class="sxs-lookup"><span data-stu-id="8a598-123">State</span></span>|<span data-ttu-id="8a598-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a598-124">xs:string</span></span>|<span data-ttu-id="8a598-125">Estado de compensación.</span><span class="sxs-lookup"><span data-stu-id="8a598-125">The compensation state.</span></span>|  
|<span data-ttu-id="8a598-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8a598-126">AppDomain</span></span>|<span data-ttu-id="8a598-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a598-127">xs:string</span></span>|<span data-ttu-id="8a598-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8a598-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
