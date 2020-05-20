---
title: EPolicyAction (Enumeración)
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: 8788d6e2220778a3f0926d5ed3dd59142487bcca
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616195"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="ca499-102">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ca499-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="ca499-103">Describe las acciones de directiva que el host puede establecer para las operaciones descritas por [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) y los errores descritos por [eclrfailure (](eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="ca499-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca499-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca499-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a><span data-ttu-id="ca499-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ca499-105">Members</span></span>  
  
|<span data-ttu-id="ca499-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ca499-106">Member</span></span>|<span data-ttu-id="ca499-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca499-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="ca499-108">Especifica que el Common Language Runtime (CLR) debe anular correctamente el subproceso.</span><span class="sxs-lookup"><span data-stu-id="ca499-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="ca499-109">Una anulación correcta incluye los intentos de ejecutar todos los `finally` bloques, los `catch` bloques relacionados con las anulaciones de subprocesos y los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="ca499-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="ca499-110">Especifica que CLR debe entrar en un Estado deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="ca499-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="ca499-111">No se puede ejecutar más código administrado en el proceso afectado y se impide que los subprocesos entren en el CLR.</span><span class="sxs-lookup"><span data-stu-id="ca499-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="ca499-112">Especifica que CLR debe intentar una salida correcta del proceso, incluidos los finalizadores en ejecución y la realización de operaciones de limpieza y registro.</span><span class="sxs-lookup"><span data-stu-id="ca499-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="ca499-113">Especifica que CLR debe salir del proceso inmediatamente, sin ejecutar finalizadores ni realizar operaciones de limpieza y registro.</span><span class="sxs-lookup"><span data-stu-id="ca499-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="ca499-114">Sin embargo, se envía una notificación al depurador.</span><span class="sxs-lookup"><span data-stu-id="ca499-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="ca499-115">Especifica que no se debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="ca499-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="ca499-116">Especifica que CLR debe realizar una anulación de subproceso forzada.</span><span class="sxs-lookup"><span data-stu-id="ca499-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="ca499-117">Solo `catch` `finally` se ejecutan los bloques y marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="ca499-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="ca499-118">Especifica que CLR debe salir del proceso sin ejecutar finalizadores ni operaciones de registro.</span><span class="sxs-lookup"><span data-stu-id="ca499-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="ca499-119">Especifica que CLR debe realizar una descarga forzada de <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="ca499-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="ca499-120">Solo se ejecutan los finalizadores marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .</span><span class="sxs-lookup"><span data-stu-id="ca499-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="ca499-121">De forma similar, todos los subprocesos con este <xref:System.AppDomain> en su pila reciben `ThreadAbortException` , pero solo `catch` `finally` <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan los bloques y marcados con.</span><span class="sxs-lookup"><span data-stu-id="ca499-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="ca499-122">Especifica que debe producirse una excepción adecuada a la condición, como memoria insuficiente, desbordamiento del búfer, etc.</span><span class="sxs-lookup"><span data-stu-id="ca499-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="ca499-123">Especifica que <xref:System.AppDomain> se debe descargar.</span><span class="sxs-lookup"><span data-stu-id="ca499-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="ca499-124">CLR intenta ejecutar los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="ca499-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca499-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ca499-125">Remarks</span></span>  
 <span data-ttu-id="ca499-126">El host establece las acciones de Directiva mediante una llamada a los métodos de la interfaz [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ca499-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="ca499-127">Para obtener información sobre las anulaciones superficiales y correctas, vea la enumeración [EClrOperation](eclroperation-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ca499-127">For information about rude and graceful aborts, see the [EClrOperation](eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca499-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca499-128">Requirements</span></span>  
 <span data-ttu-id="ca499-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca499-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca499-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ca499-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca499-131">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ca499-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca499-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca499-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca499-133">Consulta también</span><span class="sxs-lookup"><span data-stu-id="ca499-133">See also</span></span>

- [<span data-ttu-id="ca499-134">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ca499-134">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="ca499-135">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca499-135">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="ca499-136">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca499-136">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="ca499-137">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="ca499-137">Hosting Enumerations</span></span>](hosting-enumerations.md)
