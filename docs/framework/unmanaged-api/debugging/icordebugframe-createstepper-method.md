---
description: 'Más información sobre: ICorDebugFrame:: Createstepper ((método)'
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
ms.openlocfilehash: 394418b89fd7a1c780a5bc33b97b8ef40bab8df2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693101"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="6af9c-103">ICorDebugFrame::CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="6af9c-103">ICorDebugFrame::CreateStepper Method</span></span>

<span data-ttu-id="6af9c-104">Obtiene un stepper que permite al depurador realizar operaciones de ejecución de paso en relación con este ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="6af9c-104">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6af9c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6af9c-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6af9c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6af9c-106">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="6af9c-107">enuncia Puntero a la dirección de un objeto ICorDebugStepper que permite al depurador realizar operaciones de ejecución de paso en relación con el marco actual.</span><span class="sxs-lookup"><span data-stu-id="6af9c-107">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6af9c-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6af9c-108">Remarks</span></span>  

 <span data-ttu-id="6af9c-109">Si el marco no está activo, el objeto stepper normalmente tendrá que volver al marco antes de que se complete el paso.</span><span class="sxs-lookup"><span data-stu-id="6af9c-109">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6af9c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6af9c-110">Requirements</span></span>  

 <span data-ttu-id="6af9c-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6af9c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6af9c-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6af9c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6af9c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6af9c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6af9c-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6af9c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
