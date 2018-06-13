---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510398"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="8a56f-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="8a56f-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="8a56f-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8a56f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a56f-104">Id.</span><span class="sxs-lookup"><span data-stu-id="8a56f-104">ID</span></span>|<span data-ttu-id="8a56f-105">1036</span><span class="sxs-lookup"><span data-stu-id="8a56f-105">1036</span></span>|  
|<span data-ttu-id="8a56f-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8a56f-106">Keywords</span></span>|<span data-ttu-id="8a56f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8a56f-107">WFRuntime</span></span>|  
|<span data-ttu-id="8a56f-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="8a56f-108">Level</span></span>|<span data-ttu-id="8a56f-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="8a56f-109">Verbose</span></span>|  
|<span data-ttu-id="8a56f-110">Canal</span><span class="sxs-lookup"><span data-stu-id="8a56f-110">Channel</span></span>|<span data-ttu-id="8a56f-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8a56f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8a56f-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a56f-112">Description</span></span>  
 <span data-ttu-id="8a56f-113">Indica que una actividad ha programado la finalización de la transacción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8a56f-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8a56f-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="8a56f-114">Message</span></span>  
 <span data-ttu-id="8a56f-115">La actividad '%1', DisplayName: '%2', InstanceId: '%3' ha programado la finalización de la transacción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8a56f-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8a56f-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="8a56f-116">Details</span></span>  
  
|<span data-ttu-id="8a56f-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8a56f-117">Data Item Name</span></span>|<span data-ttu-id="8a56f-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8a56f-118">Data Item Type</span></span>|<span data-ttu-id="8a56f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a56f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8a56f-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="8a56f-120">Activity</span></span>|<span data-ttu-id="8a56f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a56f-121">xs:string</span></span>|<span data-ttu-id="8a56f-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8a56f-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8a56f-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8a56f-123">DisplayName</span></span>|<span data-ttu-id="8a56f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a56f-124">xs:string</span></span>|<span data-ttu-id="8a56f-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8a56f-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8a56f-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8a56f-126">InstanceId</span></span>|<span data-ttu-id="8a56f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a56f-127">xs:string</span></span>|<span data-ttu-id="8a56f-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8a56f-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8a56f-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8a56f-129">AppDomain</span></span>|<span data-ttu-id="8a56f-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a56f-130">xs:string</span></span>|<span data-ttu-id="8a56f-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8a56f-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
