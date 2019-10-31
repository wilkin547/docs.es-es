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
ms.openlocfilehash: 6ba7b7adc104db528293d77c3591370c6ce02c25
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128599"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="704ae-102">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="704ae-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="704ae-103">Proporciona métodos que envían una notificación al host de las acciones que realiza el Common Language Runtime (CLR) en caso de anulaciones, tiempos de espera o errores.</span><span class="sxs-lookup"><span data-stu-id="704ae-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="704ae-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="704ae-104">Methods</span></span>  
  
|<span data-ttu-id="704ae-105">Método</span><span class="sxs-lookup"><span data-stu-id="704ae-105">Method</span></span>|<span data-ttu-id="704ae-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="704ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="704ae-107">OnDefaultAction (método)</span><span class="sxs-lookup"><span data-stu-id="704ae-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="704ae-108">Notifica al host que CLR está a punto de realizar la acción predeterminada especificada por una llamada a [ICLRPolicyManager:: SetDefaultAction (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) en respuesta a una anulación del subproceso o <xref:System.AppDomain> descarga.</span><span class="sxs-lookup"><span data-stu-id="704ae-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="704ae-109">OnFailure (método)</span><span class="sxs-lookup"><span data-stu-id="704ae-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="704ae-110">Notifica al host que CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: setactiononfailure (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) en respuesta a un error de asignación de recursos o de recorte.</span><span class="sxs-lookup"><span data-stu-id="704ae-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="704ae-111">OnTimeout (método)</span><span class="sxs-lookup"><span data-stu-id="704ae-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="704ae-112">Notifica al host que el CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: SetActionOnTimeout (](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="704ae-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="704ae-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="704ae-113">Requirements</span></span>  
 <span data-ttu-id="704ae-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="704ae-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="704ae-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="704ae-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="704ae-116">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="704ae-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="704ae-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="704ae-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704ae-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="704ae-118">See also</span></span>

- [<span data-ttu-id="704ae-119">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="704ae-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="704ae-120">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="704ae-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="704ae-121">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="704ae-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="704ae-122">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="704ae-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="704ae-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="704ae-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
