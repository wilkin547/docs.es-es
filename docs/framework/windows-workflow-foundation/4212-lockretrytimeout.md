---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 43ec434064f768fc976232c6d3013f17c80fe053
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267174"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="f72ac-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="f72ac-102">4212 - LockRetryTimeout</span></span>

## <a name="properties"></a><span data-ttu-id="f72ac-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f72ac-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f72ac-104">ID</span><span class="sxs-lookup"><span data-stu-id="f72ac-104">ID</span></span>|<span data-ttu-id="f72ac-105">4212</span><span class="sxs-lookup"><span data-stu-id="f72ac-105">4212</span></span>|  
|<span data-ttu-id="f72ac-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f72ac-106">Keywords</span></span>|<span data-ttu-id="f72ac-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="f72ac-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="f72ac-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f72ac-108">Level</span></span>|<span data-ttu-id="f72ac-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="f72ac-109">Warning</span></span>|  
|<span data-ttu-id="f72ac-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f72ac-110">Channel</span></span>|<span data-ttu-id="f72ac-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f72ac-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f72ac-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f72ac-112">Description</span></span>  

 <span data-ttu-id="f72ac-113">El proveedor de SQL detectó que se agotó el tiempo de espera al intentar adquirir el bloqueo de instancia.</span><span class="sxs-lookup"><span data-stu-id="f72ac-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f72ac-114">Message</span><span class="sxs-lookup"><span data-stu-id="f72ac-114">Message</span></span>  

 <span data-ttu-id="f72ac-115">Tiempo de espera al intentar adquirir el bloqueo de la instancia.</span><span class="sxs-lookup"><span data-stu-id="f72ac-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="f72ac-116">La operación no se completó dentro del tiempo de espera asignado de %1.</span><span class="sxs-lookup"><span data-stu-id="f72ac-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="f72ac-117">El tiempo asignado a esta operación puede ser una porción de un tiempo de espera mayor.</span><span class="sxs-lookup"><span data-stu-id="f72ac-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f72ac-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="f72ac-118">Details</span></span>  
  
|<span data-ttu-id="f72ac-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f72ac-119">Data Item Name</span></span>|<span data-ttu-id="f72ac-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f72ac-120">Data Item Type</span></span>|<span data-ttu-id="f72ac-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="f72ac-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f72ac-122">Delay</span><span class="sxs-lookup"><span data-stu-id="f72ac-122">Delay</span></span>|<span data-ttu-id="f72ac-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f72ac-123">xs:string</span></span>|<span data-ttu-id="f72ac-124">El retraso entre los reintentos.</span><span class="sxs-lookup"><span data-stu-id="f72ac-124">The delay between retries.</span></span>|  
|<span data-ttu-id="f72ac-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f72ac-125">AppDomain</span></span>|<span data-ttu-id="f72ac-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f72ac-126">xs:string</span></span>|<span data-ttu-id="f72ac-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f72ac-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
