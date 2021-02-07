---
description: 'Más información acerca de: ICorDebugStackWalk:: Next (método)'
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
ms.openlocfilehash: 27a48ca40f6b43cae32511b71b73e68d88eb60c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717763"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="79747-103">ICorDebugStackWalk::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="79747-103">ICorDebugStackWalk::Next Method</span></span>

<span data-ttu-id="79747-104">Mueve el objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) al siguiente fotograma.</span><span class="sxs-lookup"><span data-stu-id="79747-104">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79747-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79747-105">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="79747-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="79747-106">Return Value</span></span>  

 <span data-ttu-id="79747-107">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="79747-107">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="79747-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="79747-108">HRESULT</span></span>|<span data-ttu-id="79747-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="79747-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="79747-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="79747-110">S_OK</span></span>|<span data-ttu-id="79747-111">El tiempo de ejecución se desenrollará correctamente en el siguiente fotograma (vea la sección comentarios).</span><span class="sxs-lookup"><span data-stu-id="79747-111">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="79747-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="79747-112">E_FAIL</span></span>|<span data-ttu-id="79747-113">El `ICorDebugStackWalk` objeto no pudo ser avanzado.</span><span class="sxs-lookup"><span data-stu-id="79747-113">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="79747-114">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="79747-114">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="79747-115">Se alcanzó el final de la pila como resultado de este desenredado.</span><span class="sxs-lookup"><span data-stu-id="79747-115">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="79747-116">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="79747-116">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="79747-117">El puntero de marco ya está al final de la pila; por lo tanto, no se puede tener acceso a ningún fotograma adicional.</span><span class="sxs-lookup"><span data-stu-id="79747-117">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="79747-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="79747-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79747-119">Notas</span><span class="sxs-lookup"><span data-stu-id="79747-119">Remarks</span></span>  

 <span data-ttu-id="79747-120">El `Next` método hace avanzar el `ICorDebugStackWalk` objeto hasta el marco que realiza la llamada solo si el tiempo de ejecución puede desenredar el fotograma actual.</span><span class="sxs-lookup"><span data-stu-id="79747-120">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="79747-121">De lo contrario, el objeto avanza hasta el siguiente fotograma que el runtime puede desenredar.</span><span class="sxs-lookup"><span data-stu-id="79747-121">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79747-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79747-122">Requirements</span></span>  

 <span data-ttu-id="79747-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79747-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79747-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79747-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79747-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79747-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79747-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79747-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79747-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="79747-127">See also</span></span>

- [<span data-ttu-id="79747-128">ICorDebugStackWalk (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="79747-128">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="79747-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="79747-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="79747-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="79747-130">Debugging</span></span>](index.md)
