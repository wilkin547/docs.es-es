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
ms.openlocfilehash: 9aee95c554afad5b2ea3cf157fc9e62c9b7e40e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696121"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="f960c-102">ICorDebugFunction::GetToken (Método)</span><span class="sxs-lookup"><span data-stu-id="f960c-102">ICorDebugFunction::GetToken Method</span></span>

<span data-ttu-id="f960c-103">Obtiene el símbolo (token) de metadatos de esta función.</span><span class="sxs-lookup"><span data-stu-id="f960c-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f960c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f960c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f960c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f960c-105">Parameters</span></span>  

 `pMethodDef`  
 <span data-ttu-id="f960c-106">enuncia Un puntero a un `mdMethodDef` token que hace referencia a los metadatos de esta función.</span><span class="sxs-lookup"><span data-stu-id="f960c-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f960c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f960c-107">Requirements</span></span>  

 <span data-ttu-id="f960c-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f960c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f960c-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f960c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f960c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f960c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f960c-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f960c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
