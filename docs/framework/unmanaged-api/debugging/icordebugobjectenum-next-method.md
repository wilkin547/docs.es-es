---
title: ICorDebugObjectEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4db5b6c6d54729363cd734840926f97d89aa4bfa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489298"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="cf449-102">ICorDebugObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="cf449-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="cf449-103">Obtiene las direcciones virtuales relativas (RVA) del número especificado de objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="cf449-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf449-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf449-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf449-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf449-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cf449-106">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="cf449-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="cf449-107">[out] Una matriz de punteros, cada uno de los cuales apunta a un objeto CORDB_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="cf449-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="cf449-108">[out] Puntero al número de objetos devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="cf449-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="cf449-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="cf449-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf449-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf449-110">Requirements</span></span>  
 <span data-ttu-id="cf449-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf449-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf449-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf449-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf449-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf449-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf449-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf449-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf449-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf449-115">See also</span></span>

