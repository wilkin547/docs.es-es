---
description: 'Más información acerca de: ICorDebugMDA:: Getosthreadid ((método)'
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
ms.openlocfilehash: f965585a6e6060a14f0cbc2a80b46124b2751e0e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801155"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="43bf7-103">ICorDebugMDA::GetOSThreadId (Método)</span><span class="sxs-lookup"><span data-stu-id="43bf7-103">ICorDebugMDA::GetOSThreadId Method</span></span>

<span data-ttu-id="43bf7-104">Obtiene el identificador del subproceso del sistema operativo (SO) en el que se ejecuta el Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="43bf7-104">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43bf7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43bf7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43bf7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43bf7-106">Parameters</span></span>  

 `pOsTid`  
 <span data-ttu-id="43bf7-107">enuncia Puntero al identificador del subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="43bf7-107">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43bf7-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="43bf7-108">Remarks</span></span>  

 <span data-ttu-id="43bf7-109">El subproceso del sistema operativo se usa en lugar de una expresión ICorDebugThread para permitir situaciones en las que se desencadena un MDA en un subproceso nativo o en un subproceso administrado que todavía no ha entrado en código administrado.</span><span class="sxs-lookup"><span data-stu-id="43bf7-109">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43bf7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43bf7-110">Requirements</span></span>  

 <span data-ttu-id="43bf7-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43bf7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43bf7-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43bf7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43bf7-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43bf7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43bf7-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43bf7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43bf7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="43bf7-115">See also</span></span>

- [<span data-ttu-id="43bf7-116">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="43bf7-116">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="43bf7-117">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="43bf7-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
