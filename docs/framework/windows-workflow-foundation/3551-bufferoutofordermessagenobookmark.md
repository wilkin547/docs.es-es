---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.date: 03/30/2017
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
ms.openlocfilehash: 89643edde5856688c762b0cf0d188bd4e7ba8a24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512237"
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="30d48-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="30d48-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="30d48-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="30d48-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30d48-104">Id.</span><span class="sxs-lookup"><span data-stu-id="30d48-104">ID</span></span>|<span data-ttu-id="30d48-105">3551</span><span class="sxs-lookup"><span data-stu-id="30d48-105">3551</span></span>|  
|<span data-ttu-id="30d48-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="30d48-106">Keywords</span></span>|<span data-ttu-id="30d48-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="30d48-107">WFServices</span></span>|  
|<span data-ttu-id="30d48-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="30d48-108">Level</span></span>|<span data-ttu-id="30d48-109">Información</span><span class="sxs-lookup"><span data-stu-id="30d48-109">Information</span></span>|  
|<span data-ttu-id="30d48-110">Canal</span><span class="sxs-lookup"><span data-stu-id="30d48-110">Channel</span></span>|<span data-ttu-id="30d48-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="30d48-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="30d48-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="30d48-112">Description</span></span>  
 <span data-ttu-id="30d48-113">Indica que se ha producido un error en la reanudación de marcador.</span><span class="sxs-lookup"><span data-stu-id="30d48-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="30d48-114">La operación de recepción almacenada en búfer se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="30d48-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="30d48-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="30d48-115">Message</span></span>  
 <span data-ttu-id="30d48-116">La operación '%2' en la instancia del servicio '%1' no se puede realizar en este momento.</span><span class="sxs-lookup"><span data-stu-id="30d48-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="30d48-117">Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="30d48-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="30d48-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="30d48-118">Details</span></span>  
  
|<span data-ttu-id="30d48-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="30d48-119">Data Item Name</span></span>|<span data-ttu-id="30d48-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="30d48-120">Data Item Type</span></span>|<span data-ttu-id="30d48-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="30d48-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="30d48-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="30d48-122">OperationName</span></span>|<span data-ttu-id="30d48-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="30d48-123">xs:string</span></span>|<span data-ttu-id="30d48-124">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="30d48-124">The name of the operation.</span></span>|  
|<span data-ttu-id="30d48-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="30d48-125">ServiceInstanceId</span></span>|<span data-ttu-id="30d48-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="30d48-126">xs:string</span></span>|<span data-ttu-id="30d48-127">Identificador de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="30d48-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="30d48-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="30d48-128">AppDomain</span></span>|<span data-ttu-id="30d48-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="30d48-129">xs:string</span></span>|<span data-ttu-id="30d48-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="30d48-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
