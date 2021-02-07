---
description: 'Más información acerca de: 1012-StartExecuteActivityWorkItem'
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: 3b57fc6d37a6708a4e22537de87a2566612088e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99714890"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="3898c-103">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="3898c-103">1012 - StartExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="3898c-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3898c-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3898c-105">Id.</span><span class="sxs-lookup"><span data-stu-id="3898c-105">ID</span></span>|<span data-ttu-id="3898c-106">1012</span><span class="sxs-lookup"><span data-stu-id="3898c-106">1012</span></span>|  
|<span data-ttu-id="3898c-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3898c-107">Keywords</span></span>|<span data-ttu-id="3898c-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3898c-108">WFRuntime</span></span>|  
|<span data-ttu-id="3898c-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="3898c-109">Level</span></span>|<span data-ttu-id="3898c-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="3898c-110">Verbose</span></span>|  
|<span data-ttu-id="3898c-111">Canal</span><span class="sxs-lookup"><span data-stu-id="3898c-111">Channel</span></span>|<span data-ttu-id="3898c-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3898c-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3898c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3898c-113">Description</span></span>  

 <span data-ttu-id="3898c-114">Indica que un ExecuteActivityWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="3898c-114">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3898c-115">Message</span><span class="sxs-lookup"><span data-stu-id="3898c-115">Message</span></span>  

 <span data-ttu-id="3898c-116">Iniciando la ejecución de un ExecuteActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3898c-116">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3898c-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="3898c-117">Details</span></span>  
  
|<span data-ttu-id="3898c-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3898c-118">Data Item Name</span></span>|<span data-ttu-id="3898c-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3898c-119">Data Item Type</span></span>|<span data-ttu-id="3898c-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="3898c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3898c-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="3898c-121">Activity</span></span>|<span data-ttu-id="3898c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3898c-122">xs:string</span></span>|<span data-ttu-id="3898c-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3898c-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="3898c-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3898c-124">DisplayName</span></span>|<span data-ttu-id="3898c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3898c-125">xs:string</span></span>|<span data-ttu-id="3898c-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3898c-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="3898c-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3898c-127">InstanceId</span></span>|<span data-ttu-id="3898c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3898c-128">xs:string</span></span>|<span data-ttu-id="3898c-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3898c-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3898c-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3898c-130">AppDomain</span></span>|<span data-ttu-id="3898c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="3898c-131">xs:string</span></span>|<span data-ttu-id="3898c-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3898c-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
