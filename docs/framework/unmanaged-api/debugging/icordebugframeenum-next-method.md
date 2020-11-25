---
title: ICorDebugFrameEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: 76b96dfd9d22c7e770671dcc01cb421430df729f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728191"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="94239-102">ICorDebugFrameEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="94239-102">ICorDebugFrameEnum::Next Method</span></span>

<span data-ttu-id="94239-103">Obtiene el número especificado de instancias de ICorDebugFrame, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="94239-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94239-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="94239-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94239-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="94239-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="94239-106">de El número de `ICorDebugFrame` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="94239-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="94239-107">enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="94239-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="94239-108">enuncia Puntero al número de `ICorDebugFrame` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="94239-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="94239-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="94239-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94239-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94239-110">Requirements</span></span>  

 <span data-ttu-id="94239-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94239-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94239-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94239-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94239-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94239-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94239-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94239-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
