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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 463482bbcc659c6dba15b854ff06f41754f63ccc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="9d52b-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="9d52b-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="9d52b-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9d52b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9d52b-104">Id.</span><span class="sxs-lookup"><span data-stu-id="9d52b-104">ID</span></span>|<span data-ttu-id="9d52b-105">3507</span><span class="sxs-lookup"><span data-stu-id="9d52b-105">3507</span></span>|  
|<span data-ttu-id="9d52b-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9d52b-106">Keywords</span></span>|<span data-ttu-id="9d52b-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="9d52b-107">WFServices</span></span>|  
|<span data-ttu-id="9d52b-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="9d52b-108">Level</span></span>|<span data-ttu-id="9d52b-109">Información</span><span class="sxs-lookup"><span data-stu-id="9d52b-109">Information</span></span>|  
|<span data-ttu-id="9d52b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="9d52b-110">Channel</span></span>|<span data-ttu-id="9d52b-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9d52b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9d52b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d52b-112">Description</span></span>  
 <span data-ttu-id="9d52b-113">Indica que se ha agregado un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="9d52b-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9d52b-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="9d52b-114">Message</span></span>  
 <span data-ttu-id="9d52b-115">Se ha agregado un extremo de servicio a la dirección '%1', enlace '%2', y contrato '%3'.</span><span class="sxs-lookup"><span data-stu-id="9d52b-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9d52b-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="9d52b-116">Details</span></span>  
  
|<span data-ttu-id="9d52b-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9d52b-117">Data Item Name</span></span>|<span data-ttu-id="9d52b-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9d52b-118">Data Item Type</span></span>|<span data-ttu-id="9d52b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d52b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9d52b-120">Dirección</span><span class="sxs-lookup"><span data-stu-id="9d52b-120">Address</span></span>|<span data-ttu-id="9d52b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d52b-121">xs:string</span></span>|<span data-ttu-id="9d52b-122">Dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="9d52b-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="9d52b-123">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9d52b-123">Binding</span></span>|<span data-ttu-id="9d52b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d52b-124">xs:string</span></span>|<span data-ttu-id="9d52b-125">El enlace del extremo.</span><span class="sxs-lookup"><span data-stu-id="9d52b-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="9d52b-126">Contrato</span><span class="sxs-lookup"><span data-stu-id="9d52b-126">Contract</span></span>|<span data-ttu-id="9d52b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d52b-127">xs:string</span></span>|<span data-ttu-id="9d52b-128">Contrato del extremo.</span><span class="sxs-lookup"><span data-stu-id="9d52b-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="9d52b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9d52b-129">AppDomain</span></span>|<span data-ttu-id="9d52b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9d52b-130">xs:string</span></span>|<span data-ttu-id="9d52b-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9d52b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
