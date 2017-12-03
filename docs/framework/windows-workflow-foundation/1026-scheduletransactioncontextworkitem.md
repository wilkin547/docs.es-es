---
title: 1026 - ScheduleTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a5fb800718c1fd231d0cd02bf015333a44fa794f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="07daf-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="07daf-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="07daf-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="07daf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07daf-104">Id.</span><span class="sxs-lookup"><span data-stu-id="07daf-104">ID</span></span>|<span data-ttu-id="07daf-105">1026</span><span class="sxs-lookup"><span data-stu-id="07daf-105">1026</span></span>|  
|<span data-ttu-id="07daf-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="07daf-106">Keywords</span></span>|<span data-ttu-id="07daf-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="07daf-107">WFRuntime</span></span>|  
|<span data-ttu-id="07daf-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="07daf-108">Level</span></span>|<span data-ttu-id="07daf-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="07daf-109">Verbose</span></span>|  
|<span data-ttu-id="07daf-110">Canal</span><span class="sxs-lookup"><span data-stu-id="07daf-110">Channel</span></span>|<span data-ttu-id="07daf-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="07daf-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07daf-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="07daf-112">Description</span></span>  
 <span data-ttu-id="07daf-113">Indica que se ha programado una TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="07daf-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="07daf-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="07daf-114">Message</span></span>  
 <span data-ttu-id="07daf-115">Un TransactionContextWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="07daf-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="07daf-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="07daf-116">Details</span></span>  
  
|<span data-ttu-id="07daf-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="07daf-117">Data Item Name</span></span>|<span data-ttu-id="07daf-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="07daf-118">Data Item Type</span></span>|<span data-ttu-id="07daf-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="07daf-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="07daf-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="07daf-120">Activity</span></span>|<span data-ttu-id="07daf-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="07daf-121">xs:string</span></span>|<span data-ttu-id="07daf-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="07daf-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="07daf-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="07daf-123">DisplayName</span></span>|<span data-ttu-id="07daf-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="07daf-124">xs:string</span></span>|<span data-ttu-id="07daf-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="07daf-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="07daf-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="07daf-126">InstanceId</span></span>|<span data-ttu-id="07daf-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="07daf-127">xs:string</span></span>|<span data-ttu-id="07daf-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="07daf-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="07daf-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="07daf-129">AppDomain</span></span>|<span data-ttu-id="07daf-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="07daf-130">xs:string</span></span>|<span data-ttu-id="07daf-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="07daf-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
