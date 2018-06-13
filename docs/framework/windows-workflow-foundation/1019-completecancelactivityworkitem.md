---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 28d19742055c51ca94c36ffddf15dced7dfc14cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510213"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="660ec-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="660ec-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="660ec-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="660ec-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="660ec-104">Id.</span><span class="sxs-lookup"><span data-stu-id="660ec-104">ID</span></span>|<span data-ttu-id="660ec-105">1019</span><span class="sxs-lookup"><span data-stu-id="660ec-105">1019</span></span>|  
|<span data-ttu-id="660ec-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="660ec-106">Keywords</span></span>|<span data-ttu-id="660ec-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="660ec-107">WFRuntime</span></span>|  
|<span data-ttu-id="660ec-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="660ec-108">Level</span></span>|<span data-ttu-id="660ec-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="660ec-109">Verbose</span></span>|  
|<span data-ttu-id="660ec-110">Canal</span><span class="sxs-lookup"><span data-stu-id="660ec-110">Channel</span></span>|<span data-ttu-id="660ec-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="660ec-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="660ec-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="660ec-112">Description</span></span>  
 <span data-ttu-id="660ec-113">Indica que se ha completado un CancelActivityWorkItem.</span><span class="sxs-lookup"><span data-stu-id="660ec-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="660ec-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="660ec-114">Message</span></span>  
 <span data-ttu-id="660ec-115">Un CancelActivityWorkItem se ha completado para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="660ec-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="660ec-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="660ec-116">Details</span></span>  
  
|<span data-ttu-id="660ec-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="660ec-117">Data Item Name</span></span>|<span data-ttu-id="660ec-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="660ec-118">Data Item Type</span></span>|<span data-ttu-id="660ec-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="660ec-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="660ec-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="660ec-120">Activity</span></span>|<span data-ttu-id="660ec-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="660ec-121">xs:string</span></span>|<span data-ttu-id="660ec-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="660ec-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="660ec-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="660ec-123">DisplayName</span></span>|<span data-ttu-id="660ec-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="660ec-124">xs:string</span></span>|<span data-ttu-id="660ec-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="660ec-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="660ec-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="660ec-126">InstanceId</span></span>|<span data-ttu-id="660ec-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="660ec-127">xs:string</span></span>|<span data-ttu-id="660ec-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="660ec-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="660ec-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="660ec-129">AppDomain</span></span>|<span data-ttu-id="660ec-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="660ec-130">xs:string</span></span>|<span data-ttu-id="660ec-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="660ec-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
