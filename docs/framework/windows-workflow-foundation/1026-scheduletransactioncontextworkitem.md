---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 6d0b43208f86c52e8863d4415a64466b0531832c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510288"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="defb6-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="defb6-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="defb6-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="defb6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="defb6-104">Id.</span><span class="sxs-lookup"><span data-stu-id="defb6-104">ID</span></span>|<span data-ttu-id="defb6-105">1026</span><span class="sxs-lookup"><span data-stu-id="defb6-105">1026</span></span>|  
|<span data-ttu-id="defb6-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="defb6-106">Keywords</span></span>|<span data-ttu-id="defb6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="defb6-107">WFRuntime</span></span>|  
|<span data-ttu-id="defb6-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="defb6-108">Level</span></span>|<span data-ttu-id="defb6-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="defb6-109">Verbose</span></span>|  
|<span data-ttu-id="defb6-110">Canal</span><span class="sxs-lookup"><span data-stu-id="defb6-110">Channel</span></span>|<span data-ttu-id="defb6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="defb6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="defb6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="defb6-112">Description</span></span>  
 <span data-ttu-id="defb6-113">Indica que se ha programado una TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="defb6-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="defb6-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="defb6-114">Message</span></span>  
 <span data-ttu-id="defb6-115">Un TransactionContextWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="defb6-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="defb6-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="defb6-116">Details</span></span>  
  
|<span data-ttu-id="defb6-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="defb6-117">Data Item Name</span></span>|<span data-ttu-id="defb6-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="defb6-118">Data Item Type</span></span>|<span data-ttu-id="defb6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="defb6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="defb6-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="defb6-120">Activity</span></span>|<span data-ttu-id="defb6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="defb6-121">xs:string</span></span>|<span data-ttu-id="defb6-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="defb6-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="defb6-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="defb6-123">DisplayName</span></span>|<span data-ttu-id="defb6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="defb6-124">xs:string</span></span>|<span data-ttu-id="defb6-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="defb6-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="defb6-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="defb6-126">InstanceId</span></span>|<span data-ttu-id="defb6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="defb6-127">xs:string</span></span>|<span data-ttu-id="defb6-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="defb6-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="defb6-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="defb6-129">AppDomain</span></span>|<span data-ttu-id="defb6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="defb6-130">xs:string</span></span>|<span data-ttu-id="defb6-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="defb6-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
