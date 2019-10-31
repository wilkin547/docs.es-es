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
ms.openlocfilehash: 0666becb5a34688d3f4cf5bddd1e2fa71785b38a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139788"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="ece66-102">ICorDebugProcessEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="ece66-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="ece66-103">Obtiene el número especificado de instancias de ICorDebugProcess de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="ece66-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ece66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ece66-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ece66-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ece66-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ece66-106">de Número de instancias de `ICorDebugProcess` que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="ece66-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="ece66-107">enuncia Una matriz de punteros, cada uno de los cuales apunta a un `ICorDebugProcess` objeto que representa un proceso.</span><span class="sxs-lookup"><span data-stu-id="ece66-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ece66-108">enuncia Puntero al número de instancias de `ICorDebugProcess` devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="ece66-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="ece66-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="ece66-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ece66-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ece66-110">Requirements</span></span>  
 <span data-ttu-id="ece66-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ece66-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ece66-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ece66-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ece66-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ece66-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ece66-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ece66-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
