---
description: 'Más información acerca de: ICLRControl (interfaz)'
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
ms.openlocfilehash: e108506d06b746d631f4c15c37d467399de30aba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637669"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="591ba-103">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="591ba-103">ICLRControl Interface</span></span>

<span data-ttu-id="591ba-104">Proporciona métodos que permiten a un host obtener referencias y configurar aspectos del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="591ba-104">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="591ba-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="591ba-105">Methods</span></span>  
  
|<span data-ttu-id="591ba-106">Método</span><span class="sxs-lookup"><span data-stu-id="591ba-106">Method</span></span>|<span data-ttu-id="591ba-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="591ba-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="591ba-108">Método GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="591ba-108">GetCLRManager Method</span></span>](iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="591ba-109">Obtiene un puntero de interfaz a una instancia de cualquiera de los tipos de administrador que el host puede usar para configurar CLR.</span><span class="sxs-lookup"><span data-stu-id="591ba-109">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="591ba-110">SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="591ba-110">SetAppDomainManagerType Method</span></span>](iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="591ba-111">Establece un tipo derivado de <xref:System.AppDomainManager> como el tipo para los administradores de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="591ba-111">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="591ba-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="591ba-112">Requirements</span></span>  

 <span data-ttu-id="591ba-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="591ba-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="591ba-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="591ba-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="591ba-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="591ba-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="591ba-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="591ba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="591ba-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="591ba-117">See also</span></span>

- [<span data-ttu-id="591ba-118">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="591ba-118">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="591ba-119">ICLRDebugManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="591ba-119">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="591ba-120">ICLRGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="591ba-120">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="591ba-121">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="591ba-121">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="591ba-122">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="591ba-122">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="591ba-123">ICLROnEventManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="591ba-123">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="591ba-124">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="591ba-124">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="591ba-125">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="591ba-125">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="591ba-126">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="591ba-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
