---
title: 1001 - WorkflowApplicationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a62a8448319e7b07a3ea302f00f2fa269bf654ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="19bfc-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="19bfc-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="19bfc-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="19bfc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="19bfc-104">Id.</span><span class="sxs-lookup"><span data-stu-id="19bfc-104">ID</span></span>|<span data-ttu-id="19bfc-105">1001</span><span class="sxs-lookup"><span data-stu-id="19bfc-105">1001</span></span>|  
|<span data-ttu-id="19bfc-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="19bfc-106">Keywords</span></span>|<span data-ttu-id="19bfc-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="19bfc-107">WFRuntime</span></span>|  
|<span data-ttu-id="19bfc-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="19bfc-108">Level</span></span>|<span data-ttu-id="19bfc-109">Información</span><span class="sxs-lookup"><span data-stu-id="19bfc-109">Information</span></span>|  
|<span data-ttu-id="19bfc-110">Canal</span><span class="sxs-lookup"><span data-stu-id="19bfc-110">Channel</span></span>|<span data-ttu-id="19bfc-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="19bfc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="19bfc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="19bfc-112">Description</span></span>  
 <span data-ttu-id="19bfc-113">Indica que una aplicación de flujo de trabajo se ha completado en el estado Closed.</span><span class="sxs-lookup"><span data-stu-id="19bfc-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="19bfc-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="19bfc-114">Message</span></span>  
 <span data-ttu-id="19bfc-115">WorkflowInstance Id: '%1' se completó en el estado Closed.</span><span class="sxs-lookup"><span data-stu-id="19bfc-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="19bfc-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="19bfc-116">Details</span></span>  
  
|<span data-ttu-id="19bfc-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="19bfc-117">Data Item Name</span></span>|<span data-ttu-id="19bfc-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="19bfc-118">Data Item Type</span></span>|<span data-ttu-id="19bfc-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="19bfc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="19bfc-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="19bfc-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="19bfc-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="19bfc-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="19bfc-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="19bfc-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="19bfc-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="19bfc-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
