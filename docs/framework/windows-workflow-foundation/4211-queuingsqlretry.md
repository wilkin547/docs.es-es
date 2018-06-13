---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514574"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="2114a-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="2114a-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="2114a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2114a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2114a-104">Id.</span><span class="sxs-lookup"><span data-stu-id="2114a-104">ID</span></span>|<span data-ttu-id="2114a-105">4211</span><span class="sxs-lookup"><span data-stu-id="2114a-105">4211</span></span>|  
|<span data-ttu-id="2114a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2114a-106">Keywords</span></span>|<span data-ttu-id="2114a-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="2114a-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="2114a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="2114a-108">Level</span></span>|<span data-ttu-id="2114a-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="2114a-109">Warning</span></span>|  
|<span data-ttu-id="2114a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="2114a-110">Channel</span></span>|<span data-ttu-id="2114a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2114a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2114a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2114a-112">Description</span></span>  
 <span data-ttu-id="2114a-113">Indica poner en cola el intento de SQL.</span><span class="sxs-lookup"><span data-stu-id="2114a-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2114a-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="2114a-114">Message</span></span>  
 <span data-ttu-id="2114a-115">Poniendo en cola el reintento SQL con %1 milisegundos de retraso.</span><span class="sxs-lookup"><span data-stu-id="2114a-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2114a-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="2114a-116">Details</span></span>  
  
|<span data-ttu-id="2114a-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2114a-117">Data Item Name</span></span>|<span data-ttu-id="2114a-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2114a-118">Data Item Type</span></span>|<span data-ttu-id="2114a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="2114a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2114a-120">Delay</span><span class="sxs-lookup"><span data-stu-id="2114a-120">Delay</span></span>|<span data-ttu-id="2114a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2114a-121">xs:string</span></span>|<span data-ttu-id="2114a-122">Retraso entre los intentos.</span><span class="sxs-lookup"><span data-stu-id="2114a-122">The delay between retries.</span></span>|  
|<span data-ttu-id="2114a-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2114a-123">AppDomain</span></span>|<span data-ttu-id="2114a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2114a-124">xs:string</span></span>|<span data-ttu-id="2114a-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2114a-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
