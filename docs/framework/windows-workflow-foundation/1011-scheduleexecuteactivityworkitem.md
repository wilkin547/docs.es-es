---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 299d09b7c4db94a2e27378ba0cc3dfeb03734ab4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982259"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="9676b-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="9676b-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="9676b-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9676b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9676b-104">ID</span><span class="sxs-lookup"><span data-stu-id="9676b-104">ID</span></span>|<span data-ttu-id="9676b-105">1011</span><span class="sxs-lookup"><span data-stu-id="9676b-105">1011</span></span>|  
|<span data-ttu-id="9676b-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9676b-106">Keywords</span></span>|<span data-ttu-id="9676b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9676b-107">WFRuntime</span></span>|  
|<span data-ttu-id="9676b-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="9676b-108">Level</span></span>|<span data-ttu-id="9676b-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="9676b-109">Verbose</span></span>|  
|<span data-ttu-id="9676b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="9676b-110">Channel</span></span>|<span data-ttu-id="9676b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="9676b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9676b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9676b-112">Description</span></span>  
 <span data-ttu-id="9676b-113">Indica que se ha programado un ExecuteActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="9676b-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9676b-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="9676b-114">Message</span></span>  
 <span data-ttu-id="9676b-115">Un ExecuteActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="9676b-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9676b-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="9676b-116">Details</span></span>  
  
|<span data-ttu-id="9676b-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9676b-117">Data Item Name</span></span>|<span data-ttu-id="9676b-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9676b-118">Data Item Type</span></span>|<span data-ttu-id="9676b-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9676b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9676b-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="9676b-120">Activity</span></span>|<span data-ttu-id="9676b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9676b-121">xs:string</span></span>|<span data-ttu-id="9676b-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="9676b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="9676b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="9676b-123">DisplayName</span></span>|<span data-ttu-id="9676b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9676b-124">xs:string</span></span>|<span data-ttu-id="9676b-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="9676b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="9676b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="9676b-126">InstanceId</span></span>|<span data-ttu-id="9676b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9676b-127">xs:string</span></span>|<span data-ttu-id="9676b-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="9676b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="9676b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9676b-129">AppDomain</span></span>|<span data-ttu-id="9676b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="9676b-130">xs:string</span></span>|<span data-ttu-id="9676b-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9676b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
