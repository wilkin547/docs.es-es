---
description: 'Más información acerca de: 1002-WorkflowApplicationTerminated'
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 8ceef41515231833767fc7e2095ab3850bf80e41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755633"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="35cef-103">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="35cef-103">1002 - WorkflowApplicationTerminated</span></span>

## <a name="properties"></a><span data-ttu-id="35cef-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="35cef-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="35cef-105">Id.</span><span class="sxs-lookup"><span data-stu-id="35cef-105">ID</span></span>|<span data-ttu-id="35cef-106">1002</span><span class="sxs-lookup"><span data-stu-id="35cef-106">1002</span></span>|  
|<span data-ttu-id="35cef-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="35cef-107">Keywords</span></span>|<span data-ttu-id="35cef-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="35cef-108">WFRuntime</span></span>|  
|<span data-ttu-id="35cef-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="35cef-109">Level</span></span>|<span data-ttu-id="35cef-110">Información</span><span class="sxs-lookup"><span data-stu-id="35cef-110">Information</span></span>|  
|<span data-ttu-id="35cef-111">Canal</span><span class="sxs-lookup"><span data-stu-id="35cef-111">Channel</span></span>|<span data-ttu-id="35cef-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="35cef-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="35cef-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="35cef-113">Description</span></span>  

 <span data-ttu-id="35cef-114">Indica que una aplicación de flujo de trabajo ha finalizado en el estado Faulted con una excepción.</span><span class="sxs-lookup"><span data-stu-id="35cef-114">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="35cef-115">Message</span><span class="sxs-lookup"><span data-stu-id="35cef-115">Message</span></span>  

 <span data-ttu-id="35cef-116">WorkflowApplication Id: '%1' se terminó.</span><span class="sxs-lookup"><span data-stu-id="35cef-116">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="35cef-117">Se ha completado con el estado Faulted y con una excepción.</span><span class="sxs-lookup"><span data-stu-id="35cef-117">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="35cef-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="35cef-118">Details</span></span>  
  
|<span data-ttu-id="35cef-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="35cef-119">Data Item Name</span></span>|<span data-ttu-id="35cef-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="35cef-120">Data Item Type</span></span>|<span data-ttu-id="35cef-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="35cef-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="35cef-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="35cef-122">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="35cef-123">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="35cef-123">The workflow application id</span></span>|  
|<span data-ttu-id="35cef-124">Excepción</span><span class="sxs-lookup"><span data-stu-id="35cef-124">Exception</span></span>|`xs:string`|<span data-ttu-id="35cef-125">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="35cef-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="35cef-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="35cef-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="35cef-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="35cef-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
