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
ms.openlocfilehash: a4613e11896a34ed1a7fe91d4767fb38ac75aab8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754521"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="9a820-102">ICorDebugFunction::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="9a820-102">ICorDebugFunction::GetToken Method</span></span>
<span data-ttu-id="9a820-103">Obtiene los metadatos de token para esta función.</span><span class="sxs-lookup"><span data-stu-id="9a820-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a820-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a820-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a820-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9a820-105">Parameters</span></span>  
 `pMethodDef`  
 <span data-ttu-id="9a820-106">[out] Un puntero a un `mdMethodDef` símbolo (token) que hace referencia a los metadatos para esta función.</span><span class="sxs-lookup"><span data-stu-id="9a820-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a820-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9a820-107">Requirements</span></span>  
 <span data-ttu-id="9a820-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a820-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a820-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a820-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a820-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a820-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a820-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a820-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
