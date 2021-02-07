---
description: 'Más información acerca de: ICorDebugStepper:: SetRangeIL ((método)'
title: ICorDebugStepper::SetRangeIL (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
ms.openlocfilehash: 8bccaf8ba8e52a7fe94555fa99b1c3cf92842efe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717722"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="2d114-103">ICorDebugStepper::SetRangeIL (Método)</span><span class="sxs-lookup"><span data-stu-id="2d114-103">ICorDebugStepper::SetRangeIL Method</span></span>

<span data-ttu-id="2d114-104">Establece un valor que especifica si las llamadas a [ICorDebugStepper:: steprange (](icordebugstepper-steprange-method.md) pasan valores de argumento relativos al código nativo o al código del lenguaje intermedio de Microsoft (MSIL) del método que se está ejecutando paso a paso.</span><span class="sxs-lookup"><span data-stu-id="2d114-104">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d114-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d114-105">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d114-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d114-106">Parameters</span></span>  

 `bIL`  
 <span data-ttu-id="2d114-107">de Establézcalo en `true` para especificar que los intervalos son relativos al código MSIL.</span><span class="sxs-lookup"><span data-stu-id="2d114-107">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="2d114-108">Establézcalo en `false` para especificar que los intervalos son relativos al código nativo.</span><span class="sxs-lookup"><span data-stu-id="2d114-108">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="2d114-109">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="2d114-109">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d114-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d114-110">Requirements</span></span>  

 <span data-ttu-id="2d114-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d114-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d114-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d114-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d114-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d114-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d114-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d114-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
