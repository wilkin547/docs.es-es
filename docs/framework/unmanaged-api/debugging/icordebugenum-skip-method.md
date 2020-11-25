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
ms.openlocfilehash: ae88336b9640b68b97522d252b3e8334c20ed9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705870"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="0e8a7-102">ICorDebugEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="0e8a7-102">ICorDebugEnum::Skip Method</span></span>

<span data-ttu-id="0e8a7-103">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="0e8a7-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e8a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e8a7-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e8a7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e8a7-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="0e8a7-106">de Número de elementos por los que se va a desplazar el cursor hacia delante.</span><span class="sxs-lookup"><span data-stu-id="0e8a7-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e8a7-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e8a7-107">Requirements</span></span>  

 <span data-ttu-id="0e8a7-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e8a7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e8a7-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e8a7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e8a7-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e8a7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e8a7-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e8a7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e8a7-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e8a7-112">See also</span></span>

- [<span data-ttu-id="0e8a7-113">Interfaz ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="0e8a7-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
