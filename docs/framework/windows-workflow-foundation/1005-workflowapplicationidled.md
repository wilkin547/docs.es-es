---
description: 'Más información acerca de: 1005-WorkflowApplicationIdled'
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: ee8d0b7ff2155333213a718a04c3966024fda89d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755608"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="8b78f-103">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="8b78f-103">1005 - WorkflowApplicationIdled</span></span>

## <a name="properties"></a><span data-ttu-id="8b78f-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8b78f-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8b78f-105">Id.</span><span class="sxs-lookup"><span data-stu-id="8b78f-105">ID</span></span>|<span data-ttu-id="8b78f-106">1005</span><span class="sxs-lookup"><span data-stu-id="8b78f-106">1005</span></span>|  
|<span data-ttu-id="8b78f-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="8b78f-107">Keywords</span></span>|<span data-ttu-id="8b78f-108">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8b78f-108">WFRuntime</span></span>|  
|<span data-ttu-id="8b78f-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="8b78f-109">Level</span></span>|<span data-ttu-id="8b78f-110">Información</span><span class="sxs-lookup"><span data-stu-id="8b78f-110">Information</span></span>|  
|<span data-ttu-id="8b78f-111">Canal</span><span class="sxs-lookup"><span data-stu-id="8b78f-111">Channel</span></span>|<span data-ttu-id="8b78f-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="8b78f-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8b78f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b78f-113">Description</span></span>  

 <span data-ttu-id="8b78f-114">Indica que una aplicación de flujo de trabajo ha estado inactiva.</span><span class="sxs-lookup"><span data-stu-id="8b78f-114">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8b78f-115">Message</span><span class="sxs-lookup"><span data-stu-id="8b78f-115">Message</span></span>  

 <span data-ttu-id="8b78f-116">WorkflowApplication Id: '%1' se desactivó.</span><span class="sxs-lookup"><span data-stu-id="8b78f-116">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8b78f-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="8b78f-117">Details</span></span>  
  
|<span data-ttu-id="8b78f-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8b78f-118">Data Item Name</span></span>|<span data-ttu-id="8b78f-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="8b78f-119">Data Item Type</span></span>|<span data-ttu-id="8b78f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b78f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8b78f-121">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="8b78f-121">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="8b78f-122">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8b78f-122">The workflow application id</span></span>|  
|<span data-ttu-id="8b78f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8b78f-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8b78f-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="8b78f-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
