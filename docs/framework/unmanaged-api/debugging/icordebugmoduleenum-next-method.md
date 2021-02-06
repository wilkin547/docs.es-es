---
description: 'Más información sobre: ICorDebugModuleEnum (:: Next (método)'
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
ms.openlocfilehash: ed9558edad80c67e7bf3febb10c3adcd027e180a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650279"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="22967-103">ICorDebugModuleEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="22967-103">ICorDebugModuleEnum::Next Method</span></span>

<span data-ttu-id="22967-104">Obtiene el número de instancias de "ICorDebugModule" especificadas por `celt` en la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="22967-104">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22967-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22967-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22967-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="22967-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="22967-107">de El número de `ICorDebugModule` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="22967-107">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="22967-108">enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugModule` objeto.</span><span class="sxs-lookup"><span data-stu-id="22967-108">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="22967-109">enuncia Puntero al número de `ICorDebugModule` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="22967-109">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="22967-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="22967-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22967-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22967-111">Requirements</span></span>  

 <span data-ttu-id="22967-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22967-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22967-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22967-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22967-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22967-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22967-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22967-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22967-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="22967-116">See also</span></span>
