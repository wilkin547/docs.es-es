---
description: 'Más información acerca de: 3551-BufferOutOfOrderMessageNoBookmark'
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 573056fed1753ac55c51d9a074047e8eea15e229
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778001"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="033bf-103">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="033bf-103">3551 - BufferOutOfOrderMessageNoBookmark</span></span>

## <a name="properties"></a><span data-ttu-id="033bf-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="033bf-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="033bf-105">Id.</span><span class="sxs-lookup"><span data-stu-id="033bf-105">ID</span></span>|<span data-ttu-id="033bf-106">3551</span><span class="sxs-lookup"><span data-stu-id="033bf-106">3551</span></span>|  
|<span data-ttu-id="033bf-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="033bf-107">Keywords</span></span>|<span data-ttu-id="033bf-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="033bf-108">WFServices</span></span>|  
|<span data-ttu-id="033bf-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="033bf-109">Level</span></span>|<span data-ttu-id="033bf-110">Información</span><span class="sxs-lookup"><span data-stu-id="033bf-110">Information</span></span>|  
|<span data-ttu-id="033bf-111">Canal</span><span class="sxs-lookup"><span data-stu-id="033bf-111">Channel</span></span>|<span data-ttu-id="033bf-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="033bf-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="033bf-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="033bf-113">Description</span></span>  

 <span data-ttu-id="033bf-114">Indica que se ha producido un error en la reanudación de marcador.</span><span class="sxs-lookup"><span data-stu-id="033bf-114">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="033bf-115">La operación de recepción almacenada en búfer se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="033bf-115">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="033bf-116">Message</span><span class="sxs-lookup"><span data-stu-id="033bf-116">Message</span></span>  

 <span data-ttu-id="033bf-117">La operación '%2' en la instancia del servicio '%1' no se puede realizar en este momento.</span><span class="sxs-lookup"><span data-stu-id="033bf-117">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="033bf-118">Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="033bf-118">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="033bf-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="033bf-119">Details</span></span>  
  
|<span data-ttu-id="033bf-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="033bf-120">Data Item Name</span></span>|<span data-ttu-id="033bf-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="033bf-121">Data Item Type</span></span>|<span data-ttu-id="033bf-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="033bf-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="033bf-123">OperationName</span><span class="sxs-lookup"><span data-stu-id="033bf-123">OperationName</span></span>|<span data-ttu-id="033bf-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="033bf-124">xs:string</span></span>|<span data-ttu-id="033bf-125">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="033bf-125">The name of the operation.</span></span>|  
|<span data-ttu-id="033bf-126">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="033bf-126">ServiceInstanceId</span></span>|<span data-ttu-id="033bf-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="033bf-127">xs:string</span></span>|<span data-ttu-id="033bf-128">Identificador de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="033bf-128">The id of the service instance.</span></span>|  
|<span data-ttu-id="033bf-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="033bf-129">AppDomain</span></span>|<span data-ttu-id="033bf-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="033bf-130">xs:string</span></span>|<span data-ttu-id="033bf-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="033bf-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
