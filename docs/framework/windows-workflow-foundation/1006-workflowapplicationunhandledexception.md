---
description: 'Más información acerca de: 1006-WorkflowApplicationUnhandledException'
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: bfccd0d12c5dac4caad1e84e95f1cd096a551aa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755595"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="29336-103">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="29336-103">1006 - WorkflowApplicationUnhandledException</span></span>

## <a name="properties"></a><span data-ttu-id="29336-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="29336-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29336-105">Id.</span><span class="sxs-lookup"><span data-stu-id="29336-105">ID</span></span>|<span data-ttu-id="29336-106">1006</span><span class="sxs-lookup"><span data-stu-id="29336-106">1006</span></span>|  
|<span data-ttu-id="29336-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="29336-107">Keywords</span></span>|<span data-ttu-id="29336-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="29336-108">WFRuntime</span></span>|  
|<span data-ttu-id="29336-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="29336-109">Level</span></span>|<span data-ttu-id="29336-110">Error</span><span class="sxs-lookup"><span data-stu-id="29336-110">Error</span></span>|  
|<span data-ttu-id="29336-111">Canal</span><span class="sxs-lookup"><span data-stu-id="29336-111">Channel</span></span>|<span data-ttu-id="29336-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="29336-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="29336-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="29336-113">Description</span></span>  

 <span data-ttu-id="29336-114">Indica que una aplicación de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="29336-114">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="29336-115">Message</span><span class="sxs-lookup"><span data-stu-id="29336-115">Message</span></span>  

 <span data-ttu-id="29336-116">WorkflowInstance ID: ' %1 ' ha encontrado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="29336-116">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="29336-117">La excepción se originó a partir de la actividad ' %2 ', DisplayName: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="29336-117">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="29336-118">Se realizará la siguiente acción: %4.</span><span class="sxs-lookup"><span data-stu-id="29336-118">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="29336-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="29336-119">Details</span></span>  
  
|<span data-ttu-id="29336-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="29336-120">Data Item Name</span></span>|<span data-ttu-id="29336-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="29336-121">Data Item Type</span></span>|<span data-ttu-id="29336-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="29336-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="29336-123">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="29336-123">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="29336-124">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="29336-124">The instance id for the workflow</span></span>|  
|<span data-ttu-id="29336-125">Excepción</span><span class="sxs-lookup"><span data-stu-id="29336-125">Exception</span></span>|`xs:string`|<span data-ttu-id="29336-126">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="29336-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="29336-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="29336-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="29336-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="29336-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
