---
description: 'Más información sobre: ICorDebugILFrame2:: Remapfunction ((método)'
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
ms.openlocfilehash: d8a6c7f966488e7b74a9661e3a18b5248df7400b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791301"
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="1c528-103">ICorDebugILFrame2::RemapFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="1c528-103">ICorDebugILFrame2::RemapFunction Method</span></span>

<span data-ttu-id="1c528-104">Reasigna una función editada especificando el nuevo desplazamiento del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="1c528-104">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c528-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c528-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c528-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c528-106">Parameters</span></span>  

 `newILOffset`  
 <span data-ttu-id="1c528-107">de Nuevo desplazamiento de MSIL del marco de pila en el que se debe colocar el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="1c528-107">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="1c528-108">Este valor debe ser un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="1c528-108">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="1c528-109">Es responsabilidad del autor de la llamada garantizar la validez de este valor.</span><span class="sxs-lookup"><span data-stu-id="1c528-109">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="1c528-110">Por ejemplo, el desplazamiento de MSIL no es válido si está fuera de los límites de la función.</span><span class="sxs-lookup"><span data-stu-id="1c528-110">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c528-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1c528-111">Remarks</span></span>  

 <span data-ttu-id="1c528-112">Cuando se ha editado la función de un fotograma, el depurador puede llamar al `RemapFunction` método para intercambiar en la versión más reciente de la función del fotograma para que se pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="1c528-112">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="1c528-113">La ejecución del código comenzará en el desplazamiento de MSIL especificado.</span><span class="sxs-lookup"><span data-stu-id="1c528-113">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1c528-114">Llamar a `RemapFunction` , como llamar a [ICorDebugILFrame:: setip](icordebugilframe-setip-method.md), invalidará inmediatamente todas las interfaces de depuración relacionadas con la generación de un seguimiento de la pila para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="1c528-114">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="1c528-115">Estas interfaces incluyen [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame (e ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="1c528-115">These interfaces include [ICorDebugChain](icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="1c528-116">`RemapFunction`Solo se puede llamar al método en el contexto del marco actual y solo en uno de los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="1c528-116">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
- <span data-ttu-id="1c528-117">Después de la recepción de una devolución de llamada [ICorDebugManagedCallback2:: functionremapopportunity (](icordebugmanagedcallback2-functionremapopportunity-method.md) que todavía no se ha continuado.</span><span class="sxs-lookup"><span data-stu-id="1c528-117">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
- <span data-ttu-id="1c528-118">Mientras se detiene la ejecución del código debido a un evento [ICorDebugManagedCallback:: editandcontinueremap (](icordebugmanagedcallback-editandcontinueremap-method.md) para este marco.</span><span class="sxs-lookup"><span data-stu-id="1c528-118">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c528-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c528-119">Requirements</span></span>  

 <span data-ttu-id="1c528-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c528-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c528-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c528-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c528-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c528-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c528-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c528-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
