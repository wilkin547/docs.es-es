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
ms.workload: dotnet
ms.openlocfilehash: 8fabe6f2c023bf9b997d2a4e19b4a3755c93f408
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="03870-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="03870-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="03870-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="03870-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="03870-104">Id.</span><span class="sxs-lookup"><span data-stu-id="03870-104">ID</span></span>|<span data-ttu-id="03870-105">4203</span><span class="sxs-lookup"><span data-stu-id="03870-105">4203</span></span>|  
|<span data-ttu-id="03870-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="03870-106">Keywords</span></span>|<span data-ttu-id="03870-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="03870-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="03870-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="03870-108">Level</span></span>|<span data-ttu-id="03870-109">Error</span><span class="sxs-lookup"><span data-stu-id="03870-109">Error</span></span>|  
|<span data-ttu-id="03870-110">Canal</span><span class="sxs-lookup"><span data-stu-id="03870-110">Channel</span></span>|<span data-ttu-id="03870-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="03870-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="03870-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="03870-112">Description</span></span>  
 <span data-ttu-id="03870-113">Indica que el proveedor de SQL no ha ampliado la expiración de bloqueo, debido a que la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="03870-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="03870-114">SqlWorkflowInstanceStore se anulará.</span><span class="sxs-lookup"><span data-stu-id="03870-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="03870-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="03870-115">Message</span></span>  
 <span data-ttu-id="03870-116">Error al extender la expiración de bloqueo, la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="03870-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="03870-117">Anulando SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="03870-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="03870-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="03870-118">Details</span></span>  
  
|<span data-ttu-id="03870-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="03870-119">Data Item Name</span></span>|<span data-ttu-id="03870-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="03870-120">Data Item Type</span></span>|<span data-ttu-id="03870-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="03870-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="03870-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="03870-122">AppDomain</span></span>|<span data-ttu-id="03870-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="03870-123">xs:string</span></span>|<span data-ttu-id="03870-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="03870-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
