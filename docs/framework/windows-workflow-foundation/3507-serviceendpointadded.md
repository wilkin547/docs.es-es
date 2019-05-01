---
title: 3507 - ServiceEndpointAdded
ms.date: 03/30/2017
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
ms.openlocfilehash: c787a1a5af752a3d08e2049cfa0b600b7739e56c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009843"
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="1ead4-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="1ead4-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="1ead4-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1ead4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1ead4-104">ID</span><span class="sxs-lookup"><span data-stu-id="1ead4-104">ID</span></span>|<span data-ttu-id="1ead4-105">3507</span><span class="sxs-lookup"><span data-stu-id="1ead4-105">3507</span></span>|  
|<span data-ttu-id="1ead4-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1ead4-106">Keywords</span></span>|<span data-ttu-id="1ead4-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="1ead4-107">WFServices</span></span>|  
|<span data-ttu-id="1ead4-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="1ead4-108">Level</span></span>|<span data-ttu-id="1ead4-109">Información</span><span class="sxs-lookup"><span data-stu-id="1ead4-109">Information</span></span>|  
|<span data-ttu-id="1ead4-110">Canal</span><span class="sxs-lookup"><span data-stu-id="1ead4-110">Channel</span></span>|<span data-ttu-id="1ead4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1ead4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1ead4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ead4-112">Description</span></span>  
 <span data-ttu-id="1ead4-113">Indica que se ha agregado un punto de conexión de servicio.</span><span class="sxs-lookup"><span data-stu-id="1ead4-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1ead4-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="1ead4-114">Message</span></span>  
 <span data-ttu-id="1ead4-115">Se ha agregado un extremo de servicio a la dirección '%1', enlace '%2', y contrato '%3'.</span><span class="sxs-lookup"><span data-stu-id="1ead4-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1ead4-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="1ead4-116">Details</span></span>  
  
|<span data-ttu-id="1ead4-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="1ead4-117">Data Item Name</span></span>|<span data-ttu-id="1ead4-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="1ead4-118">Data Item Type</span></span>|<span data-ttu-id="1ead4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ead4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1ead4-120">Dirección</span><span class="sxs-lookup"><span data-stu-id="1ead4-120">Address</span></span>|<span data-ttu-id="1ead4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ead4-121">xs:string</span></span>|<span data-ttu-id="1ead4-122">Dirección del extremo.</span><span class="sxs-lookup"><span data-stu-id="1ead4-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="1ead4-123">Enlaces</span><span class="sxs-lookup"><span data-stu-id="1ead4-123">Binding</span></span>|<span data-ttu-id="1ead4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ead4-124">xs:string</span></span>|<span data-ttu-id="1ead4-125">El enlace del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1ead4-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="1ead4-126">Contrato</span><span class="sxs-lookup"><span data-stu-id="1ead4-126">Contract</span></span>|<span data-ttu-id="1ead4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ead4-127">xs:string</span></span>|<span data-ttu-id="1ead4-128">Contrato del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="1ead4-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="1ead4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1ead4-129">AppDomain</span></span>|<span data-ttu-id="1ead4-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="1ead4-130">xs:string</span></span>|<span data-ttu-id="1ead4-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="1ead4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
