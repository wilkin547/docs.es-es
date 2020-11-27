---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: f02a34673c51be6e0b127a64e4622131575d836f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275897"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="c7e04-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="c7e04-102">39458 - TrackingRecordTruncated</span></span>

## <a name="properties"></a><span data-ttu-id="c7e04-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c7e04-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7e04-104">ID</span><span class="sxs-lookup"><span data-stu-id="c7e04-104">ID</span></span>|<span data-ttu-id="c7e04-105">39458</span><span class="sxs-lookup"><span data-stu-id="c7e04-105">39458</span></span>|  
|<span data-ttu-id="c7e04-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c7e04-106">Keywords</span></span>|<span data-ttu-id="c7e04-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="c7e04-107">WFTracking</span></span>|  
|<span data-ttu-id="c7e04-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="c7e04-108">Level</span></span>|<span data-ttu-id="c7e04-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="c7e04-109">Warning</span></span>|  
|<span data-ttu-id="c7e04-110">Canal</span><span class="sxs-lookup"><span data-stu-id="c7e04-110">Channel</span></span>|<span data-ttu-id="c7e04-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="c7e04-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c7e04-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7e04-112">Description</span></span>  

 <span data-ttu-id="c7e04-113">Indica que se ha truncado un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c7e04-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="c7e04-114">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="c7e04-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c7e04-115">Message</span><span class="sxs-lookup"><span data-stu-id="c7e04-115">Message</span></span>  

 <span data-ttu-id="c7e04-116">Se ha escrito un registro de seguimiento %1 truncado en la sesión de ETW con el proveedor %2.</span><span class="sxs-lookup"><span data-stu-id="c7e04-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="c7e04-117">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="c7e04-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="c7e04-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="c7e04-118">Details</span></span>  
  
|<span data-ttu-id="c7e04-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c7e04-119">Data Item Name</span></span>|<span data-ttu-id="c7e04-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c7e04-120">Data Item Type</span></span>|<span data-ttu-id="c7e04-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7e04-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c7e04-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="c7e04-122">RecordNumber</span></span>|<span data-ttu-id="c7e04-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7e04-123">xs:string</span></span>|<span data-ttu-id="c7e04-124">Número del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c7e04-124">The tracking record number.</span></span>|  
|<span data-ttu-id="c7e04-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="c7e04-125">ProviderId</span></span>|<span data-ttu-id="c7e04-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7e04-126">xs:string</span></span>|<span data-ttu-id="c7e04-127">Identificador del proveedor ETW.</span><span class="sxs-lookup"><span data-stu-id="c7e04-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="c7e04-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c7e04-128">AppDomain</span></span>|<span data-ttu-id="c7e04-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="c7e04-129">xs:string</span></span>|<span data-ttu-id="c7e04-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c7e04-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
