---
title: 39458 - TrackingRecordTruncated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d12549d201ac621361bd6a517df6c6b53ab7aec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="b406f-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="b406f-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="b406f-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b406f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b406f-104">Id.</span><span class="sxs-lookup"><span data-stu-id="b406f-104">ID</span></span>|<span data-ttu-id="b406f-105">39458</span><span class="sxs-lookup"><span data-stu-id="b406f-105">39458</span></span>|  
|<span data-ttu-id="b406f-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b406f-106">Keywords</span></span>|<span data-ttu-id="b406f-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="b406f-107">WFTracking</span></span>|  
|<span data-ttu-id="b406f-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b406f-108">Level</span></span>|<span data-ttu-id="b406f-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="b406f-109">Warning</span></span>|  
|<span data-ttu-id="b406f-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b406f-110">Channel</span></span>|<span data-ttu-id="b406f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b406f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b406f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b406f-112">Description</span></span>  
 <span data-ttu-id="b406f-113">Indica que se ha truncado un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b406f-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="b406f-114">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="b406f-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b406f-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b406f-115">Message</span></span>  
 <span data-ttu-id="b406f-116">Se ha escrito un registro de seguimiento %1 truncado en la sesión de ETW con el proveedor %2.</span><span class="sxs-lookup"><span data-stu-id="b406f-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="b406f-117">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="b406f-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="b406f-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="b406f-118">Details</span></span>  
  
|<span data-ttu-id="b406f-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b406f-119">Data Item Name</span></span>|<span data-ttu-id="b406f-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b406f-120">Data Item Type</span></span>|<span data-ttu-id="b406f-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="b406f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b406f-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="b406f-122">RecordNumber</span></span>|<span data-ttu-id="b406f-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="b406f-123">xs:string</span></span>|<span data-ttu-id="b406f-124">Número del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b406f-124">The tracking record number.</span></span>|  
|<span data-ttu-id="b406f-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="b406f-125">ProviderId</span></span>|<span data-ttu-id="b406f-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="b406f-126">xs:string</span></span>|<span data-ttu-id="b406f-127">Identificador del proveedor ETW.</span><span class="sxs-lookup"><span data-stu-id="b406f-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="b406f-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b406f-128">AppDomain</span></span>|<span data-ttu-id="b406f-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="b406f-129">xs:string</span></span>|<span data-ttu-id="b406f-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b406f-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
