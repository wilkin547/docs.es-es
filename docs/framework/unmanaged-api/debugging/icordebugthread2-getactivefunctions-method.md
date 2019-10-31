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
ms.openlocfilehash: 9b9a301714ea60b4e3220eb75721e56e39bd9659
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139933"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="4d9cf-102">ICorDebugThread2::GetActiveFunctions (Método)</span><span class="sxs-lookup"><span data-stu-id="4d9cf-102">ICorDebugThread2::GetActiveFunctions Method</span></span>
<span data-ttu-id="4d9cf-103">Obtiene información sobre la función activa en cada uno de los marcos de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="4d9cf-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d9cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d9cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d9cf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d9cf-105">Parameters</span></span>  
 `cFunctions`  
 <span data-ttu-id="4d9cf-106">[in] Tamaño de la matriz `pFunctions`.</span><span class="sxs-lookup"><span data-stu-id="4d9cf-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="4d9cf-107">enuncia Puntero al número de objetos devueltos en la matriz de `pFunctions`.</span><span class="sxs-lookup"><span data-stu-id="4d9cf-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="4d9cf-108">El número de objetos devueltos será igual al número de Marcos administrados en la pila.</span><span class="sxs-lookup"><span data-stu-id="4d9cf-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="4d9cf-109">[in, out] Matriz de objetos COR_ACTIVE_FUNCTION, cada uno de los cuales contiene información sobre las funciones activas de los marcos de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="4d9cf-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="4d9cf-110">El primer elemento se usará para el marco hoja y así sucesivamente hasta la raíz de la pila.</span><span class="sxs-lookup"><span data-stu-id="4d9cf-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d9cf-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d9cf-111">Remarks</span></span>  
 <span data-ttu-id="4d9cf-112">Si `pFunctions` es null en la entrada, `GetActiveFunctions` devuelve solo el número de funciones que se encuentran en la pila.</span><span class="sxs-lookup"><span data-stu-id="4d9cf-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="4d9cf-113">Es decir, si `pFunctions` es null en la entrada, `GetActiveFunctions` solo devuelve un valor en `pcFunctions`.</span><span class="sxs-lookup"><span data-stu-id="4d9cf-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="4d9cf-114">El método `GetActiveFunctions` está pensado como una optimización para obtener la misma información de los fotogramas de un seguimiento de la pila e incluye solo los fotogramas que habrían tenido un objeto ICorDebugILFrame para ellos en el seguimiento de la pila completa.</span><span class="sxs-lookup"><span data-stu-id="4d9cf-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d9cf-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d9cf-115">Requirements</span></span>  
 <span data-ttu-id="4d9cf-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d9cf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d9cf-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d9cf-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d9cf-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d9cf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d9cf-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d9cf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
