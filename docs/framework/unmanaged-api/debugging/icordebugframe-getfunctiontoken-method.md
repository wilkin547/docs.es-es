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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bb4331b1c55cbda818866c5ff08f9bacd3ebae0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413990"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="75eb2-102">ICorDebugFrame::GetFunctionToken (Método)</span><span class="sxs-lookup"><span data-stu-id="75eb2-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="75eb2-103">Obtiene el token de metadatos para la función que contiene el código asociado con este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="75eb2-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75eb2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75eb2-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75eb2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75eb2-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="75eb2-106">[out] Un puntero a un `mdMethodDef` símbolo (token) que hace referencia a los metadatos de la función.</span><span class="sxs-lookup"><span data-stu-id="75eb2-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75eb2-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75eb2-107">Requirements</span></span>  
 <span data-ttu-id="75eb2-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75eb2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75eb2-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75eb2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75eb2-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75eb2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75eb2-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75eb2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
