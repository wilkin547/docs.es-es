---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 186b012cdd554ec7dd0d195b460619cca04eddcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510177"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="0ee28-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="0ee28-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0ee28-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0ee28-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ee28-104">Id.</span><span class="sxs-lookup"><span data-stu-id="0ee28-104">ID</span></span>|<span data-ttu-id="0ee28-105">1017</span><span class="sxs-lookup"><span data-stu-id="0ee28-105">1017</span></span>|  
|<span data-ttu-id="0ee28-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0ee28-106">Keywords</span></span>|<span data-ttu-id="0ee28-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0ee28-107">WFRuntime</span></span>|  
|<span data-ttu-id="0ee28-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0ee28-108">Level</span></span>|<span data-ttu-id="0ee28-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="0ee28-109">Verbose</span></span>|  
|<span data-ttu-id="0ee28-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0ee28-110">Channel</span></span>|<span data-ttu-id="0ee28-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0ee28-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0ee28-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ee28-112">Description</span></span>  
 <span data-ttu-id="0ee28-113">Indica que se ha programado un CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="0ee28-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0ee28-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0ee28-114">Message</span></span>  
 <span data-ttu-id="0ee28-115">Un CancelActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="0ee28-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0ee28-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="0ee28-116">Details</span></span>  
  
|<span data-ttu-id="0ee28-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0ee28-117">Data Item Name</span></span>|<span data-ttu-id="0ee28-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0ee28-118">Data Item Type</span></span>|<span data-ttu-id="0ee28-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ee28-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0ee28-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="0ee28-120">Activity</span></span>|<span data-ttu-id="0ee28-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ee28-121">xs:string</span></span>|<span data-ttu-id="0ee28-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0ee28-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0ee28-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0ee28-123">DisplayName</span></span>|<span data-ttu-id="0ee28-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ee28-124">xs:string</span></span>|<span data-ttu-id="0ee28-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0ee28-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0ee28-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0ee28-126">InstanceId</span></span>|<span data-ttu-id="0ee28-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ee28-127">xs:string</span></span>|<span data-ttu-id="0ee28-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0ee28-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0ee28-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0ee28-129">AppDomain</span></span>|<span data-ttu-id="0ee28-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0ee28-130">xs:string</span></span>|<span data-ttu-id="0ee28-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0ee28-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
