---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774418"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="bc747-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="bc747-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="bc747-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bc747-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bc747-104">ID</span><span class="sxs-lookup"><span data-stu-id="bc747-104">ID</span></span>|<span data-ttu-id="bc747-105">39458</span><span class="sxs-lookup"><span data-stu-id="bc747-105">39458</span></span>|  
|<span data-ttu-id="bc747-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="bc747-106">Keywords</span></span>|<span data-ttu-id="bc747-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="bc747-107">WFTracking</span></span>|  
|<span data-ttu-id="bc747-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="bc747-108">Level</span></span>|<span data-ttu-id="bc747-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="bc747-109">Warning</span></span>|  
|<span data-ttu-id="bc747-110">Canal</span><span class="sxs-lookup"><span data-stu-id="bc747-110">Channel</span></span>|<span data-ttu-id="bc747-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="bc747-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bc747-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc747-112">Description</span></span>  
 <span data-ttu-id="bc747-113">Indica que se ha truncado un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bc747-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="bc747-114">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="bc747-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bc747-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="bc747-115">Message</span></span>  
 <span data-ttu-id="bc747-116">Se ha escrito un registro de seguimiento %1 truncado en la sesión de ETW con el proveedor %2.</span><span class="sxs-lookup"><span data-stu-id="bc747-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="bc747-117">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="bc747-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="bc747-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="bc747-118">Details</span></span>  
  
|<span data-ttu-id="bc747-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="bc747-119">Data Item Name</span></span>|<span data-ttu-id="bc747-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="bc747-120">Data Item Type</span></span>|<span data-ttu-id="bc747-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc747-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bc747-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="bc747-122">RecordNumber</span></span>|<span data-ttu-id="bc747-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc747-123">xs:string</span></span>|<span data-ttu-id="bc747-124">Número del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bc747-124">The tracking record number.</span></span>|  
|<span data-ttu-id="bc747-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="bc747-125">ProviderId</span></span>|<span data-ttu-id="bc747-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc747-126">xs:string</span></span>|<span data-ttu-id="bc747-127">Identificador del proveedor ETW.</span><span class="sxs-lookup"><span data-stu-id="bc747-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="bc747-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="bc747-128">AppDomain</span></span>|<span data-ttu-id="bc747-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="bc747-129">xs:string</span></span>|<span data-ttu-id="bc747-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="bc747-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
