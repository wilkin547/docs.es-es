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
ms.openlocfilehash: 1d2bc07cff75fce7ddb50da9f54d161d7f235cab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="614fd-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="614fd-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="614fd-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="614fd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="614fd-104">Id.</span><span class="sxs-lookup"><span data-stu-id="614fd-104">ID</span></span>|<span data-ttu-id="614fd-105">39458</span><span class="sxs-lookup"><span data-stu-id="614fd-105">39458</span></span>|  
|<span data-ttu-id="614fd-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="614fd-106">Keywords</span></span>|<span data-ttu-id="614fd-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="614fd-107">WFTracking</span></span>|  
|<span data-ttu-id="614fd-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="614fd-108">Level</span></span>|<span data-ttu-id="614fd-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="614fd-109">Warning</span></span>|  
|<span data-ttu-id="614fd-110">Canal</span><span class="sxs-lookup"><span data-stu-id="614fd-110">Channel</span></span>|<span data-ttu-id="614fd-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="614fd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="614fd-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="614fd-112">Description</span></span>  
 <span data-ttu-id="614fd-113">Indica que se ha truncado un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="614fd-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="614fd-114">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="614fd-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="614fd-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="614fd-115">Message</span></span>  
 <span data-ttu-id="614fd-116">Se ha escrito un registro de seguimiento %1 truncado en la sesión de ETW con el proveedor %2.</span><span class="sxs-lookup"><span data-stu-id="614fd-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="614fd-117">Se han quitado las variables, anotaciones y datos del usuario.</span><span class="sxs-lookup"><span data-stu-id="614fd-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="614fd-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="614fd-118">Details</span></span>  
  
|<span data-ttu-id="614fd-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="614fd-119">Data Item Name</span></span>|<span data-ttu-id="614fd-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="614fd-120">Data Item Type</span></span>|<span data-ttu-id="614fd-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="614fd-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="614fd-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="614fd-122">RecordNumber</span></span>|<span data-ttu-id="614fd-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="614fd-123">xs:string</span></span>|<span data-ttu-id="614fd-124">Número del registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="614fd-124">The tracking record number.</span></span>|  
|<span data-ttu-id="614fd-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="614fd-125">ProviderId</span></span>|<span data-ttu-id="614fd-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="614fd-126">xs:string</span></span>|<span data-ttu-id="614fd-127">Identificador del proveedor ETW.</span><span class="sxs-lookup"><span data-stu-id="614fd-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="614fd-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="614fd-128">AppDomain</span></span>|<span data-ttu-id="614fd-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="614fd-129">xs:string</span></span>|<span data-ttu-id="614fd-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="614fd-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
