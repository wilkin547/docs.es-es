---
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
ms.openlocfilehash: 88270cb73515cc1a671bfb3fb5c479697ad7b359
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137543"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="ab9ae-102">ICorDebugStepper::SetRangeIL (Método)</span><span class="sxs-lookup"><span data-stu-id="ab9ae-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="ab9ae-103">Establece un valor que especifica si las llamadas a [ICorDebugStepper:: steprange (](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pasan valores de argumento relativos al código nativo o al código del lenguaje intermedio de Microsoft (MSIL) del método que se está ejecutando paso a paso.</span><span class="sxs-lookup"><span data-stu-id="ab9ae-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab9ae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab9ae-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab9ae-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab9ae-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="ab9ae-106">de Establezca en `true` para especificar que los intervalos son relativos al código MSIL.</span><span class="sxs-lookup"><span data-stu-id="ab9ae-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="ab9ae-107">Establezca en `false` para especificar que los intervalos son relativos al código nativo.</span><span class="sxs-lookup"><span data-stu-id="ab9ae-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="ab9ae-108">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="ab9ae-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab9ae-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab9ae-109">Requirements</span></span>  
 <span data-ttu-id="ab9ae-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab9ae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab9ae-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab9ae-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab9ae-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab9ae-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab9ae-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab9ae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
