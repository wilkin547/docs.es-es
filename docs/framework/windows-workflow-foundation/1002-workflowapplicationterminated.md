---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008660"
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="5aedb-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="5aedb-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="5aedb-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5aedb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5aedb-104">ID</span><span class="sxs-lookup"><span data-stu-id="5aedb-104">ID</span></span>|<span data-ttu-id="5aedb-105">1002</span><span class="sxs-lookup"><span data-stu-id="5aedb-105">1002</span></span>|  
|<span data-ttu-id="5aedb-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5aedb-106">Keywords</span></span>|<span data-ttu-id="5aedb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5aedb-107">WFRuntime</span></span>|  
|<span data-ttu-id="5aedb-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="5aedb-108">Level</span></span>|<span data-ttu-id="5aedb-109">Información</span><span class="sxs-lookup"><span data-stu-id="5aedb-109">Information</span></span>|  
|<span data-ttu-id="5aedb-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5aedb-110">Channel</span></span>|<span data-ttu-id="5aedb-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="5aedb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5aedb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5aedb-112">Description</span></span>  
 <span data-ttu-id="5aedb-113">Indica que una aplicación de flujo de trabajo ha finalizado en el estado Faulted con una excepción.</span><span class="sxs-lookup"><span data-stu-id="5aedb-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5aedb-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="5aedb-114">Message</span></span>  
 <span data-ttu-id="5aedb-115">WorkflowApplication Id: '%1' se terminó.</span><span class="sxs-lookup"><span data-stu-id="5aedb-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="5aedb-116">Se ha completado con el estado Faulted y con una excepción.</span><span class="sxs-lookup"><span data-stu-id="5aedb-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5aedb-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="5aedb-117">Details</span></span>  
  
|<span data-ttu-id="5aedb-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5aedb-118">Data Item Name</span></span>|<span data-ttu-id="5aedb-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5aedb-119">Data Item Type</span></span>|<span data-ttu-id="5aedb-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="5aedb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5aedb-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="5aedb-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="5aedb-122">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5aedb-122">The workflow application id</span></span>|  
|<span data-ttu-id="5aedb-123">Excepción</span><span class="sxs-lookup"><span data-stu-id="5aedb-123">Exception</span></span>|`xs:string`|<span data-ttu-id="5aedb-124">Detalles de la excepción para la excepción</span><span class="sxs-lookup"><span data-stu-id="5aedb-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="5aedb-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5aedb-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5aedb-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5aedb-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
