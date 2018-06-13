---
title: ICorDebugBreakpointEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11c08e59813014bf9a474e92d06c6bd2576dd7d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404877"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="c5371-102">ICorDebugBreakpointEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="c5371-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="c5371-103">Obtiene el número especificado de instancias de ICorDebugBreakpoint de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="c5371-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5371-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5371-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5371-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5371-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c5371-106">[in] El número de `ICorDebugBreakpoint` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="c5371-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="c5371-107">[out] Una matriz de punteros, cada uno de los cuales señala a un `ICorDebugBreakpoint` objeto que representa un punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="c5371-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c5371-108">[out] Un puntero al número de `ICorDebugBreakpoint` instancias realmente devueltos.</span><span class="sxs-lookup"><span data-stu-id="c5371-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="c5371-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="c5371-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5371-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5371-110">Requirements</span></span>  
 <span data-ttu-id="c5371-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5371-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5371-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5371-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5371-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5371-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5371-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5371-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
