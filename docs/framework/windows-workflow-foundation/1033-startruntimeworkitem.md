---
title: 1033 - StartRuntimeWorkItem
ms.date: 03/30/2017
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
ms.openlocfilehash: c7192ed7c5fb43fe6f65b47b8cebde3cf4aed32c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924246"
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="ee0e7-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="ee0e7-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ee0e7-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ee0e7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ee0e7-104">ID</span><span class="sxs-lookup"><span data-stu-id="ee0e7-104">ID</span></span>|<span data-ttu-id="ee0e7-105">3082</span><span class="sxs-lookup"><span data-stu-id="ee0e7-105">1033</span></span>|  
|<span data-ttu-id="ee0e7-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ee0e7-106">Keywords</span></span>|<span data-ttu-id="ee0e7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ee0e7-107">WFRuntime</span></span>|  
|<span data-ttu-id="ee0e7-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ee0e7-108">Level</span></span>|<span data-ttu-id="ee0e7-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="ee0e7-109">Verbose</span></span>|  
|<span data-ttu-id="ee0e7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ee0e7-110">Channel</span></span>|<span data-ttu-id="ee0e7-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ee0e7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ee0e7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee0e7-112">Description</span></span>  
 <span data-ttu-id="ee0e7-113">Indica que un RuntimeWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="ee0e7-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ee0e7-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ee0e7-114">Message</span></span>  
 <span data-ttu-id="ee0e7-115">Iniciando la ejecución de un elemento de trabajo de runtime para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="ee0e7-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ee0e7-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="ee0e7-116">Details</span></span>  
  
|<span data-ttu-id="ee0e7-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ee0e7-117">Data Item Name</span></span>|<span data-ttu-id="ee0e7-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ee0e7-118">Data Item Type</span></span>|<span data-ttu-id="ee0e7-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee0e7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ee0e7-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="ee0e7-120">Activity</span></span>|<span data-ttu-id="ee0e7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee0e7-121">xs:string</span></span>|<span data-ttu-id="ee0e7-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ee0e7-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ee0e7-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ee0e7-123">DisplayName</span></span>|<span data-ttu-id="ee0e7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee0e7-124">xs:string</span></span>|<span data-ttu-id="ee0e7-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ee0e7-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ee0e7-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ee0e7-126">InstanceId</span></span>|<span data-ttu-id="ee0e7-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee0e7-127">xs:string</span></span>|<span data-ttu-id="ee0e7-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="ee0e7-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ee0e7-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ee0e7-129">AppDomain</span></span>|<span data-ttu-id="ee0e7-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ee0e7-130">xs:string</span></span>|<span data-ttu-id="ee0e7-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ee0e7-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
