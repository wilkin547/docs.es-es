---
title: 3507 - ServiceEndpointAdded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9f06e6cccd9c4ca2907b86372f609f8c72b5e189
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="1b246-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="1b246-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="1b246-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1b246-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1b246-104">Id.</span><span class="sxs-lookup"><span data-stu-id="1b246-104">ID</span></span>|<span data-ttu-id="1b246-105">3507</span><span class="sxs-lookup"><span data-stu-id="1b246-105">3507</span></span>|  
|<span data-ttu-id="1b246-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1b246-106">Keywords</span></span>|<span data-ttu-id="1b246-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="1b246-107">WFServices</span></span>|  
|<span data-ttu-id="1b246-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="1b246-108">Level</span></span>|<span data-ttu-id="1b246-109">Información</span><span class="sxs-lookup"><span data-stu-id="1b246-109">Information</span></span>|  
|<span data-ttu-id="1b246-110">Canal</span><span class="sxs-lookup"><span data-stu-id="1b246-110">Channel</span></span>|<span data-ttu-id="1b246-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1b246-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1b246-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b246-112">Description</span></span>  
 <span data-ttu-id="1b246-113">Indica que se ha agregado un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="1b246-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1b246-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="1b246-114">Message</span></span>  
 <span data-ttu-id="1b246-115">Se ha agregado un extremo de servicio a la dirección '%1', enlace '%2', y contrato '%3'.</span><span class="sxs-lookup"><span data-stu-id="1b246-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1b246-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="1b246-116">Details</span></span>  
  
|<span data-ttu-id="1b246-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="1b246-117">Data Item Name</span></span>|<span data-ttu-id="1b246-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="1b246-118">Data Item Type</span></span>|<span data-ttu-id="1b246-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b246-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1b246-120">Dirección</span><span class="sxs-lookup"><span data-stu-id="1b246-120">Address</span></span>|<span data-ttu-id="1b246-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b246-121">xs:string</span></span>|<span data-ttu-id="1b246-122">Dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="1b246-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="1b246-123">Enlaces</span><span class="sxs-lookup"><span data-stu-id="1b246-123">Binding</span></span>|<span data-ttu-id="1b246-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b246-124">xs:string</span></span>|<span data-ttu-id="1b246-125">El enlace del extremo.</span><span class="sxs-lookup"><span data-stu-id="1b246-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="1b246-126">Contrato</span><span class="sxs-lookup"><span data-stu-id="1b246-126">Contract</span></span>|<span data-ttu-id="1b246-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b246-127">xs:string</span></span>|<span data-ttu-id="1b246-128">Contrato del extremo.</span><span class="sxs-lookup"><span data-stu-id="1b246-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="1b246-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1b246-129">AppDomain</span></span>|<span data-ttu-id="1b246-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="1b246-130">xs:string</span></span>|<span data-ttu-id="1b246-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1b246-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
