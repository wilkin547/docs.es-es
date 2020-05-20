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
ms.openlocfilehash: 54748fdeaf911591c21f4495335e54c777878f04
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615844"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="b210d-102">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b210d-102">ICLRControl Interface</span></span>
<span data-ttu-id="b210d-103">Proporciona métodos que permiten a un host obtener referencias y configurar aspectos del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b210d-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b210d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b210d-104">Methods</span></span>  
  
|<span data-ttu-id="b210d-105">Método</span><span class="sxs-lookup"><span data-stu-id="b210d-105">Method</span></span>|<span data-ttu-id="b210d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b210d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b210d-107">Método GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="b210d-107">GetCLRManager Method</span></span>](iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="b210d-108">Obtiene un puntero de interfaz a una instancia de cualquiera de los tipos de administrador que el host puede usar para configurar CLR.</span><span class="sxs-lookup"><span data-stu-id="b210d-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="b210d-109">SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="b210d-109">SetAppDomainManagerType Method</span></span>](iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="b210d-110">Establece un tipo derivado de <xref:System.AppDomainManager> como el tipo para los administradores de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b210d-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b210d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b210d-111">Requirements</span></span>  
 <span data-ttu-id="b210d-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b210d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b210d-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b210d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b210d-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b210d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b210d-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b210d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b210d-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="b210d-116">See also</span></span>

- [<span data-ttu-id="b210d-117">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b210d-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="b210d-118">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b210d-118">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="b210d-119">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b210d-119">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="b210d-120">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b210d-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="b210d-121">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b210d-121">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="b210d-122">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b210d-122">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="b210d-123">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b210d-123">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="b210d-124">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b210d-124">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="b210d-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b210d-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
