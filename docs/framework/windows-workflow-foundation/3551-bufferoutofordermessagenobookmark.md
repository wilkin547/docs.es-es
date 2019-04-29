---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 89643edde5856688c762b0cf0d188bd4e7ba8a24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755537"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="88a2e-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="88a2e-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="88a2e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="88a2e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88a2e-104">ID</span><span class="sxs-lookup"><span data-stu-id="88a2e-104">ID</span></span>|<span data-ttu-id="88a2e-105">3551</span><span class="sxs-lookup"><span data-stu-id="88a2e-105">3551</span></span>|  
|<span data-ttu-id="88a2e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="88a2e-106">Keywords</span></span>|<span data-ttu-id="88a2e-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="88a2e-107">WFServices</span></span>|  
|<span data-ttu-id="88a2e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="88a2e-108">Level</span></span>|<span data-ttu-id="88a2e-109">Información</span><span class="sxs-lookup"><span data-stu-id="88a2e-109">Information</span></span>|  
|<span data-ttu-id="88a2e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="88a2e-110">Channel</span></span>|<span data-ttu-id="88a2e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="88a2e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="88a2e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="88a2e-112">Description</span></span>  
 <span data-ttu-id="88a2e-113">Indica que se ha producido un error en la reanudación de marcador.</span><span class="sxs-lookup"><span data-stu-id="88a2e-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="88a2e-114">La operación de recepción almacenada en búfer se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="88a2e-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="88a2e-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="88a2e-115">Message</span></span>  
 <span data-ttu-id="88a2e-116">La operación '%2' en la instancia del servicio '%1' no se puede realizar en este momento.</span><span class="sxs-lookup"><span data-stu-id="88a2e-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="88a2e-117">Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="88a2e-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="88a2e-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="88a2e-118">Details</span></span>  
  
|<span data-ttu-id="88a2e-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="88a2e-119">Data Item Name</span></span>|<span data-ttu-id="88a2e-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="88a2e-120">Data Item Type</span></span>|<span data-ttu-id="88a2e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="88a2e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="88a2e-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="88a2e-122">OperationName</span></span>|<span data-ttu-id="88a2e-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="88a2e-123">xs:string</span></span>|<span data-ttu-id="88a2e-124">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="88a2e-124">The name of the operation.</span></span>|  
|<span data-ttu-id="88a2e-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="88a2e-125">ServiceInstanceId</span></span>|<span data-ttu-id="88a2e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="88a2e-126">xs:string</span></span>|<span data-ttu-id="88a2e-127">Identificador de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="88a2e-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="88a2e-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="88a2e-128">AppDomain</span></span>|<span data-ttu-id="88a2e-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="88a2e-129">xs:string</span></span>|<span data-ttu-id="88a2e-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="88a2e-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
