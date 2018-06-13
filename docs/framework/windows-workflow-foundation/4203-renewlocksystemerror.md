---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513934"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="ea8e9-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="ea8e9-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="ea8e9-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ea8e9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea8e9-104">Id.</span><span class="sxs-lookup"><span data-stu-id="ea8e9-104">ID</span></span>|<span data-ttu-id="ea8e9-105">4203</span><span class="sxs-lookup"><span data-stu-id="ea8e9-105">4203</span></span>|  
|<span data-ttu-id="ea8e9-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ea8e9-106">Keywords</span></span>|<span data-ttu-id="ea8e9-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="ea8e9-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="ea8e9-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="ea8e9-108">Level</span></span>|<span data-ttu-id="ea8e9-109">Error</span><span class="sxs-lookup"><span data-stu-id="ea8e9-109">Error</span></span>|  
|<span data-ttu-id="ea8e9-110">Canal</span><span class="sxs-lookup"><span data-stu-id="ea8e9-110">Channel</span></span>|<span data-ttu-id="ea8e9-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="ea8e9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ea8e9-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea8e9-112">Description</span></span>  
 <span data-ttu-id="ea8e9-113">Indica que el proveedor de SQL no ha ampliado la expiración de bloqueo, debido a que la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="ea8e9-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="ea8e9-114">SqlWorkflowInstanceStore se anulará.</span><span class="sxs-lookup"><span data-stu-id="ea8e9-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ea8e9-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="ea8e9-115">Message</span></span>  
 <span data-ttu-id="ea8e9-116">Error al extender la expiración de bloqueo, la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="ea8e9-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="ea8e9-117">Anulando SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="ea8e9-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ea8e9-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="ea8e9-118">Details</span></span>  
  
|<span data-ttu-id="ea8e9-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ea8e9-119">Data Item Name</span></span>|<span data-ttu-id="ea8e9-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="ea8e9-120">Data Item Type</span></span>|<span data-ttu-id="ea8e9-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea8e9-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ea8e9-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ea8e9-122">AppDomain</span></span>|<span data-ttu-id="ea8e9-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea8e9-123">xs:string</span></span>|<span data-ttu-id="ea8e9-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="ea8e9-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
