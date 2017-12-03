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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2603621eb23747275e6db22a1743c5260967c6a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="a7f17-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="a7f17-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="a7f17-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a7f17-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a7f17-104">Id.</span><span class="sxs-lookup"><span data-stu-id="a7f17-104">ID</span></span>|<span data-ttu-id="a7f17-105">1005</span><span class="sxs-lookup"><span data-stu-id="a7f17-105">1005</span></span>|  
|<span data-ttu-id="a7f17-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a7f17-106">Keywords</span></span>|<span data-ttu-id="a7f17-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a7f17-107">WFRuntime</span></span>|  
|<span data-ttu-id="a7f17-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="a7f17-108">Level</span></span>|<span data-ttu-id="a7f17-109">Información</span><span class="sxs-lookup"><span data-stu-id="a7f17-109">Information</span></span>|  
|<span data-ttu-id="a7f17-110">Canal</span><span class="sxs-lookup"><span data-stu-id="a7f17-110">Channel</span></span>|<span data-ttu-id="a7f17-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="a7f17-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a7f17-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7f17-112">Description</span></span>  
 <span data-ttu-id="a7f17-113">Indica que una aplicación de flujo de trabajo ha estado inactiva.</span><span class="sxs-lookup"><span data-stu-id="a7f17-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a7f17-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="a7f17-114">Message</span></span>  
 <span data-ttu-id="a7f17-115">WorkflowApplication Id: '%1' se desactivó.</span><span class="sxs-lookup"><span data-stu-id="a7f17-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a7f17-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="a7f17-116">Details</span></span>  
  
|<span data-ttu-id="a7f17-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a7f17-117">Data Item Name</span></span>|<span data-ttu-id="a7f17-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="a7f17-118">Data Item Type</span></span>|<span data-ttu-id="a7f17-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7f17-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a7f17-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a7f17-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="a7f17-121">Identificador de la aplicación del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a7f17-121">The workflow application id</span></span>|  
|<span data-ttu-id="a7f17-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a7f17-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a7f17-123">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="a7f17-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
