---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: c1558e19b0de2dc5d22d4356b0f80c35e5b4fbc1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275510"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="cb0d4-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="cb0d4-102">1018 - StartCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="cb0d4-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cb0d4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cb0d4-104">ID</span><span class="sxs-lookup"><span data-stu-id="cb0d4-104">ID</span></span>|<span data-ttu-id="cb0d4-105">1018</span><span class="sxs-lookup"><span data-stu-id="cb0d4-105">1018</span></span>|  
|<span data-ttu-id="cb0d4-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="cb0d4-106">Keywords</span></span>|<span data-ttu-id="cb0d4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="cb0d4-107">WFRuntime</span></span>|  
|<span data-ttu-id="cb0d4-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="cb0d4-108">Level</span></span>|<span data-ttu-id="cb0d4-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="cb0d4-109">Verbose</span></span>|  
|<span data-ttu-id="cb0d4-110">Canal</span><span class="sxs-lookup"><span data-stu-id="cb0d4-110">Channel</span></span>|<span data-ttu-id="cb0d4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cb0d4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cb0d4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb0d4-112">Description</span></span>  

 <span data-ttu-id="cb0d4-113">Indica que un CancelActivityWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="cb0d4-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cb0d4-114">Message</span><span class="sxs-lookup"><span data-stu-id="cb0d4-114">Message</span></span>  

 <span data-ttu-id="cb0d4-115">Iniciando la ejecución de un CancelActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="cb0d4-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cb0d4-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="cb0d4-116">Details</span></span>  
  
|<span data-ttu-id="cb0d4-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cb0d4-117">Data Item Name</span></span>|<span data-ttu-id="cb0d4-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cb0d4-118">Data Item Type</span></span>|<span data-ttu-id="cb0d4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb0d4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cb0d4-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="cb0d4-120">Activity</span></span>|<span data-ttu-id="cb0d4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb0d4-121">xs:string</span></span>|<span data-ttu-id="cb0d4-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="cb0d4-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="cb0d4-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cb0d4-123">DisplayName</span></span>|<span data-ttu-id="cb0d4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb0d4-124">xs:string</span></span>|<span data-ttu-id="cb0d4-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="cb0d4-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="cb0d4-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="cb0d4-126">InstanceId</span></span>|<span data-ttu-id="cb0d4-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb0d4-127">xs:string</span></span>|<span data-ttu-id="cb0d4-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="cb0d4-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="cb0d4-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cb0d4-129">AppDomain</span></span>|<span data-ttu-id="cb0d4-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="cb0d4-130">xs:string</span></span>|<span data-ttu-id="cb0d4-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cb0d4-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
