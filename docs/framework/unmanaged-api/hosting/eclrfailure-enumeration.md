---
title: "EClrFailure (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrFailure
helpviewer_keywords: EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 94358fd0626fa17f1fd6d3c365aff79f89dde467
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="13cb3-102">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="13cb3-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="13cb3-103">Describe el conjunto de errores para los que un host puede establecer acciones de la directiva.</span><span class="sxs-lookup"><span data-stu-id="13cb3-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13cb3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13cb3-104">Syntax</span></span>  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a><span data-ttu-id="13cb3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="13cb3-105">Members</span></span>  
  
|<span data-ttu-id="13cb3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="13cb3-106">Member</span></span>|<span data-ttu-id="13cb3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="13cb3-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="13cb3-108">Se produjo un error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región no crítica del código.</span><span class="sxs-lookup"><span data-stu-id="13cb3-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="13cb3-109">Se produjo un error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región crítica del código.</span><span class="sxs-lookup"><span data-stu-id="13cb3-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="13cb3-110">Common language runtime (CLR) ya no es capaz de ejecutar código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="13cb3-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="13cb3-111">Ahora en adelante, las llamadas a funciones de hospedaje devuelven un valor HRESULT de HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="13cb3-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="13cb3-112">Un subproceso no pudo liberar un bloqueo al volver de un <xref:System.AppDomain> objeto.</span><span class="sxs-lookup"><span data-stu-id="13cb3-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="13cb3-113">El host no puede establecer este error para hacer que un subproceso anular la operación.</span><span class="sxs-lookup"><span data-stu-id="13cb3-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="13cb3-114">Se ha producido un desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="13cb3-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="13cb3-115">Se intentó leer o escribir en la memoria protegida.</span><span class="sxs-lookup"><span data-stu-id="13cb3-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="13cb3-116">No se admite en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13cb3-116">Not supported in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="13cb3-117">Se produjo un error de contrato de código.</span><span class="sxs-lookup"><span data-stu-id="13cb3-117">A code contract failure occurred.</span></span> <span data-ttu-id="13cb3-118">Vea [contratos de código](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="13cb3-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13cb3-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13cb3-119">Remarks</span></span>  
 <span data-ttu-id="13cb3-120">Consulte la [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) método para obtener una lista de [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores que el host puede utilizar para especificar las acciones de directiva para condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="13cb3-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="13cb3-121">Para obtener más información acerca de las regiones críticas y no críticas de código, vea [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="13cb3-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13cb3-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13cb3-122">Requirements</span></span>  
 <span data-ttu-id="13cb3-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13cb3-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13cb3-124">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="13cb3-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13cb3-125">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13cb3-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13cb3-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13cb3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13cb3-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="13cb3-127">See Also</span></span>  
 [<span data-ttu-id="13cb3-128">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13cb3-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="13cb3-129">SetActionOnFailure (método)</span><span class="sxs-lookup"><span data-stu-id="13cb3-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [<span data-ttu-id="13cb3-130">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13cb3-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="13cb3-131">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="13cb3-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
