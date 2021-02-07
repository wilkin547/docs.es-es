---
description: 'Más información acerca de: interfaz IHostPolicyManager'
title: IHostPolicyManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: d823ee2526019188afd17df903b61a720e18207f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671937"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="75820-103">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="75820-103">IHostPolicyManager Interface</span></span>

<span data-ttu-id="75820-104">Proporciona métodos que envían una notificación al host de las acciones que realiza el Common Language Runtime (CLR) en caso de anulaciones, tiempos de espera o errores.</span><span class="sxs-lookup"><span data-stu-id="75820-104">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="75820-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="75820-105">Methods</span></span>  
  
|<span data-ttu-id="75820-106">Método</span><span class="sxs-lookup"><span data-stu-id="75820-106">Method</span></span>|<span data-ttu-id="75820-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="75820-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="75820-108">Método OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="75820-108">OnDefaultAction Method</span></span>](ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="75820-109">Notifica al host que CLR está a punto de realizar la acción predeterminada especificada por una llamada a [ICLRPolicyManager:: SetDefaultAction (](iclrpolicymanager-setdefaultaction-method.md) en respuesta a una anulación o descarga del subproceso <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="75820-109">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="75820-110">Método OnFailure</span><span class="sxs-lookup"><span data-stu-id="75820-110">OnFailure Method</span></span>](ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="75820-111">Notifica al host que CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: setactiononfailure (](iclrpolicymanager-setactiononfailure-method.md) en respuesta a un error de asignación de recursos o de recorte.</span><span class="sxs-lookup"><span data-stu-id="75820-111">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="75820-112">Método OnTimeout</span><span class="sxs-lookup"><span data-stu-id="75820-112">OnTimeout Method</span></span>](ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="75820-113">Notifica al host que el CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: SetActionOnTimeout (](iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="75820-113">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="75820-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75820-114">Requirements</span></span>  

 <span data-ttu-id="75820-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75820-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75820-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="75820-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="75820-117">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="75820-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75820-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75820-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75820-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="75820-119">See also</span></span>

- [<span data-ttu-id="75820-120">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="75820-120">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="75820-121">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="75820-121">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="75820-122">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="75820-122">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="75820-123">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="75820-123">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="75820-124">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="75820-124">Hosting Interfaces</span></span>](hosting-interfaces.md)
