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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7624a22e5d65ae94797779a0b8cfa70f226450ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418989"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="61929-102">ICorDebugModuleEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="61929-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="61929-103">Obtiene el número de instancias de "ICorDebugModule" especificada por `celt` de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="61929-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61929-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61929-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61929-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="61929-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="61929-106">[in] El número de `ICorDebugModule` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="61929-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="61929-107">[out] Una matriz de punteros, cada uno de los cuales señala a un `ICorDebugModule` objeto.</span><span class="sxs-lookup"><span data-stu-id="61929-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="61929-108">[out] Puntero al número de `ICorDebugModule` instancias realmente devueltos.</span><span class="sxs-lookup"><span data-stu-id="61929-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="61929-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="61929-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61929-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61929-110">Requirements</span></span>  
 <span data-ttu-id="61929-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61929-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61929-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61929-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61929-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61929-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61929-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61929-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61929-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="61929-115">See Also</span></span>  
 
