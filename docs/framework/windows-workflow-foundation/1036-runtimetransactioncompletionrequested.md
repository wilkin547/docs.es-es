---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 96ea253fd61652a3719eaf8b1a4d31aa88337eeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96294266"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="d4f73-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="d4f73-102">1036 - RuntimeTransactionCompletionRequested</span></span>

## <a name="properties"></a><span data-ttu-id="d4f73-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d4f73-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4f73-104">ID</span><span class="sxs-lookup"><span data-stu-id="d4f73-104">ID</span></span>|<span data-ttu-id="d4f73-105">1036</span><span class="sxs-lookup"><span data-stu-id="d4f73-105">1036</span></span>|  
|<span data-ttu-id="d4f73-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d4f73-106">Keywords</span></span>|<span data-ttu-id="d4f73-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d4f73-107">WFRuntime</span></span>|  
|<span data-ttu-id="d4f73-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d4f73-108">Level</span></span>|<span data-ttu-id="d4f73-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="d4f73-109">Verbose</span></span>|  
|<span data-ttu-id="d4f73-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d4f73-110">Channel</span></span>|<span data-ttu-id="d4f73-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d4f73-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d4f73-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4f73-112">Description</span></span>  

 <span data-ttu-id="d4f73-113">Indica que una actividad ha programado la finalización de la transacción en runtime.</span><span class="sxs-lookup"><span data-stu-id="d4f73-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d4f73-114">Message</span><span class="sxs-lookup"><span data-stu-id="d4f73-114">Message</span></span>  

 <span data-ttu-id="d4f73-115">La actividad '%1', DisplayName: '%2', InstanceId: '%3' ha programado la finalización de la transacción en runtime.</span><span class="sxs-lookup"><span data-stu-id="d4f73-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4f73-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="d4f73-116">Details</span></span>  
  
|<span data-ttu-id="d4f73-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d4f73-117">Data Item Name</span></span>|<span data-ttu-id="d4f73-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d4f73-118">Data Item Type</span></span>|<span data-ttu-id="d4f73-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d4f73-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d4f73-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="d4f73-120">Activity</span></span>|<span data-ttu-id="d4f73-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4f73-121">xs:string</span></span>|<span data-ttu-id="d4f73-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d4f73-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="d4f73-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d4f73-123">DisplayName</span></span>|<span data-ttu-id="d4f73-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4f73-124">xs:string</span></span>|<span data-ttu-id="d4f73-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d4f73-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="d4f73-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="d4f73-126">InstanceId</span></span>|<span data-ttu-id="d4f73-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4f73-127">xs:string</span></span>|<span data-ttu-id="d4f73-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d4f73-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="d4f73-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d4f73-129">AppDomain</span></span>|<span data-ttu-id="d4f73-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4f73-130">xs:string</span></span>|<span data-ttu-id="d4f73-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d4f73-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
