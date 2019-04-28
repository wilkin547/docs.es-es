---
title: 1008 - WorkflowApplicationUnloaded
ms.date: 03/30/2017
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
ms.openlocfilehash: c7c22e6e4270a3fc3e91e1711db5da9bd5a378b9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925234"
---
# <a name="1008---workflowapplicationunloaded"></a><span data-ttu-id="e7c12-102">1008 - WorkflowApplicationUnloaded</span><span class="sxs-lookup"><span data-stu-id="e7c12-102">1008 - WorkflowApplicationUnloaded</span></span>
## <a name="properties"></a><span data-ttu-id="e7c12-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e7c12-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e7c12-104">ID</span><span class="sxs-lookup"><span data-stu-id="e7c12-104">ID</span></span>|<span data-ttu-id="e7c12-105">1008</span><span class="sxs-lookup"><span data-stu-id="e7c12-105">1008</span></span>|  
|<span data-ttu-id="e7c12-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e7c12-106">Keywords</span></span>|<span data-ttu-id="e7c12-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e7c12-107">WFRuntime</span></span>|  
|<span data-ttu-id="e7c12-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e7c12-108">Level</span></span>|<span data-ttu-id="e7c12-109">Información</span><span class="sxs-lookup"><span data-stu-id="e7c12-109">Information</span></span>|  
|<span data-ttu-id="e7c12-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e7c12-110">Channel</span></span>|<span data-ttu-id="e7c12-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="e7c12-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e7c12-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7c12-112">Description</span></span>  
 <span data-ttu-id="e7c12-113">Indica que una aplicación de flujo de trabajo se ha cargado.</span><span class="sxs-lookup"><span data-stu-id="e7c12-113">Indicates a workflow application has unloaded.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e7c12-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="e7c12-114">Message</span></span>  
 <span data-ttu-id="e7c12-115">WorkflowInstance Id: '%1' se descargó.</span><span class="sxs-lookup"><span data-stu-id="e7c12-115">WorkflowInstance Id: '%1' was Unloaded.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e7c12-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="e7c12-116">Details</span></span>  
  
|<span data-ttu-id="e7c12-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e7c12-117">Data Item Name</span></span>|<span data-ttu-id="e7c12-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e7c12-118">Data Item Type</span></span>|<span data-ttu-id="e7c12-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7c12-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e7c12-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="e7c12-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="e7c12-121">El id. de instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e7c12-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="e7c12-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e7c12-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e7c12-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e7c12-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
