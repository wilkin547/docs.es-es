---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: b9cfceb12d56f93c0f9726849e34f4333f1399ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239645"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="4ef82-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="4ef82-102">1012 - StartExecuteActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="4ef82-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4ef82-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ef82-104">ID</span><span class="sxs-lookup"><span data-stu-id="4ef82-104">ID</span></span>|<span data-ttu-id="4ef82-105">1012</span><span class="sxs-lookup"><span data-stu-id="4ef82-105">1012</span></span>|  
|<span data-ttu-id="4ef82-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4ef82-106">Keywords</span></span>|<span data-ttu-id="4ef82-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4ef82-107">WFRuntime</span></span>|  
|<span data-ttu-id="4ef82-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="4ef82-108">Level</span></span>|<span data-ttu-id="4ef82-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="4ef82-109">Verbose</span></span>|  
|<span data-ttu-id="4ef82-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4ef82-110">Channel</span></span>|<span data-ttu-id="4ef82-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4ef82-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4ef82-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ef82-112">Description</span></span>  

 <span data-ttu-id="4ef82-113">Indica que un ExecuteActivityWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="4ef82-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4ef82-114">Message</span><span class="sxs-lookup"><span data-stu-id="4ef82-114">Message</span></span>  

 <span data-ttu-id="4ef82-115">Iniciando la ejecución de un ExecuteActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="4ef82-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4ef82-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="4ef82-116">Details</span></span>  
  
|<span data-ttu-id="4ef82-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4ef82-117">Data Item Name</span></span>|<span data-ttu-id="4ef82-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4ef82-118">Data Item Type</span></span>|<span data-ttu-id="4ef82-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ef82-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4ef82-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="4ef82-120">Activity</span></span>|<span data-ttu-id="4ef82-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ef82-121">xs:string</span></span>|<span data-ttu-id="4ef82-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4ef82-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="4ef82-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4ef82-123">DisplayName</span></span>|<span data-ttu-id="4ef82-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ef82-124">xs:string</span></span>|<span data-ttu-id="4ef82-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4ef82-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="4ef82-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4ef82-126">InstanceId</span></span>|<span data-ttu-id="4ef82-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ef82-127">xs:string</span></span>|<span data-ttu-id="4ef82-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4ef82-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4ef82-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4ef82-129">AppDomain</span></span>|<span data-ttu-id="4ef82-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ef82-130">xs:string</span></span>|<span data-ttu-id="4ef82-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4ef82-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
