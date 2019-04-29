---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774353"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="055d6-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="055d6-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="055d6-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="055d6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="055d6-104">ID</span><span class="sxs-lookup"><span data-stu-id="055d6-104">ID</span></span>|<span data-ttu-id="055d6-105">4203</span><span class="sxs-lookup"><span data-stu-id="055d6-105">4203</span></span>|  
|<span data-ttu-id="055d6-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="055d6-106">Keywords</span></span>|<span data-ttu-id="055d6-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="055d6-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="055d6-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="055d6-108">Level</span></span>|<span data-ttu-id="055d6-109">Error</span><span class="sxs-lookup"><span data-stu-id="055d6-109">Error</span></span>|  
|<span data-ttu-id="055d6-110">Canal</span><span class="sxs-lookup"><span data-stu-id="055d6-110">Channel</span></span>|<span data-ttu-id="055d6-111">Microsoft-Windows-Application Server-Applications/Debug</span><span class="sxs-lookup"><span data-stu-id="055d6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="055d6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="055d6-112">Description</span></span>  
 <span data-ttu-id="055d6-113">Indica que el proveedor de SQL no ha ampliado la expiración de bloqueo, debido a que la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="055d6-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="055d6-114">SqlWorkflowInstanceStore se anulará.</span><span class="sxs-lookup"><span data-stu-id="055d6-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="055d6-115">Mensaje</span><span class="sxs-lookup"><span data-stu-id="055d6-115">Message</span></span>  
 <span data-ttu-id="055d6-116">Error al extender la expiración de bloqueo, la expiración de bloqueo ya se superó o el propietario de bloqueo se eliminó.</span><span class="sxs-lookup"><span data-stu-id="055d6-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="055d6-117">Anulando SqlWorkflowInstanceStore.</span><span class="sxs-lookup"><span data-stu-id="055d6-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="055d6-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="055d6-118">Details</span></span>  
  
|<span data-ttu-id="055d6-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="055d6-119">Data Item Name</span></span>|<span data-ttu-id="055d6-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="055d6-120">Data Item Type</span></span>|<span data-ttu-id="055d6-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="055d6-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="055d6-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="055d6-122">AppDomain</span></span>|<span data-ttu-id="055d6-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="055d6-123">xs:string</span></span>|<span data-ttu-id="055d6-124">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="055d6-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
