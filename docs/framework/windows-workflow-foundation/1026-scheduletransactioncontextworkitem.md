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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4d881f1be4e809cf45f100b966d6013ae8fa88f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="ef641-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="ef641-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ef641-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ef641-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef641-104">Id.</span><span class="sxs-lookup"><span data-stu-id="ef641-104">ID</span></span>|<span data-ttu-id="ef641-105">1026</span><span class="sxs-lookup"><span data-stu-id="ef641-105">1026</span></span>|  
|<span data-ttu-id="ef641-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ef641-106">Keywords</span></span>|<span data-ttu-id="ef641-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ef641-107">WFRuntime</span></span>|  
|<span data-ttu-id="ef641-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ef641-108">Level</span></span>|<span data-ttu-id="ef641-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="ef641-109">Verbose</span></span>|  
|<span data-ttu-id="ef641-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ef641-110">Channel</span></span>|<span data-ttu-id="ef641-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ef641-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ef641-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef641-112">Description</span></span>  
 <span data-ttu-id="ef641-113">Indica que se ha programado una TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="ef641-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ef641-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ef641-114">Message</span></span>  
 <span data-ttu-id="ef641-115">Un TransactionContextWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="ef641-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ef641-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="ef641-116">Details</span></span>  
  
|<span data-ttu-id="ef641-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ef641-117">Data Item Name</span></span>|<span data-ttu-id="ef641-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ef641-118">Data Item Type</span></span>|<span data-ttu-id="ef641-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef641-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ef641-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="ef641-120">Activity</span></span>|<span data-ttu-id="ef641-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef641-121">xs:string</span></span>|<span data-ttu-id="ef641-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ef641-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ef641-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ef641-123">DisplayName</span></span>|<span data-ttu-id="ef641-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef641-124">xs:string</span></span>|<span data-ttu-id="ef641-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ef641-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ef641-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ef641-126">InstanceId</span></span>|<span data-ttu-id="ef641-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef641-127">xs:string</span></span>|<span data-ttu-id="ef641-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ef641-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ef641-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ef641-129">AppDomain</span></span>|<span data-ttu-id="ef641-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef641-130">xs:string</span></span>|<span data-ttu-id="ef641-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ef641-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
