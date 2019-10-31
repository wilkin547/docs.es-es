---
title: ICorDebugThread4::HadUnhandledException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
ms.openlocfilehash: d9f0eff35dbe0058398d2d1c851ef85effa9cd28
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122421"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="d86d0-102">ICorDebugThread4::HadUnhandledException (Método)</span><span class="sxs-lookup"><span data-stu-id="d86d0-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="d86d0-103">Indica si el subproceso ha tenido alguna vez una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="d86d0-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d86d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d86d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d86d0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d86d0-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="d86d0-106">enuncia Puntero a la dirección de una enumeración ordenada de estructuras [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="d86d0-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d86d0-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d86d0-107">Return Value</span></span>  
 <span data-ttu-id="d86d0-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="d86d0-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d86d0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d86d0-109">HRESULT</span></span>|<span data-ttu-id="d86d0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d86d0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d86d0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d86d0-111">S_OK</span></span>|<span data-ttu-id="d86d0-112">El subproceso ha tenido una excepción no controlada desde su creación.</span><span class="sxs-lookup"><span data-stu-id="d86d0-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="d86d0-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d86d0-113">S_FALSE</span></span>|<span data-ttu-id="d86d0-114">El subproceso nunca ha tenido una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="d86d0-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d86d0-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d86d0-115">Remarks</span></span>  
 <span data-ttu-id="d86d0-116">Este método indica si el subproceso ha tenido alguna vez una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="d86d0-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="d86d0-117">En el momento en que se desencadena la devolución de llamada de excepción no controlada o se inicia la Asociación JIT nativa, se garantiza que este método devuelve S_OK.</span><span class="sxs-lookup"><span data-stu-id="d86d0-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="d86d0-118">No hay ninguna garantía de que el método [ICorDebugThread. GetCurrentException (](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) devuelva la excepción no controlada. sin embargo, si el proceso aún no se ha continuado después de obtener la devolución de llamada de excepción no controlada o después de la Asociación JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="d86d0-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="d86d0-119">Además, es posible (aunque improbable) tener más de un subproceso con una excepción no controlada en el momento en que se desencadena la Asociación JIT nativa.</span><span class="sxs-lookup"><span data-stu-id="d86d0-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="d86d0-120">En tal caso, no hay ninguna manera de determinar qué excepción desencadenó la Asociación JIT.</span><span class="sxs-lookup"><span data-stu-id="d86d0-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d86d0-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d86d0-121">Requirements</span></span>  
 <span data-ttu-id="d86d0-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d86d0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d86d0-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d86d0-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d86d0-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d86d0-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d86d0-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d86d0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d86d0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d86d0-126">See also</span></span>

- [<span data-ttu-id="d86d0-127">ICorDebugThread4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d86d0-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="d86d0-128">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d86d0-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d86d0-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="d86d0-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
