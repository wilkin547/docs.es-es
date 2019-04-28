---
title: 1006 - WorkflowApplicationUnhandledException
ms.date: 03/30/2017
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
ms.openlocfilehash: 471f3ecea66ebbd07a09686ab536a84b25d46e6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924714"
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="3ca3b-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="3ca3b-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="3ca3b-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3ca3b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ca3b-104">ID</span><span class="sxs-lookup"><span data-stu-id="3ca3b-104">ID</span></span>|<span data-ttu-id="3ca3b-105">1006</span><span class="sxs-lookup"><span data-stu-id="3ca3b-105">1006</span></span>|  
|<span data-ttu-id="3ca3b-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="3ca3b-106">Keywords</span></span>|<span data-ttu-id="3ca3b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3ca3b-107">WFRuntime</span></span>|  
|<span data-ttu-id="3ca3b-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="3ca3b-108">Level</span></span>|<span data-ttu-id="3ca3b-109">Error</span><span class="sxs-lookup"><span data-stu-id="3ca3b-109">Error</span></span>|  
|<span data-ttu-id="3ca3b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="3ca3b-110">Channel</span></span>|<span data-ttu-id="3ca3b-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="3ca3b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ca3b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ca3b-112">Description</span></span>  
 <span data-ttu-id="3ca3b-113">Indica que una aplicación de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="3ca3b-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ca3b-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="3ca3b-114">Message</span></span>  
 <span data-ttu-id="3ca3b-115">WorkflowInstance Id: '%1' ha encontrado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="3ca3b-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="3ca3b-116">La excepción originada desde la actividad '%2', DisplayName: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3ca3b-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="3ca3b-117">Se realizará la acción siguiente: %4.</span><span class="sxs-lookup"><span data-stu-id="3ca3b-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ca3b-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="3ca3b-118">Details</span></span>  
  
|<span data-ttu-id="3ca3b-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3ca3b-119">Data Item Name</span></span>|<span data-ttu-id="3ca3b-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="3ca3b-120">Data Item Type</span></span>|<span data-ttu-id="3ca3b-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ca3b-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ca3b-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="3ca3b-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="3ca3b-123">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3ca3b-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="3ca3b-124">Excepción</span><span class="sxs-lookup"><span data-stu-id="3ca3b-124">Exception</span></span>|`xs:string`|<span data-ttu-id="3ca3b-125">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="3ca3b-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="3ca3b-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3ca3b-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3ca3b-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="3ca3b-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
