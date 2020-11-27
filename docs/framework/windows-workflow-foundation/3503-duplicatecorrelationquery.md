---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: e1e64824ee9a95757ed7c00aa17fa80898219401
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270333"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="f0511-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="f0511-102">3503 - DuplicateCorrelationQuery</span></span>

## <a name="properties"></a><span data-ttu-id="f0511-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f0511-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0511-104">ID</span><span class="sxs-lookup"><span data-stu-id="f0511-104">ID</span></span>|<span data-ttu-id="f0511-105">3503</span><span class="sxs-lookup"><span data-stu-id="f0511-105">3503</span></span>|  
|<span data-ttu-id="f0511-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f0511-106">Keywords</span></span>|<span data-ttu-id="f0511-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="f0511-107">WFServices</span></span>|  
|<span data-ttu-id="f0511-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f0511-108">Level</span></span>|<span data-ttu-id="f0511-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="f0511-109">Warning</span></span>|  
|<span data-ttu-id="f0511-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f0511-110">Channel</span></span>|<span data-ttu-id="f0511-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f0511-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f0511-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0511-112">Description</span></span>  

 <span data-ttu-id="f0511-113">Indica que se encontró una CorrelationQuery duplicada.</span><span class="sxs-lookup"><span data-stu-id="f0511-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="f0511-114">La consulta duplicada no se usará al calcular la correlación.</span><span class="sxs-lookup"><span data-stu-id="f0511-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f0511-115">Message</span><span class="sxs-lookup"><span data-stu-id="f0511-115">Message</span></span>  

 <span data-ttu-id="f0511-116">Se encontró una consulta CorrelationQuery duplicada con Where='%1'.</span><span class="sxs-lookup"><span data-stu-id="f0511-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="f0511-117">Esta consulta duplicada no se usará al calcular la correlación.</span><span class="sxs-lookup"><span data-stu-id="f0511-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f0511-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="f0511-118">Details</span></span>  
  
|<span data-ttu-id="f0511-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f0511-119">Data Item Name</span></span>|<span data-ttu-id="f0511-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f0511-120">Data Item Type</span></span>|<span data-ttu-id="f0511-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="f0511-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f0511-122">Where</span><span class="sxs-lookup"><span data-stu-id="f0511-122">Where</span></span>|<span data-ttu-id="f0511-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0511-123">xs:string</span></span>|<span data-ttu-id="f0511-124">Proporción Where de la consulta de correlación.</span><span class="sxs-lookup"><span data-stu-id="f0511-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="f0511-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f0511-125">AppDomain</span></span>|<span data-ttu-id="f0511-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f0511-126">xs:string</span></span>|<span data-ttu-id="f0511-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f0511-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
