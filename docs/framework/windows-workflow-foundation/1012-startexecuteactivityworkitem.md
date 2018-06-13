---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: d6b330bc454c39584e5027f757fd9d9d3434d941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510385"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="3fac1-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="3fac1-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="3fac1-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3fac1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3fac1-104">Id.</span><span class="sxs-lookup"><span data-stu-id="3fac1-104">ID</span></span>|<span data-ttu-id="3fac1-105">1012</span><span class="sxs-lookup"><span data-stu-id="3fac1-105">1012</span></span>|  
|<span data-ttu-id="3fac1-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3fac1-106">Keywords</span></span>|<span data-ttu-id="3fac1-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3fac1-107">WFRuntime</span></span>|  
|<span data-ttu-id="3fac1-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3fac1-108">Level</span></span>|<span data-ttu-id="3fac1-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="3fac1-109">Verbose</span></span>|  
|<span data-ttu-id="3fac1-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3fac1-110">Channel</span></span>|<span data-ttu-id="3fac1-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3fac1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3fac1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fac1-112">Description</span></span>  
 <span data-ttu-id="3fac1-113">Indica que un ExecuteActivityWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="3fac1-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3fac1-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="3fac1-114">Message</span></span>  
 <span data-ttu-id="3fac1-115">Iniciando la ejecución de un ExecuteActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3fac1-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3fac1-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="3fac1-116">Details</span></span>  
  
|<span data-ttu-id="3fac1-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3fac1-117">Data Item Name</span></span>|<span data-ttu-id="3fac1-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3fac1-118">Data Item Type</span></span>|<span data-ttu-id="3fac1-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fac1-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3fac1-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="3fac1-120">Activity</span></span>|<span data-ttu-id="3fac1-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3fac1-121">xs:string</span></span>|<span data-ttu-id="3fac1-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3fac1-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3fac1-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3fac1-123">DisplayName</span></span>|<span data-ttu-id="3fac1-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3fac1-124">xs:string</span></span>|<span data-ttu-id="3fac1-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3fac1-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3fac1-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3fac1-126">InstanceId</span></span>|<span data-ttu-id="3fac1-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3fac1-127">xs:string</span></span>|<span data-ttu-id="3fac1-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3fac1-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3fac1-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3fac1-129">AppDomain</span></span>|<span data-ttu-id="3fac1-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3fac1-130">xs:string</span></span>|<span data-ttu-id="3fac1-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3fac1-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
