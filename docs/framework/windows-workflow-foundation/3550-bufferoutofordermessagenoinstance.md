---
description: 'Más información acerca de: 3550-BufferOutOfOrderMessageNoInstance'
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.date: 03/30/2017
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
ms.openlocfilehash: cb51f9fa32de1b56560f9593dae2ec82c100dc65
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631455"
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="d4c3f-103">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="d4c3f-103">3550 - BufferOutOfOrderMessageNoInstance</span></span>

## <a name="properties"></a><span data-ttu-id="d4c3f-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d4c3f-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4c3f-105">Id.</span><span class="sxs-lookup"><span data-stu-id="d4c3f-105">ID</span></span>|<span data-ttu-id="d4c3f-106">3550</span><span class="sxs-lookup"><span data-stu-id="d4c3f-106">3550</span></span>|  
|<span data-ttu-id="d4c3f-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4c3f-107">Keywords</span></span>|<span data-ttu-id="d4c3f-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="d4c3f-108">WFServices</span></span>|  
|<span data-ttu-id="d4c3f-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="d4c3f-109">Level</span></span>|<span data-ttu-id="d4c3f-110">Información</span><span class="sxs-lookup"><span data-stu-id="d4c3f-110">Information</span></span>|  
|<span data-ttu-id="d4c3f-111">Canal</span><span class="sxs-lookup"><span data-stu-id="d4c3f-111">Channel</span></span>|<span data-ttu-id="d4c3f-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="d4c3f-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d4c3f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4c3f-113">Description</span></span>  

 <span data-ttu-id="d4c3f-114">Indica que se ha producido un error en la recepción almacenada en el búfer.</span><span class="sxs-lookup"><span data-stu-id="d4c3f-114">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="d4c3f-115">La operación se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="d4c3f-115">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d4c3f-116">Message</span><span class="sxs-lookup"><span data-stu-id="d4c3f-116">Message</span></span>  

 <span data-ttu-id="d4c3f-117">La operación '%1' no se puede realizar en este momento.</span><span class="sxs-lookup"><span data-stu-id="d4c3f-117">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="d4c3f-118">Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="d4c3f-118">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4c3f-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="d4c3f-119">Details</span></span>  
  
|<span data-ttu-id="d4c3f-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d4c3f-120">Data Item Name</span></span>|<span data-ttu-id="d4c3f-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d4c3f-121">Data Item Type</span></span>|<span data-ttu-id="d4c3f-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4c3f-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d4c3f-123">OperationName</span><span class="sxs-lookup"><span data-stu-id="d4c3f-123">OperationName</span></span>|<span data-ttu-id="d4c3f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4c3f-124">xs:string</span></span>|<span data-ttu-id="d4c3f-125">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="d4c3f-125">The name of the operation.</span></span>|  
|<span data-ttu-id="d4c3f-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d4c3f-126">AppDomain</span></span>|<span data-ttu-id="d4c3f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4c3f-127">xs:string</span></span>|<span data-ttu-id="d4c3f-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d4c3f-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
