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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a380def22c270a3fafe118a426609a93862c447
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="3a8e9-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="3a8e9-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="3a8e9-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3a8e9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a8e9-104">Id.</span><span class="sxs-lookup"><span data-stu-id="3a8e9-104">ID</span></span>|<span data-ttu-id="3a8e9-105">3551</span><span class="sxs-lookup"><span data-stu-id="3a8e9-105">3551</span></span>|  
|<span data-ttu-id="3a8e9-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3a8e9-106">Keywords</span></span>|<span data-ttu-id="3a8e9-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="3a8e9-107">WFServices</span></span>|  
|<span data-ttu-id="3a8e9-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3a8e9-108">Level</span></span>|<span data-ttu-id="3a8e9-109">Información</span><span class="sxs-lookup"><span data-stu-id="3a8e9-109">Information</span></span>|  
|<span data-ttu-id="3a8e9-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3a8e9-110">Channel</span></span>|<span data-ttu-id="3a8e9-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="3a8e9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3a8e9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a8e9-112">Description</span></span>  
 <span data-ttu-id="3a8e9-113">Indica que se ha producido un error en la reanudación de marcador.</span><span class="sxs-lookup"><span data-stu-id="3a8e9-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="3a8e9-114">La operación de recepción almacenada en búfer se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="3a8e9-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3a8e9-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="3a8e9-115">Message</span></span>  
 <span data-ttu-id="3a8e9-116">La operación '%2' en la instancia del servicio '%1' no se puede realizar en este momento.</span><span class="sxs-lookup"><span data-stu-id="3a8e9-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="3a8e9-117">Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="3a8e9-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3a8e9-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="3a8e9-118">Details</span></span>  
  
|<span data-ttu-id="3a8e9-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3a8e9-119">Data Item Name</span></span>|<span data-ttu-id="3a8e9-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3a8e9-120">Data Item Type</span></span>|<span data-ttu-id="3a8e9-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a8e9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3a8e9-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="3a8e9-122">OperationName</span></span>|<span data-ttu-id="3a8e9-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="3a8e9-123">xs:string</span></span>|<span data-ttu-id="3a8e9-124">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="3a8e9-124">The name of the operation.</span></span>|  
|<span data-ttu-id="3a8e9-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="3a8e9-125">ServiceInstanceId</span></span>|<span data-ttu-id="3a8e9-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="3a8e9-126">xs:string</span></span>|<span data-ttu-id="3a8e9-127">Identificador de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="3a8e9-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="3a8e9-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3a8e9-128">AppDomain</span></span>|<span data-ttu-id="3a8e9-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="3a8e9-129">xs:string</span></span>|<span data-ttu-id="3a8e9-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3a8e9-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
