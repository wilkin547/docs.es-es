---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 4bb76a93ec7a07a735def1f1d5dc79decb7792ad
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239840"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="45720-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="45720-102">1006 - WorkflowApplicationUnhandledException</span></span>

## <a name="properties"></a><span data-ttu-id="45720-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="45720-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45720-104">ID</span><span class="sxs-lookup"><span data-stu-id="45720-104">ID</span></span>|<span data-ttu-id="45720-105">1006</span><span class="sxs-lookup"><span data-stu-id="45720-105">1006</span></span>|  
|<span data-ttu-id="45720-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="45720-106">Keywords</span></span>|<span data-ttu-id="45720-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="45720-107">WFRuntime</span></span>|  
|<span data-ttu-id="45720-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="45720-108">Level</span></span>|<span data-ttu-id="45720-109">Error</span><span class="sxs-lookup"><span data-stu-id="45720-109">Error</span></span>|  
|<span data-ttu-id="45720-110">Canal</span><span class="sxs-lookup"><span data-stu-id="45720-110">Channel</span></span>|<span data-ttu-id="45720-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="45720-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="45720-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="45720-112">Description</span></span>  

 <span data-ttu-id="45720-113">Indica que una aplicación de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="45720-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="45720-114">Message</span><span class="sxs-lookup"><span data-stu-id="45720-114">Message</span></span>  

 <span data-ttu-id="45720-115">WorkflowInstance ID: ' %1 ' ha encontrado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="45720-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="45720-116">La excepción se originó a partir de la actividad ' %2 ', DisplayName: ' %3 '.</span><span class="sxs-lookup"><span data-stu-id="45720-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="45720-117">Se realizará la siguiente acción: %4.</span><span class="sxs-lookup"><span data-stu-id="45720-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="45720-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="45720-118">Details</span></span>  
  
|<span data-ttu-id="45720-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="45720-119">Data Item Name</span></span>|<span data-ttu-id="45720-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="45720-120">Data Item Type</span></span>|<span data-ttu-id="45720-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="45720-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="45720-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="45720-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="45720-123">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="45720-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="45720-124">Excepción</span><span class="sxs-lookup"><span data-stu-id="45720-124">Exception</span></span>|`xs:string`|<span data-ttu-id="45720-125">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="45720-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="45720-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="45720-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="45720-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="45720-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
