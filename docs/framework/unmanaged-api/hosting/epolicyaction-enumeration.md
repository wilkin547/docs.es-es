---
title: "EPolicyAction (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EPolicyAction
api_location: mscoree.dll
api_type: COM
f1_keywords: EPolicyAction
helpviewer_keywords: EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5de55d46eead37962fad7d7c1c5bd1766e772fe8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="586f9-102">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="586f9-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="586f9-103">Describe las acciones de directiva que el host puede establecer para las operaciones descritas por [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) y los errores descritos por [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="586f9-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="586f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="586f9-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="586f9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="586f9-105">Members</span></span>  
  
|<span data-ttu-id="586f9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="586f9-106">Member</span></span>|<span data-ttu-id="586f9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="586f9-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="586f9-108">Especifica que common language runtime (CLR) debe anular correctamente el subproceso.</span><span class="sxs-lookup"><span data-stu-id="586f9-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="586f9-109">Una anulación correcta incluye intentar ejecutar todos los `finally` bloquea cualquier `catch` bloques relacionados con anulaciones de subprocesos y los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="586f9-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="586f9-110">Especifica que el CLR debe entrar en un estado deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="586f9-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="586f9-111">Ninguna otra se puede ejecutar código administrado en el proceso afectado, y subprocesos bloqueados entren en el CLR.</span><span class="sxs-lookup"><span data-stu-id="586f9-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="586f9-112">Especifica que el CLR debe intentar una salida correcta del proceso, incluidos los finalizadores en ejecución y realizar operaciones de limpieza y el registro.</span><span class="sxs-lookup"><span data-stu-id="586f9-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="586f9-113">Especifica que el CLR debe salir del proceso de inmediato, sin ejecutar los finalizadores ni realizar operaciones de limpieza y el registro.</span><span class="sxs-lookup"><span data-stu-id="586f9-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="586f9-114">Embargo, la notificación se envía al depurador.</span><span class="sxs-lookup"><span data-stu-id="586f9-114">Nowever, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="586f9-115">Especifica que no llevará a cabo ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="586f9-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="586f9-116">Especifica que el CLR debe realizar una anulación de subproceso forzada.</span><span class="sxs-lookup"><span data-stu-id="586f9-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="586f9-117">Solo los `catch` y `finally` los bloques marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="586f9-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="586f9-118">Especifica que el CLR debe salir del proceso sin ejecutar los finalizadores ni las operaciones de registro.</span><span class="sxs-lookup"><span data-stu-id="586f9-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="586f9-119">Especifica que el CLR debe realizar una descarga forzada de la <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="586f9-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="586f9-120">Solo los finalizadores marcan con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="586f9-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="586f9-121">De forma similar, todos los subprocesos con este <xref:System.AppDomain> en su pila reciben un `ThreadAbortException`, sino únicamente aquellas `catch` y `finally` los bloques marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="586f9-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="586f9-122">Especifica que se debe producir una excepción apropiada a la condición, como memoria insuficiente, desbordamiento de búfer y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="586f9-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="586f9-123">Especifica que el <xref:System.AppDomain> debe descargarse.</span><span class="sxs-lookup"><span data-stu-id="586f9-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="586f9-124">El CLR intenta ejecutar los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="586f9-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="586f9-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="586f9-125">Remarks</span></span>  
 <span data-ttu-id="586f9-126">El host establece las acciones de la directiva mediante una llamada a métodos de la [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="586f9-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="586f9-127">Para obtener información sobre las anulaciones forzadas y correctas, vea la [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="586f9-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="586f9-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="586f9-128">Requirements</span></span>  
 <span data-ttu-id="586f9-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="586f9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="586f9-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="586f9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="586f9-131">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="586f9-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="586f9-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="586f9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="586f9-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="586f9-133">See Also</span></span>  
 [<span data-ttu-id="586f9-134">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="586f9-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="586f9-135">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="586f9-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="586f9-136">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="586f9-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="586f9-137">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="586f9-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
