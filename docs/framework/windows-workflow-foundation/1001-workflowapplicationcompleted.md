---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: be97991be9b61908a23486da0ef255ebfbdc5485
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239957"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="4f726-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="4f726-102">1001 - WorkflowApplicationCompleted</span></span>

## <a name="properties"></a><span data-ttu-id="4f726-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4f726-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4f726-104">ID</span><span class="sxs-lookup"><span data-stu-id="4f726-104">ID</span></span>|<span data-ttu-id="4f726-105">1001</span><span class="sxs-lookup"><span data-stu-id="4f726-105">1001</span></span>|  
|<span data-ttu-id="4f726-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4f726-106">Keywords</span></span>|<span data-ttu-id="4f726-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4f726-107">WFRuntime</span></span>|  
|<span data-ttu-id="4f726-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="4f726-108">Level</span></span>|<span data-ttu-id="4f726-109">Información</span><span class="sxs-lookup"><span data-stu-id="4f726-109">Information</span></span>|  
|<span data-ttu-id="4f726-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4f726-110">Channel</span></span>|<span data-ttu-id="4f726-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="4f726-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4f726-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f726-112">Description</span></span>  

 <span data-ttu-id="4f726-113">Indica que una aplicación de flujo de trabajo se ha completado en el estado Closed.</span><span class="sxs-lookup"><span data-stu-id="4f726-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4f726-114">Message</span><span class="sxs-lookup"><span data-stu-id="4f726-114">Message</span></span>  

 <span data-ttu-id="4f726-115">WorkflowInstance Id: '%1' se completó en el estado Closed.</span><span class="sxs-lookup"><span data-stu-id="4f726-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4f726-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="4f726-116">Details</span></span>  
  
|<span data-ttu-id="4f726-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4f726-117">Data Item Name</span></span>|<span data-ttu-id="4f726-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4f726-118">Data Item Type</span></span>|<span data-ttu-id="4f726-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f726-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4f726-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="4f726-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="4f726-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f726-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="4f726-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4f726-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4f726-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4f726-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
