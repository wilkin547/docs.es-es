---
title: 4203 - RenewLockSystemError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c2214ec48f0c1cba1e3aacad0eaa5a29625f9c4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="87115-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="87115-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="87115-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="87115-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87115-104">Id.</span><span class="sxs-lookup"><span data-stu-id="87115-104">ID</span></span>|<span data-ttu-id="87115-105">4203</span><span class="sxs-lookup"><span data-stu-id="87115-105">4203</span></span>|  
|<span data-ttu-id="87115-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="87115-106">Keywords</span></span>|<span data-ttu-id="87115-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="87115-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="87115-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="87115-108">Level</span></span>|<span data-ttu-id="87115-109">Error</span><span class="sxs-lookup"><span data-stu-id="87115-109">Error</span></span>|  
|<span data-ttu-id="87115-110">Canal</span><span class="sxs-lookup"><span data-stu-id="87115-110">Channel</span></span>|<span data-ttu-id="87115-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="87115-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="87115-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="87115-112">Description</span></span>  
 <span data-ttu-id="87115-113">Indica que el proveedor de SQL no ha ampliado la expiración de bloqueo, debido a que la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="87115-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="87115-114">SqlWorkflowInstanceStore se anulará.</span><span class="sxs-lookup"><span data-stu-id="87115-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="87115-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="87115-115">Message</span></span>  
 <span data-ttu-id="87115-116">Error al extender la expiración de bloqueo, la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="87115-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="87115-117">Anulando SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="87115-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="87115-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="87115-118">Details</span></span>  
  
|<span data-ttu-id="87115-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="87115-119">Data Item Name</span></span>|<span data-ttu-id="87115-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="87115-120">Data Item Type</span></span>|<span data-ttu-id="87115-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="87115-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="87115-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="87115-122">AppDomain</span></span>|<span data-ttu-id="87115-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="87115-123">xs:string</span></span>|<span data-ttu-id="87115-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="87115-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
