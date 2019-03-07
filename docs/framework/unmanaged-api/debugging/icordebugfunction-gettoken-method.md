---
title: ICorDebugFunction::GetToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetToken
helpviewer_keywords:
- ICorDebugFunction::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: c6bbf479-062e-48e9-9c70-0f92e293e36a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e56c8eba49260eba9e3e0ca7e9ab4c7cfcd3261f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471945"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="2536f-102">ICorDebugFunction::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="2536f-102">ICorDebugFunction::GetToken Method</span></span>
<span data-ttu-id="2536f-103">Obtiene los metadatos de token para esta función.</span><span class="sxs-lookup"><span data-stu-id="2536f-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2536f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2536f-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2536f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2536f-105">Parameters</span></span>  
 `pMethodDef`  
 <span data-ttu-id="2536f-106">[out] Un puntero a un `mdMethodDef` símbolo (token) que hace referencia a los metadatos para esta función.</span><span class="sxs-lookup"><span data-stu-id="2536f-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2536f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2536f-107">Requirements</span></span>  
 <span data-ttu-id="2536f-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2536f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2536f-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2536f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2536f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2536f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2536f-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2536f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
