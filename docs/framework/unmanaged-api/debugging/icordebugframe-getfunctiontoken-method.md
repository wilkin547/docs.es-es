---
title: ICorDebugFrame::GetFunctionToken (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
ms.openlocfilehash: 6e214131aeb2d6d17ea4b0a730b5fc77428a7ca8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213691"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="03a22-102">ICorDebugFrame::GetFunctionToken (Método)</span><span class="sxs-lookup"><span data-stu-id="03a22-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="03a22-103">Obtiene el símbolo (token) de metadatos para la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="03a22-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a22-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03a22-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03a22-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03a22-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="03a22-106">enuncia Un puntero a un `mdMethodDef` token que hace referencia a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="03a22-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03a22-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03a22-107">Requirements</span></span>  
 <span data-ttu-id="03a22-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03a22-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03a22-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03a22-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03a22-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03a22-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03a22-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03a22-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
