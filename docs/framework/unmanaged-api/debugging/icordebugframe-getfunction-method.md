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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a48396f8ef668cfe7755b2718180317b465793b6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475295"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="ce852-102">ICorDebugFrame::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="ce852-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="ce852-103">Obtiene la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="ce852-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce852-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce852-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce852-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce852-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="ce852-106">[out] Un puntero a la dirección de un objeto ICorDebugFunction que representa la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="ce852-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce852-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce852-107">Remarks</span></span>  
 <span data-ttu-id="ce852-108">El `GetFunction` método puede producir un error si el marco no está asociado con ninguna función en particular.</span><span class="sxs-lookup"><span data-stu-id="ce852-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce852-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce852-109">Requirements</span></span>  
 <span data-ttu-id="ce852-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce852-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce852-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce852-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce852-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce852-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce852-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce852-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
