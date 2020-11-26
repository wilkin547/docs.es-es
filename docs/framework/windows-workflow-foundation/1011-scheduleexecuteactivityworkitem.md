---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: dc209fc41dc6b076dfb897880f753be51f7fb0ce
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239697"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="892e0-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="892e0-102">1011 - ScheduleExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="892e0-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="892e0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="892e0-104">ID</span><span class="sxs-lookup"><span data-stu-id="892e0-104">ID</span></span>|<span data-ttu-id="892e0-105">1011</span><span class="sxs-lookup"><span data-stu-id="892e0-105">1011</span></span>|  
|<span data-ttu-id="892e0-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="892e0-106">Keywords</span></span>|<span data-ttu-id="892e0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="892e0-107">WFRuntime</span></span>|  
|<span data-ttu-id="892e0-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="892e0-108">Level</span></span>|<span data-ttu-id="892e0-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="892e0-109">Verbose</span></span>|  
|<span data-ttu-id="892e0-110">Canal</span><span class="sxs-lookup"><span data-stu-id="892e0-110">Channel</span></span>|<span data-ttu-id="892e0-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="892e0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="892e0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="892e0-112">Description</span></span>  

 <span data-ttu-id="892e0-113">Indica que se ha programado un ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="892e0-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="892e0-114">Message</span><span class="sxs-lookup"><span data-stu-id="892e0-114">Message</span></span>  

 <span data-ttu-id="892e0-115">Un ExecuteActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="892e0-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="892e0-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="892e0-116">Details</span></span>  
  
|<span data-ttu-id="892e0-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="892e0-117">Data Item Name</span></span>|<span data-ttu-id="892e0-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="892e0-118">Data Item Type</span></span>|<span data-ttu-id="892e0-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="892e0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="892e0-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="892e0-120">Activity</span></span>|<span data-ttu-id="892e0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="892e0-121">xs:string</span></span>|<span data-ttu-id="892e0-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="892e0-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="892e0-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="892e0-123">DisplayName</span></span>|<span data-ttu-id="892e0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="892e0-124">xs:string</span></span>|<span data-ttu-id="892e0-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="892e0-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="892e0-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="892e0-126">InstanceId</span></span>|<span data-ttu-id="892e0-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="892e0-127">xs:string</span></span>|<span data-ttu-id="892e0-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="892e0-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="892e0-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="892e0-129">AppDomain</span></span>|<span data-ttu-id="892e0-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="892e0-130">xs:string</span></span>|<span data-ttu-id="892e0-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="892e0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
