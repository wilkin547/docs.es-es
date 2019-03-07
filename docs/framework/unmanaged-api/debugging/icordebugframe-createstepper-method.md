---
title: ICorDebugFrame::CreateStepper (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3fe3cbc4bad83496bcc58aaea60e6724b1d1f06c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466393"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="ec5df-102">ICorDebugFrame::CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="ec5df-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="ec5df-103">Obtiene un motor paso a paso que permite al depurador realizar operaciones de ejecución paso a paso en relación con este ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="ec5df-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec5df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec5df-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec5df-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec5df-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="ec5df-106">[out] Un puntero a la dirección de un objeto ICorDebugStepper que permite al depurador realizar operaciones de ejecución paso a paso en relación con el marco actual.</span><span class="sxs-lookup"><span data-stu-id="ec5df-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec5df-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec5df-107">Remarks</span></span>  
 <span data-ttu-id="ec5df-108">Si el marco no está activo, el objeto de motor paso a paso normalmente tendrá que volver al fotograma antes de que finalice el paso.</span><span class="sxs-lookup"><span data-stu-id="ec5df-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec5df-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec5df-109">Requirements</span></span>  
 <span data-ttu-id="ec5df-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec5df-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec5df-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec5df-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec5df-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec5df-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec5df-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec5df-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
