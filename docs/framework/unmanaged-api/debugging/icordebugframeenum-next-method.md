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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be126e45d8428d8786e9aadf2195133d1957440
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754826"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="fdbab-102">ICorDebugFrameEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="fdbab-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="fdbab-103">Obtiene el número especificado de instancias de ICorDebugFrame, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="fdbab-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdbab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdbab-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdbab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fdbab-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fdbab-106">[in] El número de `ICorDebugFrame` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="fdbab-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="fdbab-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="fdbab-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fdbab-108">[out] Un puntero al número de `ICorDebugFrame` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="fdbab-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="fdbab-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="fdbab-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdbab-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdbab-110">Requirements</span></span>  
 <span data-ttu-id="fdbab-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdbab-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdbab-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdbab-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdbab-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdbab-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdbab-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdbab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
