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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0a273c54559e8e297e09740ba9c770ce12d72d1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760582"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="3cfaf-102">ICorDebugStepper::SetUnmappedStopMask (Método)</span><span class="sxs-lookup"><span data-stu-id="3cfaf-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="3cfaf-103">Establece un valor que especifica el tipo de código no asignado en el que se detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="3cfaf-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cfaf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cfaf-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cfaf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3cfaf-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="3cfaf-106">[in] Un valor de la enumeración CorDebugUnmappedStop que especifica el tipo de código no asignado en el que el depurador detendrá la ejecución.</span><span class="sxs-lookup"><span data-stu-id="3cfaf-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="3cfaf-107">El valor predeterminado es STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="3cfaf-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="3cfaf-108">El valor STOP_UNMANAGED sólo es válido con la depuración de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="3cfaf-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cfaf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3cfaf-109">Remarks</span></span>  
 <span data-ttu-id="3cfaf-110">Cuando el depurador encuentra la compilación just-in-time (JIT) que no tiene ninguna asignación correspondiente al lenguaje intermedio de Microsoft (MSIL), detiene la ejecución si se ha establecido la marca que especifica ese tipo de código no asignado; en caso contrario, ejecución paso a paso de forma transparente continúa.</span><span class="sxs-lookup"><span data-stu-id="3cfaf-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="3cfaf-111">Si el depurador no usa un motor paso a paso para especificar un método, a continuación, no necesariamente recorrerá paso a través de código no asignado.</span><span class="sxs-lookup"><span data-stu-id="3cfaf-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cfaf-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cfaf-112">Requirements</span></span>  
 <span data-ttu-id="3cfaf-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cfaf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cfaf-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cfaf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cfaf-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cfaf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cfaf-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cfaf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
