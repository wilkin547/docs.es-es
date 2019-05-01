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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995844"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="a0567-102">ICorDebugFrame::GetFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="a0567-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="a0567-103">Obtiene la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="a0567-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0567-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0567-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0567-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a0567-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="a0567-106">[out] Un puntero a la dirección de un objeto ICorDebugFunction que representa la función que contiene el código asociado a este marco de pila.</span><span class="sxs-lookup"><span data-stu-id="a0567-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0567-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0567-107">Remarks</span></span>  
 <span data-ttu-id="a0567-108">El `GetFunction` método puede producir un error si el marco no está asociado con ninguna función en particular.</span><span class="sxs-lookup"><span data-stu-id="a0567-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0567-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a0567-109">Requirements</span></span>  
 <span data-ttu-id="a0567-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0567-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0567-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0567-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0567-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0567-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0567-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0567-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
