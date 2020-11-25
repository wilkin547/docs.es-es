---
title: ICorDebugProcessEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: 6aee88452819a4aabe2a29971ce86079ef7f0008
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732507"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="c9c41-102">ICorDebugProcessEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="c9c41-102">ICorDebugProcessEnum::Next Method</span></span>

<span data-ttu-id="c9c41-103">Obtiene el número especificado de instancias de ICorDebugProcess de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="c9c41-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9c41-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9c41-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9c41-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9c41-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="c9c41-106">de El número de `ICorDebugProcess` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="c9c41-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="c9c41-107">enuncia Matriz de punteros, cada uno de los cuales apunta a un `ICorDebugProcess` objeto que representa un proceso.</span><span class="sxs-lookup"><span data-stu-id="c9c41-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c9c41-108">enuncia Puntero al número de `ICorDebugProcess` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="c9c41-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="c9c41-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="c9c41-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9c41-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9c41-110">Requirements</span></span>  

 <span data-ttu-id="c9c41-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9c41-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9c41-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9c41-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9c41-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9c41-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9c41-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9c41-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
