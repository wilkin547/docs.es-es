---
title: ICorDebugStackWalk::GetFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetFrame
helpviewer_keywords:
- GetFrame method [.NET Framework debugging]
- ICorDebugStackWalk::GetFrame method [.NET Framework debugging]
ms.assetid: 4083b505-5b59-44fb-8c5d-129db6a96c10
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 253a25fdfc1f00adbc20388660caf6c227030a1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111246"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="4ae74-102">ICorDebugStackWalk::GetFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="4ae74-102">ICorDebugStackWalk::GetFrame Method</span></span>
<span data-ttu-id="4ae74-103">Obtiene el marco actual el [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="4ae74-103">Gets the current frame in the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ae74-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ae74-104">Syntax</span></span>  
  
```  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ae74-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ae74-105">Parameters</span></span>  
 `pFrame`  
 <span data-ttu-id="4ae74-106">[in] Un puntero a la dirección del objeto de marco creado que representa el fotograma actual en la pila.</span><span class="sxs-lookup"><span data-stu-id="4ae74-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4ae74-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4ae74-107">Return Value</span></span>  
 <span data-ttu-id="4ae74-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="4ae74-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4ae74-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ae74-109">HRESULT</span></span>|<span data-ttu-id="4ae74-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ae74-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ae74-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ae74-111">S_OK</span></span>|<span data-ttu-id="4ae74-112">El tiempo de ejecución devolvió el marco actual.</span><span class="sxs-lookup"><span data-stu-id="4ae74-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="4ae74-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ae74-113">E_FAIL</span></span>|<span data-ttu-id="4ae74-114">No se devolvió el marco actual.</span><span class="sxs-lookup"><span data-stu-id="4ae74-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="4ae74-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4ae74-115">S_FALSE</span></span>|<span data-ttu-id="4ae74-116">El marco actual es un marco de pila nativo.</span><span class="sxs-lookup"><span data-stu-id="4ae74-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="4ae74-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4ae74-117">E_INVALIDARG</span></span>|<span data-ttu-id="4ae74-118">`pFrame` es null.</span><span class="sxs-lookup"><span data-stu-id="4ae74-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="4ae74-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="4ae74-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="4ae74-120">El puntero de marco ya está al final de la pila; por lo tanto, no puede tener acceso a ningún marco adicional.</span><span class="sxs-lookup"><span data-stu-id="4ae74-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4ae74-121">Excepciones</span><span class="sxs-lookup"><span data-stu-id="4ae74-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ae74-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ae74-122">Remarks</span></span>  
 <span data-ttu-id="4ae74-123">`ICorDebugStackWalk` Devuelve solo los marcos de pila real.</span><span class="sxs-lookup"><span data-stu-id="4ae74-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="4ae74-124">Use la [Icordebugthread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) método para devolver los marcos internos.</span><span class="sxs-lookup"><span data-stu-id="4ae74-124">Use the [ICorDebugThread3::GetActiveInternalFrames](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="4ae74-125">(Los marcos internos son estructuras de datos que se insertan en la pila, el tiempo de ejecución para almacenar datos temporales).</span><span class="sxs-lookup"><span data-stu-id="4ae74-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ae74-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ae74-126">Requirements</span></span>  
 <span data-ttu-id="4ae74-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ae74-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ae74-128">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ae74-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ae74-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ae74-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ae74-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ae74-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ae74-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ae74-131">See also</span></span>

- [<span data-ttu-id="4ae74-132">ICorDebugStackWalk (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ae74-132">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="4ae74-133">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4ae74-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="4ae74-134">Depuración</span><span class="sxs-lookup"><span data-stu-id="4ae74-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
