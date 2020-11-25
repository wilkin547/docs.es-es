---
title: ICorDebugArrayValue::HasBaseIndicies (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
ms.openlocfilehash: a9d1faf5a834cb5d9be19f995aaa3eee1202171b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727450"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="7b2a6-102">ICorDebugArrayValue::HasBaseIndicies (Método)</span><span class="sxs-lookup"><span data-stu-id="7b2a6-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>

<span data-ttu-id="7b2a6-103">Obtiene un valor que indica si alguna dimensión de esta matriz tiene un índice base distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="7b2a6-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b2a6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b2a6-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b2a6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b2a6-105">Parameters</span></span>  

 `pbHasBaseIndicies`  
 <span data-ttu-id="7b2a6-106">enuncia Un puntero a un valor booleano que es `true` si una o más dimensiones de este `ICorDebugArrayValue` objeto tienen un índice base distinto de cero; de lo contrario, el valor booleano es `false` .</span><span class="sxs-lookup"><span data-stu-id="7b2a6-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b2a6-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b2a6-107">Requirements</span></span>  

 <span data-ttu-id="7b2a6-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b2a6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b2a6-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b2a6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b2a6-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b2a6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b2a6-111">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b2a6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
