---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 3b7210246b7fb754145c8aa6128da3183cea9f91
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239866"
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="0eac3-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="0eac3-102">1005 - WorkflowApplicationIdled</span></span>

## <a name="properties"></a><span data-ttu-id="0eac3-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0eac3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0eac3-104">ID</span><span class="sxs-lookup"><span data-stu-id="0eac3-104">ID</span></span>|<span data-ttu-id="0eac3-105">1005</span><span class="sxs-lookup"><span data-stu-id="0eac3-105">1005</span></span>|  
|<span data-ttu-id="0eac3-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0eac3-106">Keywords</span></span>|<span data-ttu-id="0eac3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0eac3-107">WFRuntime</span></span>|  
|<span data-ttu-id="0eac3-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="0eac3-108">Level</span></span>|<span data-ttu-id="0eac3-109">Información</span><span class="sxs-lookup"><span data-stu-id="0eac3-109">Information</span></span>|  
|<span data-ttu-id="0eac3-110">Canal</span><span class="sxs-lookup"><span data-stu-id="0eac3-110">Channel</span></span>|<span data-ttu-id="0eac3-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="0eac3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0eac3-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eac3-112">Description</span></span>  

 <span data-ttu-id="0eac3-113">Indica que una aplicación de flujo de trabajo ha estado inactiva.</span><span class="sxs-lookup"><span data-stu-id="0eac3-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0eac3-114">Message</span><span class="sxs-lookup"><span data-stu-id="0eac3-114">Message</span></span>  

 <span data-ttu-id="0eac3-115">WorkflowApplication Id: '%1' se desactivó.</span><span class="sxs-lookup"><span data-stu-id="0eac3-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0eac3-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="0eac3-116">Details</span></span>  
  
|<span data-ttu-id="0eac3-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0eac3-117">Data Item Name</span></span>|<span data-ttu-id="0eac3-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="0eac3-118">Data Item Type</span></span>|<span data-ttu-id="0eac3-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="0eac3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0eac3-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="0eac3-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="0eac3-121">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0eac3-121">The workflow application id</span></span>|  
|<span data-ttu-id="0eac3-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0eac3-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0eac3-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="0eac3-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
