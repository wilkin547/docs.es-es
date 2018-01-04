---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 435a6a4390d52555d353a25ac119934087cf9c87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="87cac-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="87cac-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="87cac-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="87cac-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87cac-104">Id.</span><span class="sxs-lookup"><span data-stu-id="87cac-104">ID</span></span>|<span data-ttu-id="87cac-105">3550</span><span class="sxs-lookup"><span data-stu-id="87cac-105">3550</span></span>|  
|<span data-ttu-id="87cac-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="87cac-106">Keywords</span></span>|<span data-ttu-id="87cac-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="87cac-107">WFServices</span></span>|  
|<span data-ttu-id="87cac-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="87cac-108">Level</span></span>|<span data-ttu-id="87cac-109">Información</span><span class="sxs-lookup"><span data-stu-id="87cac-109">Information</span></span>|  
|<span data-ttu-id="87cac-110">Canal</span><span class="sxs-lookup"><span data-stu-id="87cac-110">Channel</span></span>|<span data-ttu-id="87cac-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="87cac-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="87cac-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="87cac-112">Description</span></span>  
 <span data-ttu-id="87cac-113">Indica que se ha producido un error en la recepción almacenada en el búfer.</span><span class="sxs-lookup"><span data-stu-id="87cac-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="87cac-114">La operación se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="87cac-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="87cac-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="87cac-115">Message</span></span>  
 <span data-ttu-id="87cac-116">La operación '%1' no se puede realizar en este momento.</span><span class="sxs-lookup"><span data-stu-id="87cac-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="87cac-117">Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="87cac-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="87cac-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="87cac-118">Details</span></span>  
  
|<span data-ttu-id="87cac-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="87cac-119">Data Item Name</span></span>|<span data-ttu-id="87cac-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="87cac-120">Data Item Type</span></span>|<span data-ttu-id="87cac-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="87cac-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="87cac-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="87cac-122">OperationName</span></span>|<span data-ttu-id="87cac-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="87cac-123">xs:string</span></span>|<span data-ttu-id="87cac-124">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="87cac-124">The name of the operation.</span></span>|  
|<span data-ttu-id="87cac-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="87cac-125">AppDomain</span></span>|<span data-ttu-id="87cac-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="87cac-126">xs:string</span></span>|<span data-ttu-id="87cac-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="87cac-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
