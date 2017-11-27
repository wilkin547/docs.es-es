---
title: IHostPolicyManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager
helpviewer_keywords: IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8f49474f1a75af91ac5296be866914e05732e755
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="cd46c-102">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd46c-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="cd46c-103">Proporciona métodos que notifican al host de las acciones que common language runtime (CLR) lleva a cabo en caso de anulaciones, tiempos de espera o errores.</span><span class="sxs-lookup"><span data-stu-id="cd46c-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd46c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cd46c-104">Methods</span></span>  
  
|<span data-ttu-id="cd46c-105">Método</span><span class="sxs-lookup"><span data-stu-id="cd46c-105">Method</span></span>|<span data-ttu-id="cd46c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd46c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd46c-107">OnDefaultAction (método)</span><span class="sxs-lookup"><span data-stu-id="cd46c-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="cd46c-108">Notifica al host que CLR está a punto de realizar la acción predeterminada especificada por una llamada a [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) en respuesta a un subproceso anular o <xref:System.AppDomain> descargar.</span><span class="sxs-lookup"><span data-stu-id="cd46c-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="cd46c-109">OnFailure (método)</span><span class="sxs-lookup"><span data-stu-id="cd46c-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="cd46c-110">Notifica al host que CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) en respuesta a una asignación de recursos para el error de recuperación.</span><span class="sxs-lookup"><span data-stu-id="cd46c-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="cd46c-111">OnTimeout (método)</span><span class="sxs-lookup"><span data-stu-id="cd46c-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="cd46c-112">Notifica al host que CLR está a punto de realizar la acción especificada por una llamada a [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="cd46c-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd46c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd46c-113">Requirements</span></span>  
 <span data-ttu-id="cd46c-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd46c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd46c-115">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd46c-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd46c-116">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cd46c-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd46c-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd46c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd46c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd46c-118">See Also</span></span>  
 [<span data-ttu-id="cd46c-119">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="cd46c-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="cd46c-120">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="cd46c-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="cd46c-121">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="cd46c-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="cd46c-122">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd46c-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="cd46c-123">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="cd46c-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
