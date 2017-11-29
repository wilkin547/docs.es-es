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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77ef22bd29c167b5be26ceb5360397d38c547c22
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="8c07b-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="8c07b-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8c07b-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8c07b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8c07b-104">Id.</span><span class="sxs-lookup"><span data-stu-id="8c07b-104">ID</span></span>|<span data-ttu-id="8c07b-105">1028</span><span class="sxs-lookup"><span data-stu-id="8c07b-105">1028</span></span>|  
|<span data-ttu-id="8c07b-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8c07b-106">Keywords</span></span>|<span data-ttu-id="8c07b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8c07b-107">WFRuntime</span></span>|  
|<span data-ttu-id="8c07b-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="8c07b-108">Level</span></span>|<span data-ttu-id="8c07b-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="8c07b-109">Verbose</span></span>|  
|<span data-ttu-id="8c07b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8c07b-110">Channel</span></span>|<span data-ttu-id="8c07b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8c07b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8c07b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c07b-112">Description</span></span>  
 <span data-ttu-id="8c07b-113">Indica que se ha completado un TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="8c07b-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8c07b-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="8c07b-114">Message</span></span>  
 <span data-ttu-id="8c07b-115">Un TransactionContextWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="8c07b-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8c07b-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="8c07b-116">Details</span></span>  
  
|<span data-ttu-id="8c07b-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8c07b-117">Data Item Name</span></span>|<span data-ttu-id="8c07b-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8c07b-118">Data Item Type</span></span>|<span data-ttu-id="8c07b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c07b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8c07b-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="8c07b-120">Activity</span></span>|<span data-ttu-id="8c07b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8c07b-121">xs:string</span></span>|<span data-ttu-id="8c07b-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8c07b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8c07b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8c07b-123">DisplayName</span></span>|<span data-ttu-id="8c07b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8c07b-124">xs:string</span></span>|<span data-ttu-id="8c07b-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8c07b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8c07b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8c07b-126">InstanceId</span></span>|<span data-ttu-id="8c07b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8c07b-127">xs:string</span></span>|<span data-ttu-id="8c07b-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8c07b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8c07b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8c07b-129">AppDomain</span></span>|<span data-ttu-id="8c07b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8c07b-130">xs:string</span></span>|<span data-ttu-id="8c07b-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8c07b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
