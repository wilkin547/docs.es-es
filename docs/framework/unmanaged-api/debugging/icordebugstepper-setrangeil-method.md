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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 610225708bf990850fce73d6d7ff66c556e24e5d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760592"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="59561-102">ICorDebugStepper::SetRangeIL (Método)</span><span class="sxs-lookup"><span data-stu-id="59561-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="59561-103">Establece un valor que especifica si las llamadas a [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pasar un argumento código MSIL (lenguaje) del método que se está ejecutando paso intermedio de valores que son relativos al código nativo o en relación con Microsoft a través de.</span><span class="sxs-lookup"><span data-stu-id="59561-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59561-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59561-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59561-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59561-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="59561-106">[in] Establecido en `true` para especificar que los intervalos son relativos al código MSIL.</span><span class="sxs-lookup"><span data-stu-id="59561-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="59561-107">Establecido en `false` para especificar que los intervalos son relativos al código nativo.</span><span class="sxs-lookup"><span data-stu-id="59561-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="59561-108">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="59561-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59561-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59561-109">Requirements</span></span>  
 <span data-ttu-id="59561-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59561-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59561-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59561-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59561-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59561-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59561-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59561-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
