---
title: 1036 - RuntimeTransactionCompletionRequested
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 112063d5cd550f438541b2d775eaa49124d9cc02
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="f4571-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="f4571-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="f4571-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f4571-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4571-104">Id.</span><span class="sxs-lookup"><span data-stu-id="f4571-104">ID</span></span>|<span data-ttu-id="f4571-105">1036</span><span class="sxs-lookup"><span data-stu-id="f4571-105">1036</span></span>|  
|<span data-ttu-id="f4571-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="f4571-106">Keywords</span></span>|<span data-ttu-id="f4571-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f4571-107">WFRuntime</span></span>|  
|<span data-ttu-id="f4571-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="f4571-108">Level</span></span>|<span data-ttu-id="f4571-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="f4571-109">Verbose</span></span>|  
|<span data-ttu-id="f4571-110">Canal</span><span class="sxs-lookup"><span data-stu-id="f4571-110">Channel</span></span>|<span data-ttu-id="f4571-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="f4571-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f4571-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4571-112">Description</span></span>  
 <span data-ttu-id="f4571-113">Indica que una actividad ha programado la finalización de la transacción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f4571-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f4571-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="f4571-114">Message</span></span>  
 <span data-ttu-id="f4571-115">La actividad '%1', DisplayName: '%2', InstanceId: '%3' ha programado la finalización de la transacción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f4571-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f4571-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="f4571-116">Details</span></span>  
  
|<span data-ttu-id="f4571-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f4571-117">Data Item Name</span></span>|<span data-ttu-id="f4571-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="f4571-118">Data Item Type</span></span>|<span data-ttu-id="f4571-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4571-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f4571-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="f4571-120">Activity</span></span>|<span data-ttu-id="f4571-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4571-121">xs:string</span></span>|<span data-ttu-id="f4571-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="f4571-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f4571-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f4571-123">DisplayName</span></span>|<span data-ttu-id="f4571-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4571-124">xs:string</span></span>|<span data-ttu-id="f4571-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="f4571-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f4571-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f4571-126">InstanceId</span></span>|<span data-ttu-id="f4571-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4571-127">xs:string</span></span>|<span data-ttu-id="f4571-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="f4571-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f4571-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f4571-129">AppDomain</span></span>|<span data-ttu-id="f4571-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4571-130">xs:string</span></span>|<span data-ttu-id="f4571-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="f4571-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
