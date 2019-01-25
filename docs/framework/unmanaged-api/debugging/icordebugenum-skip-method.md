---
title: ICorDebugEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a886d8ab8f2d59bb9c9b0b3ff00fd89f7c931ff8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692826"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="495ac-102">ICorDebugEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="495ac-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="495ac-103">Mueve el cursor hacia delante en la enumeración por el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="495ac-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="495ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="495ac-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="495ac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="495ac-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="495ac-106">[in] El número de elementos por el que se va a mover el cursor hacia delante.</span><span class="sxs-lookup"><span data-stu-id="495ac-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="495ac-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="495ac-107">Requirements</span></span>  
 <span data-ttu-id="495ac-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="495ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="495ac-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="495ac-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="495ac-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="495ac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="495ac-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="495ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="495ac-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="495ac-112">See also</span></span>
- [<span data-ttu-id="495ac-113">ICorDebugEnum (interfaz1)</span><span class="sxs-lookup"><span data-stu-id="495ac-113">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
