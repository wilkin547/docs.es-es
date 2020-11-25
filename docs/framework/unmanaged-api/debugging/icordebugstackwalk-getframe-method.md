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
ms.openlocfilehash: 452635764794e01858baab10464a03c966a55271
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711943"
---
# <a name="icordebugstackwalkgetframe-method"></a><span data-ttu-id="69007-102">ICorDebugStackWalk::GetFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="69007-102">ICorDebugStackWalk::GetFrame Method</span></span>

<span data-ttu-id="69007-103">Obtiene el marco actual del objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="69007-103">Gets the current frame in the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69007-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69007-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrame([out] ICorDebugFrame ** pFrame);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69007-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69007-105">Parameters</span></span>  

 `pFrame`  
 <span data-ttu-id="69007-106">de Puntero a la dirección del objeto de marco creado que representa el marco actual en la pila.</span><span class="sxs-lookup"><span data-stu-id="69007-106">[in] A pointer to the address of the created frame object that represents the current frame in the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69007-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="69007-107">Return Value</span></span>  

 <span data-ttu-id="69007-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="69007-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="69007-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69007-109">HRESULT</span></span>|<span data-ttu-id="69007-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="69007-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69007-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="69007-111">S_OK</span></span>|<span data-ttu-id="69007-112">El tiempo de ejecución devolvió correctamente el marco actual.</span><span class="sxs-lookup"><span data-stu-id="69007-112">The runtime successfully returned the current frame.</span></span>|  
|<span data-ttu-id="69007-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="69007-113">E_FAIL</span></span>|<span data-ttu-id="69007-114">No se devolvió el marco actual.</span><span class="sxs-lookup"><span data-stu-id="69007-114">The current frame was not returned.</span></span>|  
|<span data-ttu-id="69007-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="69007-115">S_FALSE</span></span>|<span data-ttu-id="69007-116">El marco actual es un marco de pila nativo.</span><span class="sxs-lookup"><span data-stu-id="69007-116">The current frame is a native stack frame.</span></span>|  
|<span data-ttu-id="69007-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="69007-117">E_INVALIDARG</span></span>|<span data-ttu-id="69007-118">`pFrame` es null.</span><span class="sxs-lookup"><span data-stu-id="69007-118">`pFrame` is null.</span></span>|  
|<span data-ttu-id="69007-119">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="69007-119">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="69007-120">El puntero de marco ya está al final de la pila; por lo tanto, no se puede tener acceso a ningún fotograma adicional.</span><span class="sxs-lookup"><span data-stu-id="69007-120">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="69007-121">Excepciones</span><span class="sxs-lookup"><span data-stu-id="69007-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69007-122">Notas</span><span class="sxs-lookup"><span data-stu-id="69007-122">Remarks</span></span>  

 <span data-ttu-id="69007-123">`ICorDebugStackWalk` Devuelve solo los marcos de pila reales.</span><span class="sxs-lookup"><span data-stu-id="69007-123">`ICorDebugStackWalk` returns only actual stack frames.</span></span> <span data-ttu-id="69007-124">Use el método [ICorDebugThread3:: GetActiveInternalFrames (](icordebugthread3-getactiveinternalframes-method.md) para devolver Marcos internos.</span><span class="sxs-lookup"><span data-stu-id="69007-124">Use the [ICorDebugThread3::GetActiveInternalFrames](icordebugthread3-getactiveinternalframes-method.md) method to return internal frames.</span></span> <span data-ttu-id="69007-125">(Los marcos internos son estructuras de datos insertadas en la pila por el motor en tiempo de ejecución para almacenar datos temporales).</span><span class="sxs-lookup"><span data-stu-id="69007-125">(Internal frames are data structures pushed onto the stack by the runtime to store temporary data.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69007-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69007-126">Requirements</span></span>  

 <span data-ttu-id="69007-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69007-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69007-128">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69007-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69007-129">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69007-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69007-130">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69007-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69007-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="69007-131">See also</span></span>

- [<span data-ttu-id="69007-132">ICorDebugStackWalk (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="69007-132">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="69007-133">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="69007-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="69007-134">Depuración</span><span class="sxs-lookup"><span data-stu-id="69007-134">Debugging</span></span>](index.md)
