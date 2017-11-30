---
title: 1005 - WorkflowApplicationIdled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 42d22a7187adc712c0f236111cecac89dd59e2f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="fdb37-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="fdb37-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="fdb37-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fdb37-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fdb37-104">Id.</span><span class="sxs-lookup"><span data-stu-id="fdb37-104">ID</span></span>|<span data-ttu-id="fdb37-105">1005</span><span class="sxs-lookup"><span data-stu-id="fdb37-105">1005</span></span>|  
|<span data-ttu-id="fdb37-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="fdb37-106">Keywords</span></span>|<span data-ttu-id="fdb37-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fdb37-107">WFRuntime</span></span>|  
|<span data-ttu-id="fdb37-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="fdb37-108">Level</span></span>|<span data-ttu-id="fdb37-109">Información</span><span class="sxs-lookup"><span data-stu-id="fdb37-109">Information</span></span>|  
|<span data-ttu-id="fdb37-110">Canal</span><span class="sxs-lookup"><span data-stu-id="fdb37-110">Channel</span></span>|<span data-ttu-id="fdb37-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="fdb37-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fdb37-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdb37-112">Description</span></span>  
 <span data-ttu-id="fdb37-113">Indica que una aplicación de flujo de trabajo ha estado inactiva.</span><span class="sxs-lookup"><span data-stu-id="fdb37-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fdb37-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="fdb37-114">Message</span></span>  
 <span data-ttu-id="fdb37-115">WorkflowApplication Id: '%1' se desactivó.</span><span class="sxs-lookup"><span data-stu-id="fdb37-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fdb37-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="fdb37-116">Details</span></span>  
  
|<span data-ttu-id="fdb37-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fdb37-117">Data Item Name</span></span>|<span data-ttu-id="fdb37-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="fdb37-118">Data Item Type</span></span>|<span data-ttu-id="fdb37-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdb37-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fdb37-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="fdb37-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="fdb37-121">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdb37-121">The workflow application id</span></span>|  
|<span data-ttu-id="fdb37-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fdb37-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="fdb37-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="fdb37-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
