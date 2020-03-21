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
ms.openlocfilehash: e9b32980a5606629676549905d3c9956633f25b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178698"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="89e2f-102">ICorDebugObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="89e2f-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="89e2f-103">Obtiene las direcciones virtuales relativas (RVA) del número especificado de objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="89e2f-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89e2f-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89e2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89e2f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="89e2f-106">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="89e2f-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="89e2f-107">[fuera] Matriz de punteros, cada uno de los cuales apunta a un objeto CORDB_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="89e2f-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="89e2f-108">[fuera] Puntero al número de objetos devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="89e2f-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="89e2f-109">Este valor puede `celt` ser null si es uno.</span><span class="sxs-lookup"><span data-stu-id="89e2f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89e2f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89e2f-110">Requirements</span></span>  
 <span data-ttu-id="89e2f-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89e2f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89e2f-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89e2f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89e2f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89e2f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89e2f-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89e2f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e2f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89e2f-115">See also</span></span>
