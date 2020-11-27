---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 6aed9773aa45251075520a0f955e9d71234f1357
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275624"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="ead85-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="ead85-102">1017 - ScheduleCancelActivityWorkItem</span></span>

## <a name="properties"></a><span data-ttu-id="ead85-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ead85-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ead85-104">ID</span><span class="sxs-lookup"><span data-stu-id="ead85-104">ID</span></span>|<span data-ttu-id="ead85-105">1017</span><span class="sxs-lookup"><span data-stu-id="ead85-105">1017</span></span>|  
|<span data-ttu-id="ead85-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ead85-106">Keywords</span></span>|<span data-ttu-id="ead85-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ead85-107">WFRuntime</span></span>|  
|<span data-ttu-id="ead85-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ead85-108">Level</span></span>|<span data-ttu-id="ead85-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="ead85-109">Verbose</span></span>|  
|<span data-ttu-id="ead85-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ead85-110">Channel</span></span>|<span data-ttu-id="ead85-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ead85-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ead85-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ead85-112">Description</span></span>  

 <span data-ttu-id="ead85-113">Indica que se ha programado un CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="ead85-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ead85-114">Message</span><span class="sxs-lookup"><span data-stu-id="ead85-114">Message</span></span>  

 <span data-ttu-id="ead85-115">Un CancelActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="ead85-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ead85-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="ead85-116">Details</span></span>  
  
|<span data-ttu-id="ead85-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ead85-117">Data Item Name</span></span>|<span data-ttu-id="ead85-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ead85-118">Data Item Type</span></span>|<span data-ttu-id="ead85-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ead85-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ead85-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="ead85-120">Activity</span></span>|<span data-ttu-id="ead85-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ead85-121">xs:string</span></span>|<span data-ttu-id="ead85-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ead85-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ead85-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ead85-123">DisplayName</span></span>|<span data-ttu-id="ead85-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ead85-124">xs:string</span></span>|<span data-ttu-id="ead85-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ead85-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ead85-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ead85-126">InstanceId</span></span>|<span data-ttu-id="ead85-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ead85-127">xs:string</span></span>|<span data-ttu-id="ead85-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ead85-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ead85-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ead85-129">AppDomain</span></span>|<span data-ttu-id="ead85-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ead85-130">xs:string</span></span>|<span data-ttu-id="ead85-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ead85-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
