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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75bd7da67cbac958f0b34c8295454a719962c7ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201733"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="46d82-102">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="46d82-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="46d82-103">Describe las acciones de directiva, el host puede establecer para las operaciones descritas por [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) y los errores descritos por [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="46d82-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46d82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46d82-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="46d82-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="46d82-105">Members</span></span>  
  
|<span data-ttu-id="46d82-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="46d82-106">Member</span></span>|<span data-ttu-id="46d82-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="46d82-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="46d82-108">Especifica que common language runtime (CLR) debe anular correctamente el subproceso.</span><span class="sxs-lookup"><span data-stu-id="46d82-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="46d82-109">Una anulación correcta incluye intentos de ejecutar todo `finally` bloquea cualquier `catch` bloques relacionados con las anulaciones de subproceso y los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="46d82-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="46d82-110">Especifica que el CLR debe entrar en un estado deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="46d82-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="46d82-111">No se puede ejecutar código administrado en el proceso afectado y subprocesos se bloquean entre en CLR.</span><span class="sxs-lookup"><span data-stu-id="46d82-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="46d82-112">Especifica que el CLR debe intentar una salida correcta del proceso, incluidos los finalizadores en ejecución y realizar operaciones de limpieza y registro.</span><span class="sxs-lookup"><span data-stu-id="46d82-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="46d82-113">Especifica que el CLR debe salir del proceso inmediatamente, sin ejecutar los finalizadores ni realizar operaciones de limpieza y registro.</span><span class="sxs-lookup"><span data-stu-id="46d82-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="46d82-114">Sin embargo, se envía una notificación al depurador.</span><span class="sxs-lookup"><span data-stu-id="46d82-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="46d82-115">Especifica que no se debe tomar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="46d82-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="46d82-116">Especifica que el CLR debe realizar una anulación a la fuerza.</span><span class="sxs-lookup"><span data-stu-id="46d82-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="46d82-117">Solo los `catch` y `finally` los bloques marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="46d82-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="46d82-118">Especifica que el CLR debe salir del proceso sin ejecutar los finalizadores ni registrar las operaciones.</span><span class="sxs-lookup"><span data-stu-id="46d82-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="46d82-119">Especifica que el CLR debe realizar una descarga forzada de la <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="46d82-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="46d82-120">Los finalizadores de sólo marcan con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="46d82-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="46d82-121">De forma similar, todos los subprocesos con este <xref:System.AppDomain> en su pila recibir un `ThreadAbortException`, sino solamente aquello `catch` y `finally` los bloques marcados con <xref:System.EnterpriseServices.MustRunInClientContextAttribute> se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="46d82-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="46d82-122">Especifica que debe iniciará una excepción correspondiente a la condición, por ejemplo, de memoria insuficiente, desbordamiento del búfer y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="46d82-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="46d82-123">Especifica que el <xref:System.AppDomain> debe descargarse.</span><span class="sxs-lookup"><span data-stu-id="46d82-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="46d82-124">El CLR intenta ejecutar los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="46d82-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46d82-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46d82-125">Remarks</span></span>  
 <span data-ttu-id="46d82-126">El host establece las acciones de directiva mediante una llamada a métodos de la [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="46d82-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="46d82-127">Para obtener información sobre las anulaciones a la fuerza y estables, consulte el [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="46d82-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46d82-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46d82-128">Requirements</span></span>  
 <span data-ttu-id="46d82-129">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46d82-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46d82-130">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="46d82-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46d82-131">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46d82-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="46d82-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46d82-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d82-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="46d82-133">See also</span></span>

- [<span data-ttu-id="46d82-134">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="46d82-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="46d82-135">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46d82-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="46d82-136">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="46d82-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="46d82-137">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="46d82-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
