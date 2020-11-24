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
ms.openlocfilehash: 5dfb64d0c440cbd2c8a8a65b2c18d78f02a7615e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679720"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="69004-102">ICorDebugFrame::CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="69004-102">ICorDebugFrame::CreateStepper Method</span></span>

<span data-ttu-id="69004-103">Obtiene un stepper que permite al depurador realizar operaciones de ejecución de paso en relación con este ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="69004-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69004-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69004-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69004-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69004-105">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="69004-106">enuncia Puntero a la dirección de un objeto ICorDebugStepper que permite al depurador realizar operaciones de ejecución de paso en relación con el marco actual.</span><span class="sxs-lookup"><span data-stu-id="69004-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69004-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69004-107">Remarks</span></span>  

 <span data-ttu-id="69004-108">Si el marco no está activo, el objeto stepper normalmente tendrá que volver al marco antes de que se complete el paso.</span><span class="sxs-lookup"><span data-stu-id="69004-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69004-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69004-109">Requirements</span></span>  

 <span data-ttu-id="69004-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69004-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69004-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69004-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69004-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69004-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69004-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69004-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
