---
title: 1004 - WorkflowInstanceAborted
ms.date: 03/30/2017
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
ms.openlocfilehash: d1eaf3cf107a6b5e244cc2d9372ee68d387ef6c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510671"
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="a88a2-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="a88a2-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="a88a2-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a88a2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a88a2-104">Id.</span><span class="sxs-lookup"><span data-stu-id="a88a2-104">ID</span></span>|<span data-ttu-id="a88a2-105">1004</span><span class="sxs-lookup"><span data-stu-id="a88a2-105">1004</span></span>|  
|<span data-ttu-id="a88a2-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a88a2-106">Keywords</span></span>|<span data-ttu-id="a88a2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a88a2-107">WFRuntime</span></span>|  
|<span data-ttu-id="a88a2-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a88a2-108">Level</span></span>|<span data-ttu-id="a88a2-109">Información</span><span class="sxs-lookup"><span data-stu-id="a88a2-109">Information</span></span>|  
|<span data-ttu-id="a88a2-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a88a2-110">Channel</span></span>|<span data-ttu-id="a88a2-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a88a2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a88a2-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a88a2-112">Description</span></span>  
 <span data-ttu-id="a88a2-113">Indica que una instancia de flujo de trabajo se ha anulado con una excepción.</span><span class="sxs-lookup"><span data-stu-id="a88a2-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a88a2-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a88a2-114">Message</span></span>  
 <span data-ttu-id="a88a2-115">WorkflowInstance Id: '%1' se anuló con una excepción.</span><span class="sxs-lookup"><span data-stu-id="a88a2-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a88a2-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="a88a2-116">Details</span></span>  
  
|<span data-ttu-id="a88a2-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a88a2-117">Data Item Name</span></span>|<span data-ttu-id="a88a2-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a88a2-118">Data Item Type</span></span>|<span data-ttu-id="a88a2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a88a2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a88a2-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a88a2-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="a88a2-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a88a2-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="a88a2-122">Excepción</span><span class="sxs-lookup"><span data-stu-id="a88a2-122">Exception</span></span>|`xs:string`|<span data-ttu-id="a88a2-123">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="a88a2-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="a88a2-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a88a2-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a88a2-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a88a2-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
