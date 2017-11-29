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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4f497d777221a98b38603b2ced29342651b1020b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="7b236-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="7b236-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="7b236-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7b236-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7b236-104">Id.</span><span class="sxs-lookup"><span data-stu-id="7b236-104">ID</span></span>|<span data-ttu-id="7b236-105">1036</span><span class="sxs-lookup"><span data-stu-id="7b236-105">1036</span></span>|  
|<span data-ttu-id="7b236-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="7b236-106">Keywords</span></span>|<span data-ttu-id="7b236-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7b236-107">WFRuntime</span></span>|  
|<span data-ttu-id="7b236-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="7b236-108">Level</span></span>|<span data-ttu-id="7b236-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="7b236-109">Verbose</span></span>|  
|<span data-ttu-id="7b236-110">Canal</span><span class="sxs-lookup"><span data-stu-id="7b236-110">Channel</span></span>|<span data-ttu-id="7b236-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="7b236-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7b236-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b236-112">Description</span></span>  
 <span data-ttu-id="7b236-113">Indica que una actividad ha programado la finalización de la transacción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7b236-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7b236-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="7b236-114">Message</span></span>  
 <span data-ttu-id="7b236-115">La actividad '%1', DisplayName: '%2', InstanceId: '%3' ha programado la finalización de la transacción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7b236-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7b236-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="7b236-116">Details</span></span>  
  
|<span data-ttu-id="7b236-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7b236-117">Data Item Name</span></span>|<span data-ttu-id="7b236-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7b236-118">Data Item Type</span></span>|<span data-ttu-id="7b236-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b236-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7b236-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="7b236-120">Activity</span></span>|<span data-ttu-id="7b236-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7b236-121">xs:string</span></span>|<span data-ttu-id="7b236-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7b236-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="7b236-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7b236-123">DisplayName</span></span>|<span data-ttu-id="7b236-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7b236-124">xs:string</span></span>|<span data-ttu-id="7b236-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7b236-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="7b236-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="7b236-126">InstanceId</span></span>|<span data-ttu-id="7b236-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7b236-127">xs:string</span></span>|<span data-ttu-id="7b236-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7b236-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="7b236-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7b236-129">AppDomain</span></span>|<span data-ttu-id="7b236-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="7b236-130">xs:string</span></span>|<span data-ttu-id="7b236-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7b236-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
