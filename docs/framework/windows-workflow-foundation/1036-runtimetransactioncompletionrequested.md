---
description: 'Más información acerca de: 1036-RuntimeTransactionCompletionRequested'
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: e07400902d5c3e08732385ab30e1be0d72d3e997
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99667894"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="cf4a4-103">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="cf4a4-103">1036 - RuntimeTransactionCompletionRequested</span></span>

## <a name="properties"></a><span data-ttu-id="cf4a4-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cf4a4-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cf4a4-105">Id.</span><span class="sxs-lookup"><span data-stu-id="cf4a4-105">ID</span></span>|<span data-ttu-id="cf4a4-106">1036</span><span class="sxs-lookup"><span data-stu-id="cf4a4-106">1036</span></span>|  
|<span data-ttu-id="cf4a4-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="cf4a4-107">Keywords</span></span>|<span data-ttu-id="cf4a4-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="cf4a4-108">WFRuntime</span></span>|  
|<span data-ttu-id="cf4a4-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="cf4a4-109">Level</span></span>|<span data-ttu-id="cf4a4-110">Verbose</span><span class="sxs-lookup"><span data-stu-id="cf4a4-110">Verbose</span></span>|  
|<span data-ttu-id="cf4a4-111">Canal</span><span class="sxs-lookup"><span data-stu-id="cf4a4-111">Channel</span></span>|<span data-ttu-id="cf4a4-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cf4a4-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cf4a4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf4a4-113">Description</span></span>  

 <span data-ttu-id="cf4a4-114">Indica que una actividad ha programado la finalización de la transacción en runtime.</span><span class="sxs-lookup"><span data-stu-id="cf4a4-114">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cf4a4-115">Message</span><span class="sxs-lookup"><span data-stu-id="cf4a4-115">Message</span></span>  

 <span data-ttu-id="cf4a4-116">La actividad '%1', DisplayName: '%2', InstanceId: '%3' ha programado la finalización de la transacción en runtime.</span><span class="sxs-lookup"><span data-stu-id="cf4a4-116">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cf4a4-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="cf4a4-117">Details</span></span>  
  
|<span data-ttu-id="cf4a4-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cf4a4-118">Data Item Name</span></span>|<span data-ttu-id="cf4a4-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cf4a4-119">Data Item Type</span></span>|<span data-ttu-id="cf4a4-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf4a4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cf4a4-121">Actividad</span><span class="sxs-lookup"><span data-stu-id="cf4a4-121">Activity</span></span>|<span data-ttu-id="cf4a4-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="cf4a4-122">xs:string</span></span>|<span data-ttu-id="cf4a4-123">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="cf4a4-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="cf4a4-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cf4a4-124">DisplayName</span></span>|<span data-ttu-id="cf4a4-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="cf4a4-125">xs:string</span></span>|<span data-ttu-id="cf4a4-126">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="cf4a4-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="cf4a4-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="cf4a4-127">InstanceId</span></span>|<span data-ttu-id="cf4a4-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="cf4a4-128">xs:string</span></span>|<span data-ttu-id="cf4a4-129">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="cf4a4-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="cf4a4-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cf4a4-130">AppDomain</span></span>|<span data-ttu-id="cf4a4-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="cf4a4-131">xs:string</span></span>|<span data-ttu-id="cf4a4-132">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cf4a4-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
