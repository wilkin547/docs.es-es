---
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: 903071e7b1f89dc3489b8d3ac05427d699a33a7e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96240763"
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="b93c6-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="b93c6-102">3507 - ServiceEndpointAdded</span></span>

## <a name="properties"></a><span data-ttu-id="b93c6-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b93c6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b93c6-104">ID</span><span class="sxs-lookup"><span data-stu-id="b93c6-104">ID</span></span>|<span data-ttu-id="b93c6-105">3507</span><span class="sxs-lookup"><span data-stu-id="b93c6-105">3507</span></span>|  
|<span data-ttu-id="b93c6-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b93c6-106">Keywords</span></span>|<span data-ttu-id="b93c6-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="b93c6-107">WFServices</span></span>|  
|<span data-ttu-id="b93c6-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b93c6-108">Level</span></span>|<span data-ttu-id="b93c6-109">Información</span><span class="sxs-lookup"><span data-stu-id="b93c6-109">Information</span></span>|  
|<span data-ttu-id="b93c6-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b93c6-110">Channel</span></span>|<span data-ttu-id="b93c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="b93c6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b93c6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b93c6-112">Description</span></span>  

 <span data-ttu-id="b93c6-113">Indica que se ha agregado un punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="b93c6-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b93c6-114">Message</span><span class="sxs-lookup"><span data-stu-id="b93c6-114">Message</span></span>  

 <span data-ttu-id="b93c6-115">Se ha agregado un extremo de servicio a la dirección '%1', enlace '%2', y contrato '%3'.</span><span class="sxs-lookup"><span data-stu-id="b93c6-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b93c6-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="b93c6-116">Details</span></span>  
  
|<span data-ttu-id="b93c6-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b93c6-117">Data Item Name</span></span>|<span data-ttu-id="b93c6-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b93c6-118">Data Item Type</span></span>|<span data-ttu-id="b93c6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="b93c6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b93c6-120">Dirección</span><span class="sxs-lookup"><span data-stu-id="b93c6-120">Address</span></span>|<span data-ttu-id="b93c6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b93c6-121">xs:string</span></span>|<span data-ttu-id="b93c6-122">Dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="b93c6-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="b93c6-123">Enlaces</span><span class="sxs-lookup"><span data-stu-id="b93c6-123">Binding</span></span>|<span data-ttu-id="b93c6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b93c6-124">xs:string</span></span>|<span data-ttu-id="b93c6-125">El enlace del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b93c6-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="b93c6-126">Contrato</span><span class="sxs-lookup"><span data-stu-id="b93c6-126">Contract</span></span>|<span data-ttu-id="b93c6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b93c6-127">xs:string</span></span>|<span data-ttu-id="b93c6-128">Contrato del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b93c6-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="b93c6-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b93c6-129">AppDomain</span></span>|<span data-ttu-id="b93c6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b93c6-130">xs:string</span></span>|<span data-ttu-id="b93c6-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b93c6-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
