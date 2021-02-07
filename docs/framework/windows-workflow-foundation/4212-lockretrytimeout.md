---
description: 'Más información acerca de: 4212-LockRetryTimeout'
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: a2299d0d9643fb60ff420519fb43199e3f747c69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667088"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="67e0c-103">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="67e0c-103">4212 - LockRetryTimeout</span></span>

## <a name="properties"></a><span data-ttu-id="67e0c-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="67e0c-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67e0c-105">Id.</span><span class="sxs-lookup"><span data-stu-id="67e0c-105">ID</span></span>|<span data-ttu-id="67e0c-106">4212</span><span class="sxs-lookup"><span data-stu-id="67e0c-106">4212</span></span>|  
|<span data-ttu-id="67e0c-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="67e0c-107">Keywords</span></span>|<span data-ttu-id="67e0c-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="67e0c-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="67e0c-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="67e0c-109">Level</span></span>|<span data-ttu-id="67e0c-110">Advertencia</span><span class="sxs-lookup"><span data-stu-id="67e0c-110">Warning</span></span>|  
|<span data-ttu-id="67e0c-111">Canal</span><span class="sxs-lookup"><span data-stu-id="67e0c-111">Channel</span></span>|<span data-ttu-id="67e0c-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="67e0c-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="67e0c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="67e0c-113">Description</span></span>  

 <span data-ttu-id="67e0c-114">El proveedor de SQL detectó que se agotó el tiempo de espera al intentar adquirir el bloqueo de instancia.</span><span class="sxs-lookup"><span data-stu-id="67e0c-114">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="67e0c-115">Message</span><span class="sxs-lookup"><span data-stu-id="67e0c-115">Message</span></span>  

 <span data-ttu-id="67e0c-116">Tiempo de espera al intentar adquirir el bloqueo de la instancia.</span><span class="sxs-lookup"><span data-stu-id="67e0c-116">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="67e0c-117">La operación no se completó dentro del tiempo de espera asignado de %1.</span><span class="sxs-lookup"><span data-stu-id="67e0c-117">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="67e0c-118">El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.</span><span class="sxs-lookup"><span data-stu-id="67e0c-118">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="67e0c-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="67e0c-119">Details</span></span>  
  
|<span data-ttu-id="67e0c-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="67e0c-120">Data Item Name</span></span>|<span data-ttu-id="67e0c-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="67e0c-121">Data Item Type</span></span>|<span data-ttu-id="67e0c-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="67e0c-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="67e0c-123">Delay</span><span class="sxs-lookup"><span data-stu-id="67e0c-123">Delay</span></span>|<span data-ttu-id="67e0c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="67e0c-124">xs:string</span></span>|<span data-ttu-id="67e0c-125">El retraso entre los reintentos.</span><span class="sxs-lookup"><span data-stu-id="67e0c-125">The delay between retries.</span></span>|  
|<span data-ttu-id="67e0c-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="67e0c-126">AppDomain</span></span>|<span data-ttu-id="67e0c-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="67e0c-127">xs:string</span></span>|<span data-ttu-id="67e0c-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="67e0c-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
