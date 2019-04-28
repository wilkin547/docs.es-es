---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924844"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="494ca-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="494ca-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="494ca-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="494ca-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="494ca-104">ID</span><span class="sxs-lookup"><span data-stu-id="494ca-104">ID</span></span>|<span data-ttu-id="494ca-105">1036</span><span class="sxs-lookup"><span data-stu-id="494ca-105">1036</span></span>|  
|<span data-ttu-id="494ca-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="494ca-106">Keywords</span></span>|<span data-ttu-id="494ca-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="494ca-107">WFRuntime</span></span>|  
|<span data-ttu-id="494ca-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="494ca-108">Level</span></span>|<span data-ttu-id="494ca-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="494ca-109">Verbose</span></span>|  
|<span data-ttu-id="494ca-110">Canal</span><span class="sxs-lookup"><span data-stu-id="494ca-110">Channel</span></span>|<span data-ttu-id="494ca-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="494ca-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="494ca-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="494ca-112">Description</span></span>  
 <span data-ttu-id="494ca-113">Indica que una actividad ha programado la finalización de la transacción en runtime.</span><span class="sxs-lookup"><span data-stu-id="494ca-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="494ca-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="494ca-114">Message</span></span>  
 <span data-ttu-id="494ca-115">La actividad '%1', DisplayName: '%2', InstanceId: '%3' ha programado la finalización de la transacción en runtime.</span><span class="sxs-lookup"><span data-stu-id="494ca-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="494ca-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="494ca-116">Details</span></span>  
  
|<span data-ttu-id="494ca-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="494ca-117">Data Item Name</span></span>|<span data-ttu-id="494ca-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="494ca-118">Data Item Type</span></span>|<span data-ttu-id="494ca-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="494ca-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="494ca-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="494ca-120">Activity</span></span>|<span data-ttu-id="494ca-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="494ca-121">xs:string</span></span>|<span data-ttu-id="494ca-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="494ca-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="494ca-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="494ca-123">DisplayName</span></span>|<span data-ttu-id="494ca-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="494ca-124">xs:string</span></span>|<span data-ttu-id="494ca-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="494ca-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="494ca-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="494ca-126">InstanceId</span></span>|<span data-ttu-id="494ca-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="494ca-127">xs:string</span></span>|<span data-ttu-id="494ca-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="494ca-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="494ca-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="494ca-129">AppDomain</span></span>|<span data-ttu-id="494ca-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="494ca-130">xs:string</span></span>|<span data-ttu-id="494ca-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="494ca-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
