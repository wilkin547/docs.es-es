---
description: 'Más información acerca de: ICorDebugArrayValue:: Hasbaseindicies ((método)'
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
ms.openlocfilehash: b251653004801ff2d312dfb34749c413774ddf40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722963"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="c0bcd-103">ICorDebugArrayValue::HasBaseIndicies (Método)</span><span class="sxs-lookup"><span data-stu-id="c0bcd-103">ICorDebugArrayValue::HasBaseIndicies Method</span></span>

<span data-ttu-id="c0bcd-104">Obtiene un valor que indica si alguna dimensión de esta matriz tiene un índice base distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="c0bcd-104">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0bcd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0bcd-105">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0bcd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0bcd-106">Parameters</span></span>  

 `pbHasBaseIndicies`  
 <span data-ttu-id="c0bcd-107">enuncia Un puntero a un valor booleano que es `true` si una o más dimensiones de este `ICorDebugArrayValue` objeto tienen un índice base distinto de cero; de lo contrario, el valor booleano es `false` .</span><span class="sxs-lookup"><span data-stu-id="c0bcd-107">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0bcd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0bcd-108">Requirements</span></span>  

 <span data-ttu-id="c0bcd-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0bcd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0bcd-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0bcd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0bcd-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0bcd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0bcd-112">**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0bcd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
