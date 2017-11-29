---
title: 403 - SuspendSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 10e745ded72caa493119d7e27a5c777b2185b96e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="b7616-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="b7616-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="b7616-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b7616-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7616-104">Id.</span><span class="sxs-lookup"><span data-stu-id="b7616-104">ID</span></span>|<span data-ttu-id="b7616-105">403</span><span class="sxs-lookup"><span data-stu-id="b7616-105">403</span></span>|  
|<span data-ttu-id="b7616-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b7616-106">Keywords</span></span>|<span data-ttu-id="b7616-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b7616-107">Troubleshooting</span></span>|  
|<span data-ttu-id="b7616-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b7616-108">Level</span></span>|<span data-ttu-id="b7616-109">Información</span><span class="sxs-lookup"><span data-stu-id="b7616-109">Information</span></span>|  
|<span data-ttu-id="b7616-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b7616-110">Channel</span></span>|<span data-ttu-id="b7616-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b7616-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b7616-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7616-112">Description</span></span>  
 <span data-ttu-id="b7616-113">Este evento marca la suspensión de una actividad de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="b7616-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="b7616-114">Contiene el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b7616-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b7616-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b7616-115">Message</span></span>  
 <span data-ttu-id="b7616-116">Límite de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b7616-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b7616-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="b7616-117">Details</span></span>  
  
|<span data-ttu-id="b7616-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b7616-118">Data Item Name</span></span>|<span data-ttu-id="b7616-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b7616-119">Data Item Type</span></span>|<span data-ttu-id="b7616-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7616-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b7616-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="b7616-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="b7616-122">El nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b7616-122">The name of the activity.</span></span>|  
|<span data-ttu-id="b7616-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b7616-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b7616-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b7616-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
