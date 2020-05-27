---
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
ms.openlocfilehash: db089a55128fa675ceedf157b046fe205d8c6b51
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804336"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="bf40e-102">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf40e-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="bf40e-103">Proporciona métodos que envían una notificación al host de las acciones que realiza el Common Language Runtime (CLR) en caso de anulaciones, tiempos de espera o errores.</span><span class="sxs-lookup"><span data-stu-id="bf40e-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf40e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bf40e-104">Methods</span></span>  
  
|<span data-ttu-id="bf40e-105">Método</span><span class="sxs-lookup"><span data-stu-id="bf40e-105">Method</span></span>|<span data-ttu-id="bf40e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf40e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf40e-107">Método OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="bf40e-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="bf40e-108">Notifica al host que CLR está a punto de realizar la acción predeterminada especificada por una llamada a [ICLRPolicyManager:: SetDefaultAction (](iclrpolicymanager-setdefaultaction-method.md) en respuesta a una anulación o descarga del subproceso <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="bf40e-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="bf40e-109">Método OnFailure</span><span class="sxs-lookup"><span data-stu-id="bf40e-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="bf40e-110">Notifica al host que CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: setactiononfailure (](iclrpolicymanager-setactiononfailure-method.md) en respuesta a un error de asignación de recursos o de recorte.</span><span class="sxs-lookup"><span data-stu-id="bf40e-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="bf40e-111">Método OnTimeout</span><span class="sxs-lookup"><span data-stu-id="bf40e-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="bf40e-112">Notifica al host que el CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: SetActionOnTimeout (](iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="bf40e-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf40e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf40e-113">Requirements</span></span>  
 <span data-ttu-id="bf40e-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf40e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf40e-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bf40e-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bf40e-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bf40e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf40e-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf40e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf40e-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf40e-118">See also</span></span>

- [<span data-ttu-id="bf40e-119">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="bf40e-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="bf40e-120">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="bf40e-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="bf40e-121">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="bf40e-121">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="bf40e-122">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf40e-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="bf40e-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="bf40e-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
