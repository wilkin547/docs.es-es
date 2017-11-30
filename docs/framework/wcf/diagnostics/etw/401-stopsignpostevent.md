---
title: 401- StopSignPostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 31cd94e2c988d614babc1e0c203316b41e01f5bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="094b4-102">401- StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="094b4-102">401- StopSignPostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="094b4-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="094b4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="094b4-104">Id.</span><span class="sxs-lookup"><span data-stu-id="094b4-104">ID</span></span>|<span data-ttu-id="094b4-105">401</span><span class="sxs-lookup"><span data-stu-id="094b4-105">401</span></span>|  
|<span data-ttu-id="094b4-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="094b4-106">Keywords</span></span>|<span data-ttu-id="094b4-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="094b4-107">Troubleshooting</span></span>|  
|<span data-ttu-id="094b4-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="094b4-108">Level</span></span>|<span data-ttu-id="094b4-109">Información</span><span class="sxs-lookup"><span data-stu-id="094b4-109">Information</span></span>|  
|<span data-ttu-id="094b4-110">Canal</span><span class="sxs-lookup"><span data-stu-id="094b4-110">Channel</span></span>|<span data-ttu-id="094b4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="094b4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="094b4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="094b4-112">Description</span></span>  
 <span data-ttu-id="094b4-113">Este evento marca el final de una actividad de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="094b4-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="094b4-114">Contiene el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="094b4-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="094b4-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="094b4-115">Message</span></span>  
 <span data-ttu-id="094b4-116">Límite de la actividad.</span><span class="sxs-lookup"><span data-stu-id="094b4-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="094b4-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="094b4-117">Details</span></span>  
  
|<span data-ttu-id="094b4-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="094b4-118">Data Item Name</span></span>|<span data-ttu-id="094b4-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="094b4-119">Data Item Type</span></span>|<span data-ttu-id="094b4-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="094b4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="094b4-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="094b4-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="094b4-122">El nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="094b4-122">The name of the activity.</span></span>|  
|<span data-ttu-id="094b4-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="094b4-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="094b4-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="094b4-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
