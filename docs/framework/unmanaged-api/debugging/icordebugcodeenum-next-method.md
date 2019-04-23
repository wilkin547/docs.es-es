---
title: ICorDebugCodeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5db87cd4ad965654b63a68828cd088b8d2f7d07c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113053"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="25389-102">ICorDebugCodeEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="25389-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="25389-103">Obtiene el número especificado de instancias de "ICorDebugCode" de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="25389-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25389-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25389-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25389-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25389-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="25389-106">[in] El número de `ICorDebugCode` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="25389-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="25389-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugCode` objeto.</span><span class="sxs-lookup"><span data-stu-id="25389-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="25389-108">[out] Un puntero al número de `ICorDebugCode` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="25389-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="25389-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="25389-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25389-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25389-110">Requirements</span></span>  
 <span data-ttu-id="25389-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25389-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25389-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25389-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25389-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25389-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25389-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25389-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25389-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="25389-115">See also</span></span>
