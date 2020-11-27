---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 7ba2ada1fbd5217592b4e4e3cffd813ffbe978ac
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275250"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="0472a-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="0472a-102">1026 - ScheduleTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="0472a-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0472a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0472a-104">ID</span><span class="sxs-lookup"><span data-stu-id="0472a-104">ID</span></span>|<span data-ttu-id="0472a-105">1026</span><span class="sxs-lookup"><span data-stu-id="0472a-105">1026</span></span>|  
|<span data-ttu-id="0472a-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0472a-106">Keywords</span></span>|<span data-ttu-id="0472a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0472a-107">WFRuntime</span></span>|  
|<span data-ttu-id="0472a-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0472a-108">Level</span></span>|<span data-ttu-id="0472a-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="0472a-109">Verbose</span></span>|  
|<span data-ttu-id="0472a-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0472a-110">Channel</span></span>|<span data-ttu-id="0472a-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0472a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0472a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0472a-112">Description</span></span>  

 <span data-ttu-id="0472a-113">Indica que se ha programado una TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="0472a-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0472a-114">Message</span><span class="sxs-lookup"><span data-stu-id="0472a-114">Message</span></span>  

 <span data-ttu-id="0472a-115">Un TransactionContextWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="0472a-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0472a-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="0472a-116">Details</span></span>  
  
|<span data-ttu-id="0472a-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0472a-117">Data Item Name</span></span>|<span data-ttu-id="0472a-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0472a-118">Data Item Type</span></span>|<span data-ttu-id="0472a-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="0472a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0472a-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="0472a-120">Activity</span></span>|<span data-ttu-id="0472a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0472a-121">xs:string</span></span>|<span data-ttu-id="0472a-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0472a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0472a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0472a-123">DisplayName</span></span>|<span data-ttu-id="0472a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0472a-124">xs:string</span></span>|<span data-ttu-id="0472a-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0472a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0472a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0472a-126">InstanceId</span></span>|<span data-ttu-id="0472a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0472a-127">xs:string</span></span>|<span data-ttu-id="0472a-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0472a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0472a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0472a-129">AppDomain</span></span>|<span data-ttu-id="0472a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0472a-130">xs:string</span></span>|<span data-ttu-id="0472a-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0472a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
