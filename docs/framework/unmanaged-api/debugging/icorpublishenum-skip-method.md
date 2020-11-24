---
title: ICorPublishEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
ms.openlocfilehash: 888cc40c194cb86b0f898f5556ea14b8897e08c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693312"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="44899-102">ICorPublishEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="44899-102">ICorPublishEnum::Skip Method</span></span>

<span data-ttu-id="44899-103">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="44899-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44899-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44899-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44899-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="44899-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="44899-106">de Número de elementos por los que se va a desplazar el cursor hacia delante.</span><span class="sxs-lookup"><span data-stu-id="44899-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44899-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44899-107">Requirements</span></span>  

 <span data-ttu-id="44899-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44899-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44899-109">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="44899-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="44899-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44899-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44899-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44899-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44899-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44899-112">See also</span></span>

- [<span data-ttu-id="44899-113">ICorPublishEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44899-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
