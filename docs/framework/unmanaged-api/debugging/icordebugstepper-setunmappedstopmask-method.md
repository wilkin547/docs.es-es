---
title: ICorDebugStepper::SetUnmappedStopMask (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
ms.openlocfilehash: ef458fda8e8b7e75f92a4b3c06eabec106180d23
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379261"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="00242-102">ICorDebugStepper::SetUnmappedStopMask (Método)</span><span class="sxs-lookup"><span data-stu-id="00242-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="00242-103">Establece un valor que especifica el tipo de código no asignado en el que se detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="00242-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00242-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00242-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00242-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00242-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="00242-106">de Un valor de la enumeración Cordebugunmappedstop (que especifica el tipo de código no asignado en el que el depurador detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="00242-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="00242-107">El valor predeterminado es STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="00242-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="00242-108">El valor STOP_UNMANAGED solo es válido con la depuración de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="00242-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00242-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="00242-109">Remarks</span></span>  
 <span data-ttu-id="00242-110">Cuando el depurador encuentra una compilación Just-in-Time (JIT) que no tiene ninguna asignación correspondiente al lenguaje intermedio de Microsoft (MSIL), detiene la ejecución si se ha establecido la marca que especifica el tipo de código no asignado; de lo contrario, la ejecución continuará de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="00242-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="00242-111">Si el depurador no usa un stepper para entrar en un método, no tendrá que pasar por el código sin asignar.</span><span class="sxs-lookup"><span data-stu-id="00242-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00242-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00242-112">Requirements</span></span>  
 <span data-ttu-id="00242-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00242-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00242-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00242-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00242-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00242-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00242-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00242-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
