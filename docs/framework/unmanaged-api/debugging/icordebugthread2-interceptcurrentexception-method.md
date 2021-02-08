---
description: 'Más información sobre: ICorDebugThread2:: Interceptcurrentexception ((método)'
title: ICorDebugThread2::InterceptCurrentException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
ms.openlocfilehash: 5bf8d3adf6f5e4a24d8fc5abddb72c0c8963c142
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790720"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="f2a9b-103">ICorDebugThread2::InterceptCurrentException (Método)</span><span class="sxs-lookup"><span data-stu-id="f2a9b-103">ICorDebugThread2::InterceptCurrentException Method</span></span>

<span data-ttu-id="f2a9b-104">Permite a un depurador interceptar la excepción actual en este subproceso.</span><span class="sxs-lookup"><span data-stu-id="f2a9b-104">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2a9b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2a9b-105">Syntax</span></span>  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2a9b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2a9b-106">Parameters</span></span>  

 `pFrame`  
 <span data-ttu-id="f2a9b-107">de Puntero a un ICorDebugFrame que representa el marco de pila activo.</span><span class="sxs-lookup"><span data-stu-id="f2a9b-107">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2a9b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f2a9b-108">Remarks</span></span>  

 <span data-ttu-id="f2a9b-109">`InterceptCurrentException`Se puede llamar al método entre una devolución de llamada de excepción ([ICorDebugManagedCallback:: Exception](icordebugmanagedcallback-exception-method.md) o [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md)) y la llamada asociada a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md).</span><span class="sxs-lookup"><span data-stu-id="f2a9b-109">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2a9b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2a9b-110">Requirements</span></span>  

 <span data-ttu-id="f2a9b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2a9b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2a9b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f2a9b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f2a9b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f2a9b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f2a9b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2a9b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
