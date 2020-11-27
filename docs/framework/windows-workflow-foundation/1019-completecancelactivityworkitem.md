---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 903b497fb3f244fd40c6888829ef71dddd455251
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275484"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="d7e77-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="d7e77-102">1019 - CompleteCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="d7e77-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d7e77-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7e77-104">ID</span><span class="sxs-lookup"><span data-stu-id="d7e77-104">ID</span></span>|<span data-ttu-id="d7e77-105">1019</span><span class="sxs-lookup"><span data-stu-id="d7e77-105">1019</span></span>|  
|<span data-ttu-id="d7e77-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d7e77-106">Keywords</span></span>|<span data-ttu-id="d7e77-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d7e77-107">WFRuntime</span></span>|  
|<span data-ttu-id="d7e77-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d7e77-108">Level</span></span>|<span data-ttu-id="d7e77-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="d7e77-109">Verbose</span></span>|  
|<span data-ttu-id="d7e77-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d7e77-110">Channel</span></span>|<span data-ttu-id="d7e77-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d7e77-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d7e77-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7e77-112">Description</span></span>  

 <span data-ttu-id="d7e77-113">Indica que se ha completado un CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="d7e77-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d7e77-114">Message</span><span class="sxs-lookup"><span data-stu-id="d7e77-114">Message</span></span>  

 <span data-ttu-id="d7e77-115">Un CancelActivityWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="d7e77-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d7e77-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="d7e77-116">Details</span></span>  
  
|<span data-ttu-id="d7e77-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d7e77-117">Data Item Name</span></span>|<span data-ttu-id="d7e77-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d7e77-118">Data Item Type</span></span>|<span data-ttu-id="d7e77-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7e77-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d7e77-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="d7e77-120">Activity</span></span>|<span data-ttu-id="d7e77-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7e77-121">xs:string</span></span>|<span data-ttu-id="d7e77-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d7e77-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d7e77-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d7e77-123">DisplayName</span></span>|<span data-ttu-id="d7e77-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7e77-124">xs:string</span></span>|<span data-ttu-id="d7e77-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d7e77-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d7e77-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d7e77-126">InstanceId</span></span>|<span data-ttu-id="d7e77-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7e77-127">xs:string</span></span>|<span data-ttu-id="d7e77-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d7e77-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d7e77-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d7e77-129">AppDomain</span></span>|<span data-ttu-id="d7e77-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d7e77-130">xs:string</span></span>|<span data-ttu-id="d7e77-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d7e77-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
