---
title: 1027 - StartTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baa644cb7693b8608f119cf211b3b08ab4b1a2b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="97a21-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="97a21-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="97a21-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="97a21-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="97a21-104">Id.</span><span class="sxs-lookup"><span data-stu-id="97a21-104">ID</span></span>|<span data-ttu-id="97a21-105">1027</span><span class="sxs-lookup"><span data-stu-id="97a21-105">1027</span></span>|  
|<span data-ttu-id="97a21-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="97a21-106">Keywords</span></span>|<span data-ttu-id="97a21-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="97a21-107">WFRuntime</span></span>|  
|<span data-ttu-id="97a21-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="97a21-108">Level</span></span>|<span data-ttu-id="97a21-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="97a21-109">Verbose</span></span>|  
|<span data-ttu-id="97a21-110">Canal</span><span class="sxs-lookup"><span data-stu-id="97a21-110">Channel</span></span>|<span data-ttu-id="97a21-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="97a21-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="97a21-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="97a21-112">Description</span></span>  
 <span data-ttu-id="97a21-113">Indica que un TransactionContextWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="97a21-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="97a21-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="97a21-114">Message</span></span>  
 <span data-ttu-id="97a21-115">Iniciando la ejecución de un TransactionContextWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="97a21-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="97a21-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="97a21-116">Details</span></span>  
  
|<span data-ttu-id="97a21-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="97a21-117">Data Item Name</span></span>|<span data-ttu-id="97a21-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="97a21-118">Data Item Type</span></span>|<span data-ttu-id="97a21-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="97a21-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="97a21-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="97a21-120">Activity</span></span>|<span data-ttu-id="97a21-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="97a21-121">xs:string</span></span>|<span data-ttu-id="97a21-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="97a21-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="97a21-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="97a21-123">DisplayName</span></span>|<span data-ttu-id="97a21-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="97a21-124">xs:string</span></span>|<span data-ttu-id="97a21-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="97a21-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="97a21-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="97a21-126">InstanceId</span></span>|<span data-ttu-id="97a21-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="97a21-127">xs:string</span></span>|<span data-ttu-id="97a21-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="97a21-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="97a21-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="97a21-129">AppDomain</span></span>|<span data-ttu-id="97a21-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="97a21-130">xs:string</span></span>|<span data-ttu-id="97a21-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="97a21-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
