---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 2fc509dac7e13f30f74c24d8b98cba55ed5f8e1d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275120"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="2a73e-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="2a73e-102">1028 - CompleteTransactionContextWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="2a73e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2a73e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a73e-104">ID</span><span class="sxs-lookup"><span data-stu-id="2a73e-104">ID</span></span>|<span data-ttu-id="2a73e-105">1028</span><span class="sxs-lookup"><span data-stu-id="2a73e-105">1028</span></span>|  
|<span data-ttu-id="2a73e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2a73e-106">Keywords</span></span>|<span data-ttu-id="2a73e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2a73e-107">WFRuntime</span></span>|  
|<span data-ttu-id="2a73e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="2a73e-108">Level</span></span>|<span data-ttu-id="2a73e-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="2a73e-109">Verbose</span></span>|  
|<span data-ttu-id="2a73e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="2a73e-110">Channel</span></span>|<span data-ttu-id="2a73e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2a73e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2a73e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a73e-112">Description</span></span>  

 <span data-ttu-id="2a73e-113">Indica que se ha completado un TransactionContextWorkItem.</span><span class="sxs-lookup"><span data-stu-id="2a73e-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2a73e-114">Message</span><span class="sxs-lookup"><span data-stu-id="2a73e-114">Message</span></span>  

 <span data-ttu-id="2a73e-115">Un TransactionContextWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="2a73e-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2a73e-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="2a73e-116">Details</span></span>  
  
|<span data-ttu-id="2a73e-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2a73e-117">Data Item Name</span></span>|<span data-ttu-id="2a73e-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2a73e-118">Data Item Type</span></span>|<span data-ttu-id="2a73e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a73e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2a73e-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="2a73e-120">Activity</span></span>|<span data-ttu-id="2a73e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a73e-121">xs:string</span></span>|<span data-ttu-id="2a73e-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="2a73e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="2a73e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2a73e-123">DisplayName</span></span>|<span data-ttu-id="2a73e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a73e-124">xs:string</span></span>|<span data-ttu-id="2a73e-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="2a73e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="2a73e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2a73e-126">InstanceId</span></span>|<span data-ttu-id="2a73e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a73e-127">xs:string</span></span>|<span data-ttu-id="2a73e-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="2a73e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2a73e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2a73e-129">AppDomain</span></span>|<span data-ttu-id="2a73e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a73e-130">xs:string</span></span>|<span data-ttu-id="2a73e-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2a73e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
