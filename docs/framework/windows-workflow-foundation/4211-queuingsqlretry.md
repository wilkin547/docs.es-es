---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774249"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="48be4-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="48be4-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="48be4-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="48be4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="48be4-104">ID</span><span class="sxs-lookup"><span data-stu-id="48be4-104">ID</span></span>|<span data-ttu-id="48be4-105">4211</span><span class="sxs-lookup"><span data-stu-id="48be4-105">4211</span></span>|  
|<span data-ttu-id="48be4-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="48be4-106">Keywords</span></span>|<span data-ttu-id="48be4-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="48be4-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="48be4-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="48be4-108">Level</span></span>|<span data-ttu-id="48be4-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="48be4-109">Warning</span></span>|  
|<span data-ttu-id="48be4-110">Canal</span><span class="sxs-lookup"><span data-stu-id="48be4-110">Channel</span></span>|<span data-ttu-id="48be4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="48be4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="48be4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="48be4-112">Description</span></span>  
 <span data-ttu-id="48be4-113">Indica poner en cola el intento de SQL.</span><span class="sxs-lookup"><span data-stu-id="48be4-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="48be4-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="48be4-114">Message</span></span>  
 <span data-ttu-id="48be4-115">Poniendo en cola el reintento SQL con %1 milisegundos de retraso.</span><span class="sxs-lookup"><span data-stu-id="48be4-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="48be4-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="48be4-116">Details</span></span>  
  
|<span data-ttu-id="48be4-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="48be4-117">Data Item Name</span></span>|<span data-ttu-id="48be4-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="48be4-118">Data Item Type</span></span>|<span data-ttu-id="48be4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="48be4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="48be4-120">Delay</span><span class="sxs-lookup"><span data-stu-id="48be4-120">Delay</span></span>|<span data-ttu-id="48be4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="48be4-121">xs:string</span></span>|<span data-ttu-id="48be4-122">Retraso entre los intentos.</span><span class="sxs-lookup"><span data-stu-id="48be4-122">The delay between retries.</span></span>|  
|<span data-ttu-id="48be4-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="48be4-123">AppDomain</span></span>|<span data-ttu-id="48be4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="48be4-124">xs:string</span></span>|<span data-ttu-id="48be4-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="48be4-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
