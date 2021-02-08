---
description: 'Más información acerca de: 3503-DuplicateCorrelationQuery'
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: a8e1e41aad3aa1b273d8f8a5d7b0768fabe4e658
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778079"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="cb0e9-103">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="cb0e9-103">3503 - DuplicateCorrelationQuery</span></span>

## <a name="properties"></a><span data-ttu-id="cb0e9-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cb0e9-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb0e9-105">Id.</span><span class="sxs-lookup"><span data-stu-id="cb0e9-105">ID</span></span>|<span data-ttu-id="cb0e9-106">3503</span><span class="sxs-lookup"><span data-stu-id="cb0e9-106">3503</span></span>|  
|<span data-ttu-id="cb0e9-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="cb0e9-107">Keywords</span></span>|<span data-ttu-id="cb0e9-108">WFServices</span><span class="sxs-lookup"><span data-stu-id="cb0e9-108">WFServices</span></span>|  
|<span data-ttu-id="cb0e9-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="cb0e9-109">Level</span></span>|<span data-ttu-id="cb0e9-110">Advertencia</span><span class="sxs-lookup"><span data-stu-id="cb0e9-110">Warning</span></span>|  
|<span data-ttu-id="cb0e9-111">Canal</span><span class="sxs-lookup"><span data-stu-id="cb0e9-111">Channel</span></span>|<span data-ttu-id="cb0e9-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="cb0e9-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cb0e9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb0e9-113">Description</span></span>  

 <span data-ttu-id="cb0e9-114">Indica que se encontró una CorrelationQuery duplicada.</span><span class="sxs-lookup"><span data-stu-id="cb0e9-114">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="cb0e9-115">La consulta duplicada no se usará al calcular la correlación.</span><span class="sxs-lookup"><span data-stu-id="cb0e9-115">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cb0e9-116">Message</span><span class="sxs-lookup"><span data-stu-id="cb0e9-116">Message</span></span>  

 <span data-ttu-id="cb0e9-117">Se encontró una consulta CorrelationQuery duplicada con Where='%1'.</span><span class="sxs-lookup"><span data-stu-id="cb0e9-117">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="cb0e9-118">Esta consulta duplicada no se usará al calcular la correlación.</span><span class="sxs-lookup"><span data-stu-id="cb0e9-118">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cb0e9-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="cb0e9-119">Details</span></span>  
  
|<span data-ttu-id="cb0e9-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cb0e9-120">Data Item Name</span></span>|<span data-ttu-id="cb0e9-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cb0e9-121">Data Item Type</span></span>|<span data-ttu-id="cb0e9-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb0e9-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cb0e9-123">Where</span><span class="sxs-lookup"><span data-stu-id="cb0e9-123">Where</span></span>|<span data-ttu-id="cb0e9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb0e9-124">xs:string</span></span>|<span data-ttu-id="cb0e9-125">Proporción Where de la consulta de correlación.</span><span class="sxs-lookup"><span data-stu-id="cb0e9-125">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="cb0e9-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cb0e9-126">AppDomain</span></span>|<span data-ttu-id="cb0e9-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb0e9-127">xs:string</span></span>|<span data-ttu-id="cb0e9-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cb0e9-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
