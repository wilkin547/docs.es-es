---
title: ICLRControl (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a06c1f4e1fcfe9c9c361a0e0bb2e8722577a13b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432900"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="708d0-102">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="708d0-102">ICLRControl Interface</span></span>
<span data-ttu-id="708d0-103">Proporciona métodos que permiten a un host obtener referencias a y configurar aspectos de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="708d0-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="708d0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="708d0-104">Methods</span></span>  
  
|<span data-ttu-id="708d0-105">Método</span><span class="sxs-lookup"><span data-stu-id="708d0-105">Method</span></span>|<span data-ttu-id="708d0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="708d0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="708d0-107">GetCLRManager (método)</span><span class="sxs-lookup"><span data-stu-id="708d0-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="708d0-108">Obtiene un puntero de interfaz a una instancia de cualquiera de los tipos de administrador que el host puede utilizar para configurar el CLR.</span><span class="sxs-lookup"><span data-stu-id="708d0-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="708d0-109">SetAppDomainManagerType (método)</span><span class="sxs-lookup"><span data-stu-id="708d0-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="708d0-110">Establece un tipo derivado de <xref:System.AppDomainManager> como el tipo para los administradores de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="708d0-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="708d0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="708d0-111">Requirements</span></span>  
 <span data-ttu-id="708d0-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="708d0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="708d0-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="708d0-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="708d0-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="708d0-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="708d0-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="708d0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="708d0-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="708d0-116">See Also</span></span>  
 [<span data-ttu-id="708d0-117">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="708d0-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="708d0-118">ICLRDebugManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="708d0-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="708d0-119">ICLRGCManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="708d0-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="708d0-120">ICLRHostBindingPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="708d0-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="708d0-121">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="708d0-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="708d0-122">ICLROnEventManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="708d0-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="708d0-123">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="708d0-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="708d0-124">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="708d0-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="708d0-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="708d0-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
