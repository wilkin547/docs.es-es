---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510084"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="5027e-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="5027e-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="5027e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5027e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5027e-104">Id.</span><span class="sxs-lookup"><span data-stu-id="5027e-104">ID</span></span>|<span data-ttu-id="5027e-105">1002</span><span class="sxs-lookup"><span data-stu-id="5027e-105">1002</span></span>|  
|<span data-ttu-id="5027e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5027e-106">Keywords</span></span>|<span data-ttu-id="5027e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5027e-107">WFRuntime</span></span>|  
|<span data-ttu-id="5027e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="5027e-108">Level</span></span>|<span data-ttu-id="5027e-109">Información</span><span class="sxs-lookup"><span data-stu-id="5027e-109">Information</span></span>|  
|<span data-ttu-id="5027e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5027e-110">Channel</span></span>|<span data-ttu-id="5027e-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5027e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5027e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5027e-112">Description</span></span>  
 <span data-ttu-id="5027e-113">Indica que una aplicación de flujo de trabajo ha finalizado en el estado Faulted con una excepción.</span><span class="sxs-lookup"><span data-stu-id="5027e-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5027e-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="5027e-114">Message</span></span>  
 <span data-ttu-id="5027e-115">WorkflowApplication Id: '%1' se terminó.</span><span class="sxs-lookup"><span data-stu-id="5027e-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="5027e-116">Se ha completado con el estado Faulted y con una excepción.</span><span class="sxs-lookup"><span data-stu-id="5027e-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5027e-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="5027e-117">Details</span></span>  
  
|<span data-ttu-id="5027e-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5027e-118">Data Item Name</span></span>|<span data-ttu-id="5027e-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5027e-119">Data Item Type</span></span>|<span data-ttu-id="5027e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="5027e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5027e-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="5027e-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="5027e-122">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5027e-122">The workflow application id</span></span>|  
|<span data-ttu-id="5027e-123">Excepción</span><span class="sxs-lookup"><span data-stu-id="5027e-123">Exception</span></span>|`xs:string`|<span data-ttu-id="5027e-124">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="5027e-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="5027e-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5027e-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5027e-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5027e-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
