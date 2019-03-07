---
title: ICorDebugMDA::GetOSThreadId (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c38aa9cc891514a7f37dba47402c168060ec3727
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486100"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="dc34a-102">ICorDebugMDA::GetOSThreadId (Método)</span><span class="sxs-lookup"><span data-stu-id="dc34a-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="dc34a-103">Obtiene el identificador del subproceso del sistema operativo (SO) en el que el Asistente para depuración administrada (MDA) representado por [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="dc34a-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc34a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc34a-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc34a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc34a-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="dc34a-106">[out] Un puntero al identificador de subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="dc34a-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc34a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc34a-107">Remarks</span></span>  
 <span data-ttu-id="dc34a-108">El subproceso de sistema operativo se usa en lugar de un ICorDebugThread para permitir situaciones en que se desencadena un MDA en un subproceso nativo o en un subproceso administrado que aún no ha entrado código administrado.</span><span class="sxs-lookup"><span data-stu-id="dc34a-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc34a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc34a-109">Requirements</span></span>  
 <span data-ttu-id="dc34a-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc34a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc34a-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc34a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc34a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc34a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc34a-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc34a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc34a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc34a-114">See also</span></span>
- [<span data-ttu-id="dc34a-115">ICorDebugMDA (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc34a-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="dc34a-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="dc34a-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
