---
title: ICorDebugModuleEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: 6c4262c18e4efcbbca1b3e2a327fec7d4b609a31
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096924"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="573b5-102">ICorDebugModuleEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="573b5-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="573b5-103">Obtiene el número de instancias de "ICorDebugModule" especificadas por `celt` de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="573b5-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="573b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="573b5-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="573b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="573b5-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="573b5-106">de Número de instancias de `ICorDebugModule` que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="573b5-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="573b5-107">enuncia Matriz de punteros, cada uno de los cuales señala a un objeto `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="573b5-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="573b5-108">enuncia Puntero al número de instancias de `ICorDebugModule` devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="573b5-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="573b5-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="573b5-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="573b5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="573b5-110">Requirements</span></span>  
 <span data-ttu-id="573b5-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="573b5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="573b5-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="573b5-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="573b5-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="573b5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="573b5-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="573b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="573b5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="573b5-115">See also</span></span>
