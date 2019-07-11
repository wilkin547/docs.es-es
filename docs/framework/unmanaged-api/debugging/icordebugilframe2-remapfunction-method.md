---
title: ICorDebugILFrame2::RemapFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdcc2eccbb24a92643415db8e5d267033ac1ca0a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758751"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="f46a3-102">ICorDebugILFrame2::RemapFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="f46a3-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="f46a3-103">Reasigna una función editada especificando el nuevo desplazamiento de lenguaje intermedio (MSIL) de Microsoft</span><span class="sxs-lookup"><span data-stu-id="f46a3-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f46a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f46a3-104">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f46a3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f46a3-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="f46a3-106">[in] Nuevo desplazamiento de MSIL del marco de pila en el que se debe colocar el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="f46a3-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="f46a3-107">Este valor debe ser un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="f46a3-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="f46a3-108">Es responsabilidad del llamador para garantizar la validez de este valor.</span><span class="sxs-lookup"><span data-stu-id="f46a3-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="f46a3-109">Por ejemplo, el desplazamiento MSIL no es válido si se encuentra fuera de los límites de la función.</span><span class="sxs-lookup"><span data-stu-id="f46a3-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f46a3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f46a3-110">Remarks</span></span>  
 <span data-ttu-id="f46a3-111">Cuando se ha editado la función de un marco, el depurador puede llamar a la `RemapFunction` método intercambiar en la versión más reciente de la función del marco, por lo que se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="f46a3-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="f46a3-112">Se iniciará la ejecución del código en el desplazamiento dado de MSIL.</span><span class="sxs-lookup"><span data-stu-id="f46a3-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f46a3-113">Una llamada a `RemapFunction`, como una llamada a [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), inmediatamente se invalidarán todas las interfaces de depuración que están relacionados con la generación de un seguimiento de pila del subproceso.</span><span class="sxs-lookup"><span data-stu-id="f46a3-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="f46a3-114">Estas interfaces incluyen [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame ICorDebugInternalFrame y ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="f46a3-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="f46a3-115">El `RemapFunction` método puede llamarse únicamente en el contexto del fotograma actual y sólo en uno de los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f46a3-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="f46a3-116">Después de recibir un [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) devolución de llamada que todavía no ha continuado.</span><span class="sxs-lookup"><span data-stu-id="f46a3-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="f46a3-117">Mientras se detiene la ejecución de código debido un [EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) eventos para este marco.</span><span class="sxs-lookup"><span data-stu-id="f46a3-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f46a3-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f46a3-118">Requirements</span></span>  
 <span data-ttu-id="f46a3-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f46a3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f46a3-120">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f46a3-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f46a3-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f46a3-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f46a3-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f46a3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
