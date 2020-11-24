---
title: ICorDebugFrame::GetFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
ms.openlocfilehash: 9f9a6238057f56459eb8dca2375da412c3cd569d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690322"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="c58f2-102">ICorDebugFrame::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="c58f2-102">ICorDebugFrame::GetFunction Method</span></span>

<span data-ttu-id="c58f2-103">Obtiene la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="c58f2-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c58f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c58f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c58f2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c58f2-105">Parameters</span></span>  

 `ppFunction`  
 <span data-ttu-id="c58f2-106">enuncia Puntero a la dirección de un objeto ICorDebugFunction que representa la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="c58f2-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c58f2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c58f2-107">Remarks</span></span>  

 <span data-ttu-id="c58f2-108">El `GetFunction` método puede producir un error si el marco no está asociado a ninguna función determinada.</span><span class="sxs-lookup"><span data-stu-id="c58f2-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c58f2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c58f2-109">Requirements</span></span>  

 <span data-ttu-id="c58f2-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c58f2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c58f2-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c58f2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c58f2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c58f2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c58f2-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c58f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
