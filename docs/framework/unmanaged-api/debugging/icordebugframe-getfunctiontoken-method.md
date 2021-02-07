---
description: 'Más información sobre: ICorDebugFrame:: GetFunctionToken ((método)'
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
ms.openlocfilehash: c64bb8d59c8de03c3d8c667384ffe4118c996d8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692945"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="fad40-103">ICorDebugFrame::GetFunctionToken (Método)</span><span class="sxs-lookup"><span data-stu-id="fad40-103">ICorDebugFrame::GetFunctionToken Method</span></span>

<span data-ttu-id="fad40-104">Obtiene el símbolo (token) de metadatos para la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="fad40-104">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fad40-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fad40-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fad40-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fad40-106">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="fad40-107">enuncia Un puntero a un `mdMethodDef` token que hace referencia a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="fad40-107">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fad40-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fad40-108">Requirements</span></span>  

 <span data-ttu-id="fad40-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fad40-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fad40-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fad40-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fad40-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fad40-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fad40-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fad40-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
