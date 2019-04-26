---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: d6b330bc454c39584e5027f757fd9d9d3434d941
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924584"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="0040e-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="0040e-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="0040e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0040e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0040e-104">ID</span><span class="sxs-lookup"><span data-stu-id="0040e-104">ID</span></span>|<span data-ttu-id="0040e-105">1012</span><span class="sxs-lookup"><span data-stu-id="0040e-105">1012</span></span>|  
|<span data-ttu-id="0040e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0040e-106">Keywords</span></span>|<span data-ttu-id="0040e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0040e-107">WFRuntime</span></span>|  
|<span data-ttu-id="0040e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0040e-108">Level</span></span>|<span data-ttu-id="0040e-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="0040e-109">Verbose</span></span>|  
|<span data-ttu-id="0040e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0040e-110">Channel</span></span>|<span data-ttu-id="0040e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0040e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0040e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0040e-112">Description</span></span>  
 <span data-ttu-id="0040e-113">Indica que un ExecuteActivityWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="0040e-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0040e-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="0040e-114">Message</span></span>  
 <span data-ttu-id="0040e-115">Iniciando la ejecución de un ExecuteActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="0040e-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0040e-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="0040e-116">Details</span></span>  
  
|<span data-ttu-id="0040e-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0040e-117">Data Item Name</span></span>|<span data-ttu-id="0040e-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0040e-118">Data Item Type</span></span>|<span data-ttu-id="0040e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="0040e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0040e-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="0040e-120">Activity</span></span>|<span data-ttu-id="0040e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0040e-121">xs:string</span></span>|<span data-ttu-id="0040e-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0040e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="0040e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0040e-123">DisplayName</span></span>|<span data-ttu-id="0040e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0040e-124">xs:string</span></span>|<span data-ttu-id="0040e-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0040e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="0040e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="0040e-126">InstanceId</span></span>|<span data-ttu-id="0040e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="0040e-127">xs:string</span></span>|<span data-ttu-id="0040e-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0040e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="0040e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0040e-129">AppDomain</span></span>|<span data-ttu-id="0040e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="0040e-130">xs:string</span></span>|<span data-ttu-id="0040e-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0040e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
