---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: 6ea121e7901d877d4f0d8f9f5bfd259c2f93696d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239826"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="d2577-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="d2577-102">1008 - WorkflowApplicationUnloaded</span></span>

## <a name="properties"></a><span data-ttu-id="d2577-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d2577-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2577-104">ID</span><span class="sxs-lookup"><span data-stu-id="d2577-104">ID</span></span>|<span data-ttu-id="d2577-105">1008</span><span class="sxs-lookup"><span data-stu-id="d2577-105">1008</span></span>|  
|<span data-ttu-id="d2577-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="d2577-106">Keywords</span></span>|<span data-ttu-id="d2577-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d2577-107">WFRuntime</span></span>|  
|<span data-ttu-id="d2577-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="d2577-108">Level</span></span>|<span data-ttu-id="d2577-109">Información</span><span class="sxs-lookup"><span data-stu-id="d2577-109">Information</span></span>|  
|<span data-ttu-id="d2577-110">Canal</span><span class="sxs-lookup"><span data-stu-id="d2577-110">Channel</span></span>|<span data-ttu-id="d2577-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="d2577-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d2577-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2577-112">Description</span></span>  

 <span data-ttu-id="d2577-113">Indica que una aplicación de flujo de trabajo se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="d2577-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d2577-114">Message</span><span class="sxs-lookup"><span data-stu-id="d2577-114">Message</span></span>  

 <span data-ttu-id="d2577-115">WorkflowInstance Id: '%1' se descargó.</span><span class="sxs-lookup"><span data-stu-id="d2577-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d2577-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="d2577-116">Details</span></span>  
  
|<span data-ttu-id="d2577-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d2577-117">Data Item Name</span></span>|<span data-ttu-id="d2577-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="d2577-118">Data Item Type</span></span>|<span data-ttu-id="d2577-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2577-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d2577-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="d2577-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="d2577-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d2577-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="d2577-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d2577-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d2577-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="d2577-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
