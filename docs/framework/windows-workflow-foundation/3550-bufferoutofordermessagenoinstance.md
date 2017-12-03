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
ms.openlocfilehash: eabc6a6915560d8c49e695d5d681f1544689cb07
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="c9169-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="c9169-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="c9169-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c9169-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9169-104">Id.</span><span class="sxs-lookup"><span data-stu-id="c9169-104">ID</span></span>|<span data-ttu-id="c9169-105">3550</span><span class="sxs-lookup"><span data-stu-id="c9169-105">3550</span></span>|  
|<span data-ttu-id="c9169-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="c9169-106">Keywords</span></span>|<span data-ttu-id="c9169-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="c9169-107">WFServices</span></span>|  
|<span data-ttu-id="c9169-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="c9169-108">Level</span></span>|<span data-ttu-id="c9169-109">Información</span><span class="sxs-lookup"><span data-stu-id="c9169-109">Information</span></span>|  
|<span data-ttu-id="c9169-110">Canal</span><span class="sxs-lookup"><span data-stu-id="c9169-110">Channel</span></span>|<span data-ttu-id="c9169-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="c9169-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c9169-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9169-112">Description</span></span>  
 <span data-ttu-id="c9169-113">Indica que se ha producido un error en la recepción almacenada en el búfer.</span><span class="sxs-lookup"><span data-stu-id="c9169-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="c9169-114">La operación se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="c9169-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c9169-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="c9169-115">Message</span></span>  
 <span data-ttu-id="c9169-116">La operación '%1' no se puede realizar en este momento.</span><span class="sxs-lookup"><span data-stu-id="c9169-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="c9169-117">Se intentará de nuevo cuando la instancia del servicio esté lista para procesar esta operación en particular.</span><span class="sxs-lookup"><span data-stu-id="c9169-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c9169-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="c9169-118">Details</span></span>  
  
|<span data-ttu-id="c9169-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c9169-119">Data Item Name</span></span>|<span data-ttu-id="c9169-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="c9169-120">Data Item Type</span></span>|<span data-ttu-id="c9169-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9169-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c9169-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="c9169-122">OperationName</span></span>|<span data-ttu-id="c9169-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="c9169-123">xs:string</span></span>|<span data-ttu-id="c9169-124">Nombre de la operación.</span><span class="sxs-lookup"><span data-stu-id="c9169-124">The name of the operation.</span></span>|  
|<span data-ttu-id="c9169-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c9169-125">AppDomain</span></span>|<span data-ttu-id="c9169-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="c9169-126">xs:string</span></span>|<span data-ttu-id="c9169-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="c9169-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
