---
title: ICorDebugValueEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
ms.openlocfilehash: db1721fed6414310556ceac493275e069a781ac8
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397143"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="f8648-102">ICorDebugValueEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="f8648-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="f8648-103">Obtiene el número especificado de instancias de "ICorDebugValue" de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="f8648-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8648-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8648-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8648-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8648-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="f8648-106">de El número de `ICorDebugValue` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="f8648-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="f8648-107">enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="f8648-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f8648-108">enuncia Puntero al número de `ICorDebugValue` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="f8648-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="f8648-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="f8648-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8648-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8648-110">Requirements</span></span>  
 <span data-ttu-id="f8648-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8648-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8648-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8648-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8648-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8648-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8648-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8648-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8648-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8648-115">See also</span></span>
