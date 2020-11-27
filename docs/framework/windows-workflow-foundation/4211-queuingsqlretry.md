---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ff8a1e099934f5bf71fef0afbb7e54c0d1851fae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267187"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="5ec66-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="5ec66-102">4211 - QueuingSqlRetry</span></span>

## <a name="properties"></a><span data-ttu-id="5ec66-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5ec66-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ec66-104">ID</span><span class="sxs-lookup"><span data-stu-id="5ec66-104">ID</span></span>|<span data-ttu-id="5ec66-105">4211</span><span class="sxs-lookup"><span data-stu-id="5ec66-105">4211</span></span>|  
|<span data-ttu-id="5ec66-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5ec66-106">Keywords</span></span>|<span data-ttu-id="5ec66-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="5ec66-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="5ec66-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="5ec66-108">Level</span></span>|<span data-ttu-id="5ec66-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="5ec66-109">Warning</span></span>|  
|<span data-ttu-id="5ec66-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5ec66-110">Channel</span></span>|<span data-ttu-id="5ec66-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5ec66-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5ec66-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ec66-112">Description</span></span>  

 <span data-ttu-id="5ec66-113">Indica poner en cola el intento de SQL.</span><span class="sxs-lookup"><span data-stu-id="5ec66-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5ec66-114">Message</span><span class="sxs-lookup"><span data-stu-id="5ec66-114">Message</span></span>  

 <span data-ttu-id="5ec66-115">Poniendo en cola el reintento SQL con %1 milisegundos de retraso.</span><span class="sxs-lookup"><span data-stu-id="5ec66-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5ec66-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="5ec66-116">Details</span></span>  
  
|<span data-ttu-id="5ec66-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5ec66-117">Data Item Name</span></span>|<span data-ttu-id="5ec66-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5ec66-118">Data Item Type</span></span>|<span data-ttu-id="5ec66-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ec66-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5ec66-120">Delay</span><span class="sxs-lookup"><span data-stu-id="5ec66-120">Delay</span></span>|<span data-ttu-id="5ec66-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5ec66-121">xs:string</span></span>|<span data-ttu-id="5ec66-122">El retraso entre los reintentos.</span><span class="sxs-lookup"><span data-stu-id="5ec66-122">The delay between retries.</span></span>|  
|<span data-ttu-id="5ec66-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5ec66-123">AppDomain</span></span>|<span data-ttu-id="5ec66-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5ec66-124">xs:string</span></span>|<span data-ttu-id="5ec66-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5ec66-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
