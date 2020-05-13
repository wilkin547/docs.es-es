---
title: ICorDebugStackWalk::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: b89e968e9b12943c8192af3b280f8bd321a02110
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378793"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="143ea-102">ICorDebugStackWalk::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="143ea-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="143ea-103">Mueve el objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) al siguiente fotograma.</span><span class="sxs-lookup"><span data-stu-id="143ea-103">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="143ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="143ea-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="143ea-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="143ea-105">Return Value</span></span>  
 <span data-ttu-id="143ea-106">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="143ea-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="143ea-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="143ea-107">HRESULT</span></span>|<span data-ttu-id="143ea-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="143ea-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="143ea-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="143ea-109">S_OK</span></span>|<span data-ttu-id="143ea-110">El tiempo de ejecución se desenrollará correctamente en el siguiente fotograma (vea la sección comentarios).</span><span class="sxs-lookup"><span data-stu-id="143ea-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="143ea-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="143ea-111">E_FAIL</span></span>|<span data-ttu-id="143ea-112">El `ICorDebugStackWalk` objeto no pudo ser avanzado.</span><span class="sxs-lookup"><span data-stu-id="143ea-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="143ea-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="143ea-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="143ea-114">Se alcanzó el final de la pila como resultado de este desenredado.</span><span class="sxs-lookup"><span data-stu-id="143ea-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="143ea-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="143ea-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="143ea-116">El puntero de marco ya está al final de la pila; por lo tanto, no se puede tener acceso a ningún fotograma adicional.</span><span class="sxs-lookup"><span data-stu-id="143ea-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="143ea-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="143ea-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="143ea-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="143ea-118">Remarks</span></span>  
 <span data-ttu-id="143ea-119">El `Next` método hace avanzar el `ICorDebugStackWalk` objeto hasta el marco que realiza la llamada solo si el tiempo de ejecución puede desenredar el fotograma actual.</span><span class="sxs-lookup"><span data-stu-id="143ea-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="143ea-120">De lo contrario, el objeto avanza hasta el siguiente fotograma que el runtime puede desenredar.</span><span class="sxs-lookup"><span data-stu-id="143ea-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="143ea-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="143ea-121">Requirements</span></span>  
 <span data-ttu-id="143ea-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="143ea-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="143ea-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="143ea-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="143ea-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="143ea-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="143ea-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="143ea-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="143ea-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="143ea-126">See also</span></span>

- [<span data-ttu-id="143ea-127">ICorDebugStackWalk (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="143ea-127">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="143ea-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="143ea-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="143ea-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="143ea-129">Debugging</span></span>](index.md)
