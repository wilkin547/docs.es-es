---
title: 3503 - DuplicateCorrelationQuery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4b86289340c35d24552b1d524a3cceaacb2f0420
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="b642c-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="b642c-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="b642c-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b642c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b642c-104">Id.</span><span class="sxs-lookup"><span data-stu-id="b642c-104">ID</span></span>|<span data-ttu-id="b642c-105">3503</span><span class="sxs-lookup"><span data-stu-id="b642c-105">3503</span></span>|  
|<span data-ttu-id="b642c-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b642c-106">Keywords</span></span>|<span data-ttu-id="b642c-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="b642c-107">WFServices</span></span>|  
|<span data-ttu-id="b642c-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b642c-108">Level</span></span>|<span data-ttu-id="b642c-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="b642c-109">Warning</span></span>|  
|<span data-ttu-id="b642c-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b642c-110">Channel</span></span>|<span data-ttu-id="b642c-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b642c-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b642c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b642c-112">Description</span></span>  
 <span data-ttu-id="b642c-113">Indica que se encontró una CorrelationQuery duplicada.</span><span class="sxs-lookup"><span data-stu-id="b642c-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="b642c-114">La consulta duplicada no se usará al calcular la correlación.</span><span class="sxs-lookup"><span data-stu-id="b642c-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b642c-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b642c-115">Message</span></span>  
 <span data-ttu-id="b642c-116">Se encontró una consulta CorrelationQuery duplicada con Where='%1'.</span><span class="sxs-lookup"><span data-stu-id="b642c-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="b642c-117">Esta consulta duplicada no se usará al calcular la correlación.</span><span class="sxs-lookup"><span data-stu-id="b642c-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b642c-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="b642c-118">Details</span></span>  
  
|<span data-ttu-id="b642c-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b642c-119">Data Item Name</span></span>|<span data-ttu-id="b642c-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b642c-120">Data Item Type</span></span>|<span data-ttu-id="b642c-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="b642c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b642c-122">Where</span><span class="sxs-lookup"><span data-stu-id="b642c-122">Where</span></span>|<span data-ttu-id="b642c-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="b642c-123">xs:string</span></span>|<span data-ttu-id="b642c-124">Proporción Where de la consulta de correlación.</span><span class="sxs-lookup"><span data-stu-id="b642c-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="b642c-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b642c-125">AppDomain</span></span>|<span data-ttu-id="b642c-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="b642c-126">xs:string</span></span>|<span data-ttu-id="b642c-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b642c-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
