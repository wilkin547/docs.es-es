---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 186b012cdd554ec7dd0d195b460619cca04eddcb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924493"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="3d954-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="3d954-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3d954-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3d954-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3d954-104">ID</span><span class="sxs-lookup"><span data-stu-id="3d954-104">ID</span></span>|<span data-ttu-id="3d954-105">1017</span><span class="sxs-lookup"><span data-stu-id="3d954-105">1017</span></span>|  
|<span data-ttu-id="3d954-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3d954-106">Keywords</span></span>|<span data-ttu-id="3d954-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3d954-107">WFRuntime</span></span>|  
|<span data-ttu-id="3d954-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3d954-108">Level</span></span>|<span data-ttu-id="3d954-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="3d954-109">Verbose</span></span>|  
|<span data-ttu-id="3d954-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3d954-110">Channel</span></span>|<span data-ttu-id="3d954-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3d954-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3d954-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d954-112">Description</span></span>  
 <span data-ttu-id="3d954-113">Indica que se ha programado un CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="3d954-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3d954-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="3d954-114">Message</span></span>  
 <span data-ttu-id="3d954-115">Un CancelActivityWorkItem se ha programado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3d954-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3d954-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="3d954-116">Details</span></span>  
  
|<span data-ttu-id="3d954-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3d954-117">Data Item Name</span></span>|<span data-ttu-id="3d954-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3d954-118">Data Item Type</span></span>|<span data-ttu-id="3d954-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d954-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3d954-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="3d954-120">Activity</span></span>|<span data-ttu-id="3d954-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3d954-121">xs:string</span></span>|<span data-ttu-id="3d954-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3d954-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3d954-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3d954-123">DisplayName</span></span>|<span data-ttu-id="3d954-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3d954-124">xs:string</span></span>|<span data-ttu-id="3d954-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3d954-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3d954-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3d954-126">InstanceId</span></span>|<span data-ttu-id="3d954-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3d954-127">xs:string</span></span>|<span data-ttu-id="3d954-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3d954-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3d954-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3d954-129">AppDomain</span></span>|<span data-ttu-id="3d954-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3d954-130">xs:string</span></span>|<span data-ttu-id="3d954-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3d954-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
