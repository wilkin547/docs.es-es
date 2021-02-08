---
description: 'Más información sobre: enumeración Eclrfailure ('
title: EClrFailure (Enumeración)
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
ms.openlocfilehash: 9f3a2270651e5b05d2d31ed90511b8eb05dd4d44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785593"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="81dc8-103">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="81dc8-103">EClrFailure Enumeration</span></span>

<span data-ttu-id="81dc8-104">Describe el conjunto de errores para los que un host puede establecer acciones de directiva.</span><span class="sxs-lookup"><span data-stu-id="81dc8-104">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81dc8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81dc8-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="81dc8-106">Members</span><span class="sxs-lookup"><span data-stu-id="81dc8-106">Members</span></span>  
  
|<span data-ttu-id="81dc8-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="81dc8-107">Member</span></span>|<span data-ttu-id="81dc8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="81dc8-108">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="81dc8-109">Se produjo un error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región de código que no es crítica.</span><span class="sxs-lookup"><span data-stu-id="81dc8-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="81dc8-110">Se produjo un error al intentar asignar un recurso (por ejemplo, un subproceso, un bloque de memoria o un bloqueo) en una región crítica de código.</span><span class="sxs-lookup"><span data-stu-id="81dc8-110">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="81dc8-111">El Common Language Runtime (CLR) ya no puede ejecutar código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="81dc8-111">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="81dc8-112">En adelante, las llamadas a las funciones de hospedaje devuelven un valor HRESULT de HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="81dc8-112">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="81dc8-113">Un subproceso no pudo liberar un bloqueo al devolver un <xref:System.AppDomain> objeto.</span><span class="sxs-lookup"><span data-stu-id="81dc8-113">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="81dc8-114">El host no puede establecer este error para hacer que un subproceso se anule.</span><span class="sxs-lookup"><span data-stu-id="81dc8-114">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="81dc8-115">Se ha producido un desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="81dc8-115">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="81dc8-116">Se intentó leer o escribir en la memoria protegida.</span><span class="sxs-lookup"><span data-stu-id="81dc8-116">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="81dc8-117">No se admite en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="81dc8-117">Not supported in the .NET Framework 4.</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="81dc8-118">Error de contrato de código.</span><span class="sxs-lookup"><span data-stu-id="81dc8-118">A code contract failure occurred.</span></span> <span data-ttu-id="81dc8-119">Vea [contratos de código](../../debug-trace-profile/code-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="81dc8-119">See [Code Contracts](../../debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81dc8-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="81dc8-120">Remarks</span></span>  

 <span data-ttu-id="81dc8-121">Vea el método [ICLRPolicyManager:: setactiononfailure (](iclrpolicymanager-setactiononfailure-method.md) para obtener una lista de los valores de [EPolicyAction](epolicyaction-enumeration.md) que el host puede usar para especificar las acciones de directiva para las condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="81dc8-121">See the [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="81dc8-122">Para obtener más información sobre las regiones críticas y no críticas de código, vea [EClrOperation](eclroperation-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="81dc8-122">For more information about critical and non-critical regions of code, see [EClrOperation](eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81dc8-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81dc8-123">Requirements</span></span>  

 <span data-ttu-id="81dc8-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81dc8-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81dc8-125">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="81dc8-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="81dc8-126">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="81dc8-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="81dc8-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81dc8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81dc8-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="81dc8-128">See also</span></span>

- [<span data-ttu-id="81dc8-129">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81dc8-129">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="81dc8-130">Método SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="81dc8-130">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)
- [<span data-ttu-id="81dc8-131">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81dc8-131">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="81dc8-132">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="81dc8-132">Hosting Enumerations</span></span>](hosting-enumerations.md)
