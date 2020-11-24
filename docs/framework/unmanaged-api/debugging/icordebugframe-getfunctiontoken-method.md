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
ms.openlocfilehash: 3430c5062bd5633e1178226974b7358783192e51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675989"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="0f88e-102">ICorDebugFrame::GetFunctionToken (Método)</span><span class="sxs-lookup"><span data-stu-id="0f88e-102">ICorDebugFrame::GetFunctionToken Method</span></span>

<span data-ttu-id="0f88e-103">Obtiene el símbolo (token) de metadatos para la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="0f88e-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f88e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f88e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f88e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f88e-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="0f88e-106">enuncia Un puntero a un `mdMethodDef` token que hace referencia a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="0f88e-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f88e-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f88e-107">Requirements</span></span>  

 <span data-ttu-id="0f88e-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f88e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f88e-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f88e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f88e-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f88e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f88e-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f88e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
