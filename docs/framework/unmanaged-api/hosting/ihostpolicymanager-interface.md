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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9d903b4e44ea7a185ad8b3b71b7a5da2f2bda3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126352"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="0c654-102">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c654-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="0c654-103">Proporciona métodos que notifican al host de las acciones que realiza el common language runtime (CLR) en caso de anulaciones, tiempos de espera o errores.</span><span class="sxs-lookup"><span data-stu-id="0c654-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c654-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0c654-104">Methods</span></span>  
  
|<span data-ttu-id="0c654-105">Método</span><span class="sxs-lookup"><span data-stu-id="0c654-105">Method</span></span>|<span data-ttu-id="0c654-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c654-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c654-107">Método OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="0c654-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="0c654-108">Notifica al host que CLR está a punto de realizar la acción predeterminada especificada por una llamada a [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) en respuesta a un subproceso anular o <xref:System.AppDomain> descargar.</span><span class="sxs-lookup"><span data-stu-id="0c654-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="0c654-109">Método OnFailure</span><span class="sxs-lookup"><span data-stu-id="0c654-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="0c654-110">Notifica al host que CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) en respuesta a un error de recuperación o la asignación de recursos.</span><span class="sxs-lookup"><span data-stu-id="0c654-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="0c654-111">Método OnTimeout</span><span class="sxs-lookup"><span data-stu-id="0c654-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="0c654-112">Notifica al host que CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="0c654-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c654-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c654-113">Requirements</span></span>  
 <span data-ttu-id="0c654-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c654-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c654-115">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c654-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c654-116">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c654-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0c654-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0c654-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c654-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c654-118">See also</span></span>

- [<span data-ttu-id="0c654-119">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0c654-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="0c654-120">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0c654-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="0c654-121">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0c654-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="0c654-122">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c654-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="0c654-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="0c654-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
