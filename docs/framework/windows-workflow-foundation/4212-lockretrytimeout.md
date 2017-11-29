---
title: 4212 - LockRetryTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 897e6ef8b739654a61058106966c870c47f8129a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="3c586-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="3c586-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="3c586-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3c586-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3c586-104">Id.</span><span class="sxs-lookup"><span data-stu-id="3c586-104">ID</span></span>|<span data-ttu-id="3c586-105">4212</span><span class="sxs-lookup"><span data-stu-id="3c586-105">4212</span></span>|  
|<span data-ttu-id="3c586-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3c586-106">Keywords</span></span>|<span data-ttu-id="3c586-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="3c586-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="3c586-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3c586-108">Level</span></span>|<span data-ttu-id="3c586-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="3c586-109">Warning</span></span>|  
|<span data-ttu-id="3c586-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3c586-110">Channel</span></span>|<span data-ttu-id="3c586-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3c586-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3c586-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c586-112">Description</span></span>  
 <span data-ttu-id="3c586-113">El proveedor de SQL detectó que se agotó el tiempo de espera al intentar adquirir el bloqueo de instancia.</span><span class="sxs-lookup"><span data-stu-id="3c586-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3c586-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="3c586-114">Message</span></span>  
 <span data-ttu-id="3c586-115">Intenta adquirir el bloqueo de la instancia de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3c586-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="3c586-116">La operación no se completó dentro del tiempo de espera asignado de %1.</span><span class="sxs-lookup"><span data-stu-id="3c586-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="3c586-117">El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.</span><span class="sxs-lookup"><span data-stu-id="3c586-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3c586-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="3c586-118">Details</span></span>  
  
|<span data-ttu-id="3c586-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3c586-119">Data Item Name</span></span>|<span data-ttu-id="3c586-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3c586-120">Data Item Type</span></span>|<span data-ttu-id="3c586-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c586-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3c586-122">Delay</span><span class="sxs-lookup"><span data-stu-id="3c586-122">Delay</span></span>|<span data-ttu-id="3c586-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c586-123">xs:string</span></span>|<span data-ttu-id="3c586-124">Retraso entre los intentos.</span><span class="sxs-lookup"><span data-stu-id="3c586-124">The delay between retries.</span></span>|  
|<span data-ttu-id="3c586-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3c586-125">AppDomain</span></span>|<span data-ttu-id="3c586-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="3c586-126">xs:string</span></span>|<span data-ttu-id="3c586-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3c586-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
