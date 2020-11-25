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
ms.openlocfilehash: 5eb6299526d69624056961cfb7f0387ff8f873cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725032"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="d4779-102">ICorDebugILFrame2::RemapFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="d4779-102">ICorDebugILFrame2::RemapFunction Method</span></span>

<span data-ttu-id="d4779-103">Reasigna una función editada especificando el nuevo desplazamiento del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="d4779-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4779-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4779-104">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4779-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4779-105">Parameters</span></span>  

 `newILOffset`  
 <span data-ttu-id="d4779-106">de Nuevo desplazamiento de MSIL del marco de pila en el que se debe colocar el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="d4779-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="d4779-107">Este valor debe ser un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="d4779-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="d4779-108">Es responsabilidad del autor de la llamada garantizar la validez de este valor.</span><span class="sxs-lookup"><span data-stu-id="d4779-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="d4779-109">Por ejemplo, el desplazamiento de MSIL no es válido si está fuera de los límites de la función.</span><span class="sxs-lookup"><span data-stu-id="d4779-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4779-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4779-110">Remarks</span></span>  

 <span data-ttu-id="d4779-111">Cuando se ha editado la función de un fotograma, el depurador puede llamar al `RemapFunction` método para intercambiar en la versión más reciente de la función del fotograma para que se pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d4779-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="d4779-112">La ejecución del código comenzará en el desplazamiento de MSIL especificado.</span><span class="sxs-lookup"><span data-stu-id="d4779-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4779-113">Llamar a `RemapFunction` , como llamar a [ICorDebugILFrame:: setip](icordebugilframe-setip-method.md), invalidará inmediatamente todas las interfaces de depuración relacionadas con la generación de un seguimiento de la pila para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="d4779-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="d4779-114">Estas interfaces incluyen [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame (e ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="d4779-114">These interfaces include [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="d4779-115">`RemapFunction`Solo se puede llamar al método en el contexto del marco actual y solo en uno de los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="d4779-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="d4779-116">Después de la recepción de una devolución de llamada [ICorDebugManagedCallback2:: functionremapopportunity (](icordebugmanagedcallback2-functionremapopportunity-method.md) que todavía no se ha continuado.</span><span class="sxs-lookup"><span data-stu-id="d4779-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="d4779-117">Mientras se detiene la ejecución del código debido a un evento [ICorDebugManagedCallback:: editandcontinueremap (](icordebugmanagedcallback-editandcontinueremap-method.md) para este marco.</span><span class="sxs-lookup"><span data-stu-id="d4779-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4779-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4779-118">Requirements</span></span>  

 <span data-ttu-id="d4779-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4779-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4779-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4779-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4779-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4779-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4779-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4779-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
