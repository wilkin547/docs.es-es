---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509800"
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="cf0b4-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="cf0b4-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="cf0b4-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="cf0b4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cf0b4-104">Id.</span><span class="sxs-lookup"><span data-stu-id="cf0b4-104">ID</span></span>|<span data-ttu-id="cf0b4-105">1001</span><span class="sxs-lookup"><span data-stu-id="cf0b4-105">1001</span></span>|  
|<span data-ttu-id="cf0b4-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="cf0b4-106">Keywords</span></span>|<span data-ttu-id="cf0b4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="cf0b4-107">WFRuntime</span></span>|  
|<span data-ttu-id="cf0b4-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="cf0b4-108">Level</span></span>|<span data-ttu-id="cf0b4-109">Información</span><span class="sxs-lookup"><span data-stu-id="cf0b4-109">Information</span></span>|  
|<span data-ttu-id="cf0b4-110">Canal</span><span class="sxs-lookup"><span data-stu-id="cf0b4-110">Channel</span></span>|<span data-ttu-id="cf0b4-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="cf0b4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cf0b4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf0b4-112">Description</span></span>  
 <span data-ttu-id="cf0b4-113">Indica que una aplicación de flujo de trabajo se ha completado en el estado Closed.</span><span class="sxs-lookup"><span data-stu-id="cf0b4-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cf0b4-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="cf0b4-114">Message</span></span>  
 <span data-ttu-id="cf0b4-115">WorkflowInstance Id: '%1' se completó en el estado Closed.</span><span class="sxs-lookup"><span data-stu-id="cf0b4-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cf0b4-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="cf0b4-116">Details</span></span>  
  
|<span data-ttu-id="cf0b4-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cf0b4-117">Data Item Name</span></span>|<span data-ttu-id="cf0b4-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="cf0b4-118">Data Item Type</span></span>|<span data-ttu-id="cf0b4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="cf0b4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cf0b4-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="cf0b4-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="cf0b4-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cf0b4-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="cf0b4-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cf0b4-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="cf0b4-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="cf0b4-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
