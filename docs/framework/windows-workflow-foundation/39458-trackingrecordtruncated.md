---
description: 'Más información acerca de: 39458-TrackingRecordTruncated'
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: bb9a46dc5bd9bc4f4709a740dd0e7ec47ca826e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631286"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="a9542-103">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="a9542-103">39458 - TrackingRecordTruncated</span></span>

## <a name="properties"></a><span data-ttu-id="a9542-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a9542-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9542-105">Id.</span><span class="sxs-lookup"><span data-stu-id="a9542-105">ID</span></span>|<span data-ttu-id="a9542-106">39458</span><span class="sxs-lookup"><span data-stu-id="a9542-106">39458</span></span>|  
|<span data-ttu-id="a9542-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a9542-107">Keywords</span></span>|<span data-ttu-id="a9542-108">WFTracking</span><span class="sxs-lookup"><span data-stu-id="a9542-108">WFTracking</span></span>|  
|<span data-ttu-id="a9542-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="a9542-109">Level</span></span>|<span data-ttu-id="a9542-110">Advertencia</span><span class="sxs-lookup"><span data-stu-id="a9542-110">Warning</span></span>|  
|<span data-ttu-id="a9542-111">Canal</span><span class="sxs-lookup"><span data-stu-id="a9542-111">Channel</span></span>|<span data-ttu-id="a9542-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a9542-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a9542-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9542-113">Description</span></span>  

 <span data-ttu-id="a9542-114">Indica que se ha truncado un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a9542-114">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="a9542-115">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="a9542-115">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a9542-116">Message</span><span class="sxs-lookup"><span data-stu-id="a9542-116">Message</span></span>  

 <span data-ttu-id="a9542-117">Se ha escrito un registro de seguimiento %1 truncado en la sesión de ETW con el proveedor %2.</span><span class="sxs-lookup"><span data-stu-id="a9542-117">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="a9542-118">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="a9542-118">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="a9542-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="a9542-119">Details</span></span>  
  
|<span data-ttu-id="a9542-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a9542-120">Data Item Name</span></span>|<span data-ttu-id="a9542-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a9542-121">Data Item Type</span></span>|<span data-ttu-id="a9542-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9542-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a9542-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="a9542-123">RecordNumber</span></span>|<span data-ttu-id="a9542-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a9542-124">xs:string</span></span>|<span data-ttu-id="a9542-125">Número del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a9542-125">The tracking record number.</span></span>|  
|<span data-ttu-id="a9542-126">ProviderId</span><span class="sxs-lookup"><span data-stu-id="a9542-126">ProviderId</span></span>|<span data-ttu-id="a9542-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="a9542-127">xs:string</span></span>|<span data-ttu-id="a9542-128">Identificador del proveedor ETW.</span><span class="sxs-lookup"><span data-stu-id="a9542-128">The ETW provider id.</span></span>|  
|<span data-ttu-id="a9542-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a9542-129">AppDomain</span></span>|<span data-ttu-id="a9542-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="a9542-130">xs:string</span></span>|<span data-ttu-id="a9542-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a9542-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
