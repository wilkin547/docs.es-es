---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: 654f961088c371ab53e4a81f40e3c63335efb1a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239593"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="84aa3-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="84aa3-102">1013 - CompleteExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="84aa3-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="84aa3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="84aa3-104">ID</span><span class="sxs-lookup"><span data-stu-id="84aa3-104">ID</span></span>|<span data-ttu-id="84aa3-105">1013</span><span class="sxs-lookup"><span data-stu-id="84aa3-105">1013</span></span>|  
|<span data-ttu-id="84aa3-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="84aa3-106">Keywords</span></span>|<span data-ttu-id="84aa3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="84aa3-107">WFRuntime</span></span>|  
|<span data-ttu-id="84aa3-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="84aa3-108">Level</span></span>|<span data-ttu-id="84aa3-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="84aa3-109">Verbose</span></span>|  
|<span data-ttu-id="84aa3-110">Canal</span><span class="sxs-lookup"><span data-stu-id="84aa3-110">Channel</span></span>|<span data-ttu-id="84aa3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="84aa3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="84aa3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="84aa3-112">Description</span></span>  

 <span data-ttu-id="84aa3-113">Indica que un ExecuteActivityWorkItem se ha completado</span><span class="sxs-lookup"><span data-stu-id="84aa3-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="84aa3-114">Message</span><span class="sxs-lookup"><span data-stu-id="84aa3-114">Message</span></span>  

 <span data-ttu-id="84aa3-115">Un ExecuteActivityWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="84aa3-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="84aa3-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="84aa3-116">Details</span></span>  
  
|<span data-ttu-id="84aa3-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="84aa3-117">Data Item Name</span></span>|<span data-ttu-id="84aa3-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="84aa3-118">Data Item Type</span></span>|<span data-ttu-id="84aa3-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="84aa3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="84aa3-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="84aa3-120">Activity</span></span>|<span data-ttu-id="84aa3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="84aa3-121">xs:string</span></span>|<span data-ttu-id="84aa3-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="84aa3-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="84aa3-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="84aa3-123">DisplayName</span></span>|<span data-ttu-id="84aa3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="84aa3-124">xs:string</span></span>|<span data-ttu-id="84aa3-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="84aa3-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="84aa3-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="84aa3-126">InstanceId</span></span>|<span data-ttu-id="84aa3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="84aa3-127">xs:string</span></span>|<span data-ttu-id="84aa3-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="84aa3-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="84aa3-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="84aa3-129">AppDomain</span></span>|<span data-ttu-id="84aa3-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="84aa3-130">xs:string</span></span>|<span data-ttu-id="84aa3-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="84aa3-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
