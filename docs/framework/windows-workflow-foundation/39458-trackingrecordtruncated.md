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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ecf18d6d751edd47dbeca7d2e5f4491892e41e6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="6b27a-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="6b27a-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="6b27a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6b27a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6b27a-104">Id.</span><span class="sxs-lookup"><span data-stu-id="6b27a-104">ID</span></span>|<span data-ttu-id="6b27a-105">39458</span><span class="sxs-lookup"><span data-stu-id="6b27a-105">39458</span></span>|  
|<span data-ttu-id="6b27a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6b27a-106">Keywords</span></span>|<span data-ttu-id="6b27a-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="6b27a-107">WFTracking</span></span>|  
|<span data-ttu-id="6b27a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="6b27a-108">Level</span></span>|<span data-ttu-id="6b27a-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="6b27a-109">Warning</span></span>|  
|<span data-ttu-id="6b27a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6b27a-110">Channel</span></span>|<span data-ttu-id="6b27a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6b27a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6b27a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b27a-112">Description</span></span>  
 <span data-ttu-id="6b27a-113">Indica que se ha truncado un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6b27a-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="6b27a-114">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="6b27a-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6b27a-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="6b27a-115">Message</span></span>  
 <span data-ttu-id="6b27a-116">Se ha escrito un registro de seguimiento %1 truncado en la sesión de ETW con el proveedor %2.</span><span class="sxs-lookup"><span data-stu-id="6b27a-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="6b27a-117">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="6b27a-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="6b27a-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="6b27a-118">Details</span></span>  
  
|<span data-ttu-id="6b27a-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6b27a-119">Data Item Name</span></span>|<span data-ttu-id="6b27a-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6b27a-120">Data Item Type</span></span>|<span data-ttu-id="6b27a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b27a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6b27a-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="6b27a-122">RecordNumber</span></span>|<span data-ttu-id="6b27a-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="6b27a-123">xs:string</span></span>|<span data-ttu-id="6b27a-124">Número del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6b27a-124">The tracking record number.</span></span>|  
|<span data-ttu-id="6b27a-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="6b27a-125">ProviderId</span></span>|<span data-ttu-id="6b27a-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="6b27a-126">xs:string</span></span>|<span data-ttu-id="6b27a-127">Identificador del proveedor ETW.</span><span class="sxs-lookup"><span data-stu-id="6b27a-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="6b27a-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6b27a-128">AppDomain</span></span>|<span data-ttu-id="6b27a-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="6b27a-129">xs:string</span></span>|<span data-ttu-id="6b27a-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6b27a-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
