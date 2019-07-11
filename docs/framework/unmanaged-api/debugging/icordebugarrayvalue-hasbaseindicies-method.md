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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c488ca3a77f2c2b2a40c6143989cd86adf071787
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737432"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="570e4-102">ICorDebugArrayValue::HasBaseIndicies (Método)</span><span class="sxs-lookup"><span data-stu-id="570e4-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="570e4-103">Obtiene un valor que indica si las dimensiones de esta matriz tienen un índice base distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="570e4-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="570e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="570e4-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="570e4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="570e4-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="570e4-106">[out] Un puntero a un valor booleano que es `true` si uno o más dimensiones de esta `ICorDebugArrayValue` objeto tiene un índice base distinto de cero; en caso contrario, es el valor booleano `false`.</span><span class="sxs-lookup"><span data-stu-id="570e4-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="570e4-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="570e4-107">Requirements</span></span>  
 <span data-ttu-id="570e4-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="570e4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="570e4-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="570e4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="570e4-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="570e4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="570e4-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="570e4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
