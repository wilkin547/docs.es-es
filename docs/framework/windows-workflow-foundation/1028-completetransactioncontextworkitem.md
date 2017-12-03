---
title: 1028 - CompleteTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8770c0d41537ec1ce48dd0038aecc220f0e6ab32
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="4e357-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="4e357-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="4e357-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4e357-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4e357-104">Id.</span><span class="sxs-lookup"><span data-stu-id="4e357-104">ID</span></span>|<span data-ttu-id="4e357-105">1028</span><span class="sxs-lookup"><span data-stu-id="4e357-105">1028</span></span>|  
|<span data-ttu-id="4e357-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4e357-106">Keywords</span></span>|<span data-ttu-id="4e357-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4e357-107">WFRuntime</span></span>|  
|<span data-ttu-id="4e357-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="4e357-108">Level</span></span>|<span data-ttu-id="4e357-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="4e357-109">Verbose</span></span>|  
|<span data-ttu-id="4e357-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4e357-110">Channel</span></span>|<span data-ttu-id="4e357-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4e357-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4e357-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e357-112">Description</span></span>  
 <span data-ttu-id="4e357-113">Indica que se ha completado un TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="4e357-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4e357-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="4e357-114">Message</span></span>  
 <span data-ttu-id="4e357-115">Un TransactionContextWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="4e357-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4e357-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="4e357-116">Details</span></span>  
  
|<span data-ttu-id="4e357-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4e357-117">Data Item Name</span></span>|<span data-ttu-id="4e357-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4e357-118">Data Item Type</span></span>|<span data-ttu-id="4e357-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e357-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4e357-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="4e357-120">Activity</span></span>|<span data-ttu-id="4e357-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e357-121">xs:string</span></span>|<span data-ttu-id="4e357-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4e357-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="4e357-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4e357-123">DisplayName</span></span>|<span data-ttu-id="4e357-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e357-124">xs:string</span></span>|<span data-ttu-id="4e357-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4e357-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="4e357-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4e357-126">InstanceId</span></span>|<span data-ttu-id="4e357-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e357-127">xs:string</span></span>|<span data-ttu-id="4e357-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4e357-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4e357-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4e357-129">AppDomain</span></span>|<span data-ttu-id="4e357-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4e357-130">xs:string</span></span>|<span data-ttu-id="4e357-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4e357-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
