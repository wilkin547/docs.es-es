---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 17617e25c5cf8cecae608438529e9ce1a7d506f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251274"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="6e088-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="6e088-102">4203 - RenewLockSystemError</span></span>

## <a name="properties"></a><span data-ttu-id="6e088-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6e088-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6e088-104">ID</span><span class="sxs-lookup"><span data-stu-id="6e088-104">ID</span></span>|<span data-ttu-id="6e088-105">4203</span><span class="sxs-lookup"><span data-stu-id="6e088-105">4203</span></span>|  
|<span data-ttu-id="6e088-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6e088-106">Keywords</span></span>|<span data-ttu-id="6e088-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="6e088-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="6e088-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="6e088-108">Level</span></span>|<span data-ttu-id="6e088-109">Error</span><span class="sxs-lookup"><span data-stu-id="6e088-109">Error</span></span>|  
|<span data-ttu-id="6e088-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6e088-110">Channel</span></span>|<span data-ttu-id="6e088-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="6e088-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6e088-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e088-112">Description</span></span>  

 <span data-ttu-id="6e088-113">Indica que el proveedor de SQL no ha ampliado la expiración de bloqueo, debido a que la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="6e088-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="6e088-114">SqlWorkflowInstanceStore se anulará.</span><span class="sxs-lookup"><span data-stu-id="6e088-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6e088-115">Message</span><span class="sxs-lookup"><span data-stu-id="6e088-115">Message</span></span>  

 <span data-ttu-id="6e088-116">Error al extender la expiración de bloqueo, la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="6e088-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="6e088-117">Anulando SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="6e088-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6e088-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="6e088-118">Details</span></span>  
  
|<span data-ttu-id="6e088-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6e088-119">Data Item Name</span></span>|<span data-ttu-id="6e088-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6e088-120">Data Item Type</span></span>|<span data-ttu-id="6e088-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e088-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6e088-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6e088-122">AppDomain</span></span>|<span data-ttu-id="6e088-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="6e088-123">xs:string</span></span>|<span data-ttu-id="6e088-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6e088-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
