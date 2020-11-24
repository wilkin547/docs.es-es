---
title: ICorDebugThread2::GetActiveFunctions (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
ms.openlocfilehash: 2d5674d6b5962ca539de02cda1e5658daed83622
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678758"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="5f4b4-102">ICorDebugThread2::GetActiveFunctions (Método)</span><span class="sxs-lookup"><span data-stu-id="5f4b4-102">ICorDebugThread2::GetActiveFunctions Method</span></span>

<span data-ttu-id="5f4b4-103">Obtiene información sobre la función activa en cada uno de los marcos de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="5f4b4-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f4b4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f4b4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f4b4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f4b4-105">Parameters</span></span>  

 `cFunctions`  
 <span data-ttu-id="5f4b4-106">[in] Tamaño de la matriz `pFunctions`.</span><span class="sxs-lookup"><span data-stu-id="5f4b4-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="5f4b4-107">enuncia Puntero al número de objetos devueltos en la `pFunctions` matriz.</span><span class="sxs-lookup"><span data-stu-id="5f4b4-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="5f4b4-108">El número de objetos devueltos será igual al número de Marcos administrados en la pila.</span><span class="sxs-lookup"><span data-stu-id="5f4b4-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="5f4b4-109">[in, out] Matriz de objetos COR_ACTIVE_FUNCTION, cada uno de los cuales contiene información sobre las funciones activas de los marcos de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="5f4b4-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="5f4b4-110">El primer elemento se usará para el marco hoja y así sucesivamente hasta la raíz de la pila.</span><span class="sxs-lookup"><span data-stu-id="5f4b4-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f4b4-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f4b4-111">Remarks</span></span>  

 <span data-ttu-id="5f4b4-112">Si `pFunctions` es null en la entrada, `GetActiveFunctions` solo devuelve el número de funciones que se encuentran en la pila.</span><span class="sxs-lookup"><span data-stu-id="5f4b4-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="5f4b4-113">Es decir, si `pFunctions` es null en la entrada, `GetActiveFunctions` solo devuelve un valor en `pcFunctions` .</span><span class="sxs-lookup"><span data-stu-id="5f4b4-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="5f4b4-114">El `GetActiveFunctions` método está pensado como una optimización para obtener la misma información de los marcos de un seguimiento de la pila e incluye solo los fotogramas que habrían tenido un objeto ICorDebugILFrame para ellos en el seguimiento de la pila completa.</span><span class="sxs-lookup"><span data-stu-id="5f4b4-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f4b4-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f4b4-115">Requirements</span></span>  

 <span data-ttu-id="5f4b4-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f4b4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f4b4-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f4b4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f4b4-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f4b4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f4b4-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f4b4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
