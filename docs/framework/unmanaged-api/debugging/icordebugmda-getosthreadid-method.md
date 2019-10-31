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
ms.openlocfilehash: e9846234f8217b822860c2400a54a91a651a0a56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129825"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="1d7fb-102">ICorDebugMDA::GetOSThreadId (Método)</span><span class="sxs-lookup"><span data-stu-id="1d7fb-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="1d7fb-103">Obtiene el identificador del subproceso del sistema operativo (SO) en el que se ejecuta el Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1d7fb-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d7fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d7fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d7fb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1d7fb-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="1d7fb-106">enuncia Puntero al identificador del subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1d7fb-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d7fb-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1d7fb-107">Remarks</span></span>  
 <span data-ttu-id="1d7fb-108">El subproceso del sistema operativo se usa en lugar de una expresión ICorDebugThread para permitir situaciones en las que se desencadena un MDA en un subproceso nativo o en un subproceso administrado que todavía no ha entrado en código administrado.</span><span class="sxs-lookup"><span data-stu-id="1d7fb-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d7fb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d7fb-109">Requirements</span></span>  
 <span data-ttu-id="1d7fb-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d7fb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d7fb-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d7fb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d7fb-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d7fb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d7fb-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d7fb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d7fb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d7fb-114">See also</span></span>

- [<span data-ttu-id="1d7fb-115">ICorDebugMDA (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d7fb-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="1d7fb-116">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="1d7fb-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
