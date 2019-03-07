---
title: ICorDebugChainEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26df40297d080d1ccc9464f7b09e7731f135e270
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489831"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="aa1cc-102">ICorDebugChainEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="aa1cc-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="aa1cc-103">Obtiene el número especificado de instancias de ICorDebugChain de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="aa1cc-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa1cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa1cc-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa1cc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa1cc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="aa1cc-106">[in] El número de `ICorDebugChain` instancias va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="aa1cc-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="aa1cc-107">[out] Una matriz de punteros, cada uno de los cuales señala a una `ICorDebugChain` objeto que representa una cadena.</span><span class="sxs-lookup"><span data-stu-id="aa1cc-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="aa1cc-108">[out] Un puntero al número de `ICorDebugChain` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="aa1cc-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="aa1cc-109">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="aa1cc-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa1cc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa1cc-110">Requirements</span></span>  
 <span data-ttu-id="aa1cc-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa1cc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa1cc-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa1cc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa1cc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa1cc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa1cc-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa1cc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
