---
description: 'Más información sobre: ICorDebugStackWalk:: GetFrame (método)'
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
ms.openlocfilehash: b00ddb6a475aff4263a922f5a20b866cd0e1b2ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794746"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="e0b6e-103">ICorDebugStackWalk::GetFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="e0b6e-103">ICorDebugStackWalk::GetFrame Method</span></span>

<span data-ttu-id="e0b6e-104">Obtiene el marco actual del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e0b6e-104">Gets the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0b6e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0b6e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0b6e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0b6e-106">Parameters</span></span>  

 `pFrame`  
 <span data-ttu-id="e0b6e-107">de Puntero a la dirección del objeto de marco creado que representa el marco actual en la pila.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-107">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0b6e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e0b6e-108">Return Value</span></span>  

 <span data-ttu-id="e0b6e-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e0b6e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0b6e-110">HRESULT</span></span>|<span data-ttu-id="e0b6e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0b6e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0b6e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0b6e-112">S_OK</span></span>|<span data-ttu-id="e0b6e-113">El tiempo de ejecución devolvió correctamente el marco actual.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-113">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="e0b6e-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0b6e-114">E_FAIL</span></span>|<span data-ttu-id="e0b6e-115">No se devolvió el marco actual.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-115">The current frame was not returned.</span></span>|  
|<span data-ttu-id="e0b6e-116">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e0b6e-116">S_FALSE</span></span>|<span data-ttu-id="e0b6e-117">El marco actual es un marco de pila nativo.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-117">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="e0b6e-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e0b6e-118">E_INVALIDARG</span></span>|<span data-ttu-id="e0b6e-119">`pFrame` es null.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-119">`pFrame` is null.</span></span>|  
|<span data-ttu-id="e0b6e-120">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="e0b6e-120">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="e0b6e-121">El puntero de marco ya está al final de la pila; por lo tanto, no se puede tener acceso a ningún fotograma adicional.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-121">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="e0b6e-122">Excepciones</span><span class="sxs-lookup"><span data-stu-id="e0b6e-122">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0b6e-123">Notas</span><span class="sxs-lookup"><span data-stu-id="e0b6e-123">Remarks</span></span>  

 <span data-ttu-id="e0b6e-124">`ICorDebugStackWalk` Devuelve solo los marcos de pila reales.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-124">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="e0b6e-125">Use el método [ICorDebugThread3:: GetActiveInternalFrames (](icordebugthread3-getactiveinternalframes-method.md) para devolver Marcos internos.</span><span class="sxs-lookup"><span data-stu-id="e0b6e-125">Use the [ICorDebugThread3::GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="e0b6e-126">(Los marcos internos son estructuras de datos insertadas en la pila por el motor en tiempo de ejecución para almacenar datos temporales).</span><span class="sxs-lookup"><span data-stu-id="e0b6e-126">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0b6e-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0b6e-127">Requirements</span></span>  

 <span data-ttu-id="e0b6e-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0b6e-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0b6e-129">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0b6e-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0b6e-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0b6e-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0b6e-131">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0b6e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b6e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0b6e-132">See also</span></span>

- [<span data-ttu-id="e0b6e-133">ICorDebugStackWalk (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0b6e-133">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="e0b6e-134">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e0b6e-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e0b6e-135">Depuración</span><span class="sxs-lookup"><span data-stu-id="e0b6e-135">Debugging</span></span>](index.md)
