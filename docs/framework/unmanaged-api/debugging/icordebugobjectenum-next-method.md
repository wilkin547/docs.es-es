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
ms.openlocfilehash: 6998be3daf0ab6a6290a3400b96c32227df3e022
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175102"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="56402-102">ICorDebugObjectEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="56402-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="56402-103">Obtiene las direcciones virtuales relativas (RVA) del número especificado de objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="56402-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56402-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="56402-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56402-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="56402-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="56402-106">[in] Número de objetos que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="56402-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="56402-107">[out] Una matriz de punteros, cada uno de los cuales apunta a un objeto CORDB_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="56402-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="56402-108">[out] Puntero al número de objetos devueltos realmente.</span><span class="sxs-lookup"><span data-stu-id="56402-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="56402-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="56402-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56402-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="56402-110">Requirements</span></span>  
 <span data-ttu-id="56402-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56402-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56402-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56402-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56402-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56402-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="56402-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="56402-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56402-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="56402-115">See also</span></span>
