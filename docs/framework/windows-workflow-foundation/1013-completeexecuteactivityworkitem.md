---
title: 1013 - CompleteExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
ms.openlocfilehash: c1ff62bb4143bb798ea7adb7c3fee539ef68bc37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925195"
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="3cff1-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="3cff1-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3cff1-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3cff1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3cff1-104">ID</span><span class="sxs-lookup"><span data-stu-id="3cff1-104">ID</span></span>|<span data-ttu-id="3cff1-105">1013</span><span class="sxs-lookup"><span data-stu-id="3cff1-105">1013</span></span>|  
|<span data-ttu-id="3cff1-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3cff1-106">Keywords</span></span>|<span data-ttu-id="3cff1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3cff1-107">WFRuntime</span></span>|  
|<span data-ttu-id="3cff1-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3cff1-108">Level</span></span>|<span data-ttu-id="3cff1-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="3cff1-109">Verbose</span></span>|  
|<span data-ttu-id="3cff1-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3cff1-110">Channel</span></span>|<span data-ttu-id="3cff1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3cff1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3cff1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cff1-112">Description</span></span>  
 <span data-ttu-id="3cff1-113">Indica que un ExecuteActivityWorkItem se ha completado</span><span class="sxs-lookup"><span data-stu-id="3cff1-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="3cff1-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="3cff1-114">Message</span></span>  
 <span data-ttu-id="3cff1-115">Un ExecuteActivityWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3cff1-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3cff1-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="3cff1-116">Details</span></span>  
  
|<span data-ttu-id="3cff1-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3cff1-117">Data Item Name</span></span>|<span data-ttu-id="3cff1-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3cff1-118">Data Item Type</span></span>|<span data-ttu-id="3cff1-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3cff1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3cff1-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="3cff1-120">Activity</span></span>|<span data-ttu-id="3cff1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cff1-121">xs:string</span></span>|<span data-ttu-id="3cff1-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3cff1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3cff1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3cff1-123">DisplayName</span></span>|<span data-ttu-id="3cff1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cff1-124">xs:string</span></span>|<span data-ttu-id="3cff1-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3cff1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3cff1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3cff1-126">InstanceId</span></span>|<span data-ttu-id="3cff1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cff1-127">xs:string</span></span>|<span data-ttu-id="3cff1-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3cff1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3cff1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3cff1-129">AppDomain</span></span>|<span data-ttu-id="3cff1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3cff1-130">xs:string</span></span>|<span data-ttu-id="3cff1-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3cff1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
