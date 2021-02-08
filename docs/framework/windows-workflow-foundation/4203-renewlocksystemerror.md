---
description: 'Más información acerca de: 4203-RenewLockSystemError'
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 0e62c501391fcaec56f2016631707832170775ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792783"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="2bd20-103">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="2bd20-103">4203 - RenewLockSystemError</span></span>

## <a name="properties"></a><span data-ttu-id="2bd20-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2bd20-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2bd20-105">Id.</span><span class="sxs-lookup"><span data-stu-id="2bd20-105">ID</span></span>|<span data-ttu-id="2bd20-106">4203</span><span class="sxs-lookup"><span data-stu-id="2bd20-106">4203</span></span>|  
|<span data-ttu-id="2bd20-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2bd20-107">Keywords</span></span>|<span data-ttu-id="2bd20-108">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="2bd20-108">WFInstanceStore</span></span>|  
|<span data-ttu-id="2bd20-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="2bd20-109">Level</span></span>|<span data-ttu-id="2bd20-110">Error</span><span class="sxs-lookup"><span data-stu-id="2bd20-110">Error</span></span>|  
|<span data-ttu-id="2bd20-111">Canal</span><span class="sxs-lookup"><span data-stu-id="2bd20-111">Channel</span></span>|<span data-ttu-id="2bd20-112">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="2bd20-112">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2bd20-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bd20-113">Description</span></span>  

 <span data-ttu-id="2bd20-114">Indica que el proveedor de SQL no ha ampliado la expiración de bloqueo, debido a que la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="2bd20-114">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="2bd20-115">SqlWorkflowInstanceStore se anulará.</span><span class="sxs-lookup"><span data-stu-id="2bd20-115">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2bd20-116">Message</span><span class="sxs-lookup"><span data-stu-id="2bd20-116">Message</span></span>  

 <span data-ttu-id="2bd20-117">Error al extender la expiración de bloqueo, la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="2bd20-117">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="2bd20-118">Anulando SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="2bd20-118">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2bd20-119">Detalles</span><span class="sxs-lookup"><span data-stu-id="2bd20-119">Details</span></span>  
  
|<span data-ttu-id="2bd20-120">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2bd20-120">Data Item Name</span></span>|<span data-ttu-id="2bd20-121">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2bd20-121">Data Item Type</span></span>|<span data-ttu-id="2bd20-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bd20-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2bd20-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2bd20-123">AppDomain</span></span>|<span data-ttu-id="2bd20-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2bd20-124">xs:string</span></span>|<span data-ttu-id="2bd20-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2bd20-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
