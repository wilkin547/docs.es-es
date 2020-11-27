---
title: 2577 - TryCatchExceptionDuringCancelation
ms.date: 03/30/2017
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
ms.openlocfilehash: 33c68984e88eaa5e3028899a7c3066c94a65e8eb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96271244"
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="f3e2d-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="f3e2d-102">2577 - TryCatchExceptionDuringCancelation</span></span>

## <a name="properties"></a><span data-ttu-id="f3e2d-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f3e2d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f3e2d-104">ID</span><span class="sxs-lookup"><span data-stu-id="f3e2d-104">ID</span></span>|<span data-ttu-id="f3e2d-105">2577</span><span class="sxs-lookup"><span data-stu-id="f3e2d-105">2577</span></span>|  
|<span data-ttu-id="f3e2d-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f3e2d-106">Keywords</span></span>|<span data-ttu-id="f3e2d-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="f3e2d-107">WFActivities</span></span>|  
|<span data-ttu-id="f3e2d-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f3e2d-108">Level</span></span>|<span data-ttu-id="f3e2d-109">Advertencia</span><span class="sxs-lookup"><span data-stu-id="f3e2d-109">Warning</span></span>|  
|<span data-ttu-id="f3e2d-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f3e2d-110">Channel</span></span>|<span data-ttu-id="f3e2d-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f3e2d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f3e2d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3e2d-112">Description</span></span>  

 <span data-ttu-id="f3e2d-113">Indica que una actividad secundaria de la actividad TryCatch ha producido una excepción durante la cancelación.</span><span class="sxs-lookup"><span data-stu-id="f3e2d-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f3e2d-114">Message</span><span class="sxs-lookup"><span data-stu-id="f3e2d-114">Message</span></span>  

 <span data-ttu-id="f3e2d-115">Una actividad secundaria de la actividad TryCatch '%1' produjo una excepción durante la cancelación.</span><span class="sxs-lookup"><span data-stu-id="f3e2d-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f3e2d-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="f3e2d-116">Details</span></span>  
  
|<span data-ttu-id="f3e2d-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f3e2d-117">Data Item Name</span></span>|<span data-ttu-id="f3e2d-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f3e2d-118">Data Item Type</span></span>|<span data-ttu-id="f3e2d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3e2d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f3e2d-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f3e2d-120">DisplayName</span></span>|<span data-ttu-id="f3e2d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3e2d-121">xs:string</span></span>|<span data-ttu-id="f3e2d-122">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="f3e2d-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="f3e2d-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f3e2d-123">AppDomain</span></span>|<span data-ttu-id="f3e2d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f3e2d-124">xs:string</span></span>|<span data-ttu-id="f3e2d-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f3e2d-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
