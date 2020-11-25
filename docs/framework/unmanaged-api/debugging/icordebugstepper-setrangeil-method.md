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
ms.openlocfilehash: 5a27f155021661022b27022bbb252e00dfa67255
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698785"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="1621f-102">ICorDebugStepper::SetRangeIL (Método)</span><span class="sxs-lookup"><span data-stu-id="1621f-102">ICorDebugStepper::SetRangeIL Method</span></span>

<span data-ttu-id="1621f-103">Establece un valor que especifica si las llamadas a [ICorDebugStepper:: steprange (](icordebugstepper-steprange-method.md) pasan valores de argumento relativos al código nativo o al código del lenguaje intermedio de Microsoft (MSIL) del método que se está ejecutando paso a paso.</span><span class="sxs-lookup"><span data-stu-id="1621f-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1621f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1621f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1621f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1621f-105">Parameters</span></span>  

 `bIL`  
 <span data-ttu-id="1621f-106">de Establézcalo en `true` para especificar que los intervalos son relativos al código MSIL.</span><span class="sxs-lookup"><span data-stu-id="1621f-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="1621f-107">Establézcalo en `false` para especificar que los intervalos son relativos al código nativo.</span><span class="sxs-lookup"><span data-stu-id="1621f-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="1621f-108">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="1621f-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1621f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1621f-109">Requirements</span></span>  

 <span data-ttu-id="1621f-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1621f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1621f-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1621f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1621f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1621f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1621f-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1621f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
