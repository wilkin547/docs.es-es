---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6dc505a4e0e79b37f9adff41b80dcba55215576f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="b4b82-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="b4b82-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="b4b82-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b4b82-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b4b82-104">Id.</span><span class="sxs-lookup"><span data-stu-id="b4b82-104">ID</span></span>|<span data-ttu-id="b4b82-105">3551</span><span class="sxs-lookup"><span data-stu-id="b4b82-105">3551</span></span>|  
|<span data-ttu-id="b4b82-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b4b82-106">Keywords</span></span>|<span data-ttu-id="b4b82-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="b4b82-107">WFServices</span></span>|  
|<span data-ttu-id="b4b82-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b4b82-108">Level</span></span>|<span data-ttu-id="b4b82-109">Información</span><span class="sxs-lookup"><span data-stu-id="b4b82-109">Information</span></span>|  
|<span data-ttu-id="b4b82-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b4b82-110">Channel</span></span>|<span data-ttu-id="b4b82-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b4b82-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b4b82-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4b82-112">Description</span></span>  
 <span data-ttu-id="b4b82-113">Indica que se ha producido un error en la reanudación de marcador.</span><span class="sxs-lookup"><span data-stu-id="b4b82-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="b4b82-114">La operación de recepción almacenada en búfer se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="b4b82-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b4b82-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b4b82-115">Message</span></span>  
 <span data-ttu-id="b4b82-116">La operación '%2' en la instancia del servicio '%1' no se puede realizar en este momento.</span><span class="sxs-lookup"><span data-stu-id="b4b82-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="b4b82-117">Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="b4b82-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b4b82-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="b4b82-118">Details</span></span>  
  
|<span data-ttu-id="b4b82-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b4b82-119">Data Item Name</span></span>|<span data-ttu-id="b4b82-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b4b82-120">Data Item Type</span></span>|<span data-ttu-id="b4b82-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4b82-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b4b82-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="b4b82-122">OperationName</span></span>|<span data-ttu-id="b4b82-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4b82-123">xs:string</span></span>|<span data-ttu-id="b4b82-124">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="b4b82-124">The name of the operation.</span></span>|  
|<span data-ttu-id="b4b82-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="b4b82-125">ServiceInstanceId</span></span>|<span data-ttu-id="b4b82-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4b82-126">xs:string</span></span>|<span data-ttu-id="b4b82-127">Identificador de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="b4b82-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="b4b82-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b4b82-128">AppDomain</span></span>|<span data-ttu-id="b4b82-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="b4b82-129">xs:string</span></span>|<span data-ttu-id="b4b82-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b4b82-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
