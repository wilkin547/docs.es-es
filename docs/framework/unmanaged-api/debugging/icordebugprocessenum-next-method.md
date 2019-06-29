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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9f32b554de191ff84e7c319e2a00e3cd0610a9f
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422197"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="4dd13-102">ICorDebugProcessEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="4dd13-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="4dd13-103">Obtiene el número de instancias de ICorDebugProcess especificado de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="4dd13-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dd13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4dd13-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dd13-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4dd13-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4dd13-106">[in] El número de `ICorDebugProcess` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="4dd13-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="4dd13-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugProcess` objeto que representa un proceso.</span><span class="sxs-lookup"><span data-stu-id="4dd13-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4dd13-108">[out] Puntero al número de `ICorDebugProcess` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="4dd13-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="4dd13-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="4dd13-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dd13-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4dd13-110">Requirements</span></span>  
 <span data-ttu-id="4dd13-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dd13-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dd13-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4dd13-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dd13-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dd13-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dd13-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dd13-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
