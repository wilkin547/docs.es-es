---
title: 1018 - StartCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
ms.openlocfilehash: 8d7045b0a7f31ecfd5dd90f319192bd202804353
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008868"
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="b7002-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="b7002-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b7002-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b7002-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b7002-104">ID</span><span class="sxs-lookup"><span data-stu-id="b7002-104">ID</span></span>|<span data-ttu-id="b7002-105">1018</span><span class="sxs-lookup"><span data-stu-id="b7002-105">1018</span></span>|  
|<span data-ttu-id="b7002-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="b7002-106">Keywords</span></span>|<span data-ttu-id="b7002-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b7002-107">WFRuntime</span></span>|  
|<span data-ttu-id="b7002-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="b7002-108">Level</span></span>|<span data-ttu-id="b7002-109">Detallado</span><span class="sxs-lookup"><span data-stu-id="b7002-109">Verbose</span></span>|  
|<span data-ttu-id="b7002-110">Canal</span><span class="sxs-lookup"><span data-stu-id="b7002-110">Channel</span></span>|<span data-ttu-id="b7002-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="b7002-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b7002-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7002-112">Description</span></span>  
 <span data-ttu-id="b7002-113">Indica que un CancelActivityWorkItem está iniciando la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7002-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b7002-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="b7002-114">Message</span></span>  
 <span data-ttu-id="b7002-115">Iniciando la ejecución de un CancelActivityWorkItem para la actividad '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="b7002-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b7002-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="b7002-116">Details</span></span>  
  
|<span data-ttu-id="b7002-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b7002-117">Data Item Name</span></span>|<span data-ttu-id="b7002-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="b7002-118">Data Item Type</span></span>|<span data-ttu-id="b7002-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7002-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b7002-120">Actividad</span><span class="sxs-lookup"><span data-stu-id="b7002-120">Activity</span></span>|<span data-ttu-id="b7002-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7002-121">xs:string</span></span>|<span data-ttu-id="b7002-122">El nombre de tipo de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b7002-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b7002-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b7002-123">DisplayName</span></span>|<span data-ttu-id="b7002-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7002-124">xs:string</span></span>|<span data-ttu-id="b7002-125">El nombre para mostrar de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b7002-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b7002-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b7002-126">InstanceId</span></span>|<span data-ttu-id="b7002-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7002-127">xs:string</span></span>|<span data-ttu-id="b7002-128">La identificación de instancia de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b7002-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b7002-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b7002-129">AppDomain</span></span>|<span data-ttu-id="b7002-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b7002-130">xs:string</span></span>|<span data-ttu-id="b7002-131">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="b7002-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
