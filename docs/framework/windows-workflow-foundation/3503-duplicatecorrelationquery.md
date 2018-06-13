---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: 37a689b30b0bcab9124472deb98627afbe30dfee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511405"
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="cff9f-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="cff9f-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="cff9f-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cff9f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cff9f-104">Id.</span><span class="sxs-lookup"><span data-stu-id="cff9f-104">ID</span></span>|<span data-ttu-id="cff9f-105">3503</span><span class="sxs-lookup"><span data-stu-id="cff9f-105">3503</span></span>|  
|<span data-ttu-id="cff9f-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="cff9f-106">Keywords</span></span>|<span data-ttu-id="cff9f-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="cff9f-107">WFServices</span></span>|  
|<span data-ttu-id="cff9f-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="cff9f-108">Level</span></span>|<span data-ttu-id="cff9f-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="cff9f-109">Warning</span></span>|  
|<span data-ttu-id="cff9f-110">Canal</span><span class="sxs-lookup"><span data-stu-id="cff9f-110">Channel</span></span>|<span data-ttu-id="cff9f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="cff9f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cff9f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cff9f-112">Description</span></span>  
 <span data-ttu-id="cff9f-113">Indica que se encontró una CorrelationQuery duplicada.</span><span class="sxs-lookup"><span data-stu-id="cff9f-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="cff9f-114">La consulta duplicada no se usará al calcular la correlación.</span><span class="sxs-lookup"><span data-stu-id="cff9f-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cff9f-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="cff9f-115">Message</span></span>  
 <span data-ttu-id="cff9f-116">Se encontró una consulta CorrelationQuery duplicada con Where='%1'.</span><span class="sxs-lookup"><span data-stu-id="cff9f-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="cff9f-117">Esta consulta duplicada no se usará al calcular la correlación.</span><span class="sxs-lookup"><span data-stu-id="cff9f-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cff9f-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="cff9f-118">Details</span></span>  
  
|<span data-ttu-id="cff9f-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cff9f-119">Data Item Name</span></span>|<span data-ttu-id="cff9f-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cff9f-120">Data Item Type</span></span>|<span data-ttu-id="cff9f-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="cff9f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cff9f-122">Where</span><span class="sxs-lookup"><span data-stu-id="cff9f-122">Where</span></span>|<span data-ttu-id="cff9f-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="cff9f-123">xs:string</span></span>|<span data-ttu-id="cff9f-124">Proporción Where de la consulta de correlación.</span><span class="sxs-lookup"><span data-stu-id="cff9f-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="cff9f-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cff9f-125">AppDomain</span></span>|<span data-ttu-id="cff9f-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="cff9f-126">xs:string</span></span>|<span data-ttu-id="cff9f-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cff9f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
