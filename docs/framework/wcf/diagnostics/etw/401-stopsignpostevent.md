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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 058cae31c70e2c415e27870af1a0064b84a70b12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="b0121-102">401- StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="b0121-102">401- StopSignPostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="b0121-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b0121-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b0121-104">Id.</span><span class="sxs-lookup"><span data-stu-id="b0121-104">ID</span></span>|<span data-ttu-id="b0121-105">401</span><span class="sxs-lookup"><span data-stu-id="b0121-105">401</span></span>|  
|<span data-ttu-id="b0121-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b0121-106">Keywords</span></span>|<span data-ttu-id="b0121-107">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b0121-107">Troubleshooting</span></span>|  
|<span data-ttu-id="b0121-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b0121-108">Level</span></span>|<span data-ttu-id="b0121-109">Información</span><span class="sxs-lookup"><span data-stu-id="b0121-109">Information</span></span>|  
|<span data-ttu-id="b0121-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b0121-110">Channel</span></span>|<span data-ttu-id="b0121-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b0121-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b0121-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0121-112">Description</span></span>  
 <span data-ttu-id="b0121-113">Este evento marca el final de una actividad de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="b0121-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="b0121-114">Contiene el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b0121-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b0121-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b0121-115">Message</span></span>  
 <span data-ttu-id="b0121-116">Límite de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b0121-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b0121-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="b0121-117">Details</span></span>  
  
|<span data-ttu-id="b0121-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b0121-118">Data Item Name</span></span>|<span data-ttu-id="b0121-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b0121-119">Data Item Type</span></span>|<span data-ttu-id="b0121-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0121-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b0121-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="b0121-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="b0121-122">El nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b0121-122">The name of the activity.</span></span>|  
|<span data-ttu-id="b0121-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b0121-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b0121-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b0121-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
