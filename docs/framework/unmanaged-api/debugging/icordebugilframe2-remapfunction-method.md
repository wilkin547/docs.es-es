---
title: "ICorDebugILFrame2::RemapFunction (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2.RemapFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9fed4759576d1b6d2fec1a5e9c1e36019e5944c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe2remapfunction-method"></a><span data-ttu-id="38d68-102">ICorDebugILFrame2::RemapFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="38d68-102">ICorDebugILFrame2::RemapFunction Method</span></span>
<span data-ttu-id="38d68-103">Reasigna una función editada especificando el nuevo desplazamiento de lenguaje intermedio (MSIL) de Microsoft</span><span class="sxs-lookup"><span data-stu-id="38d68-103">Remaps an edited function by specifying the new Microsoft intermediate language (MSIL) offset</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d68-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38d68-104">Syntax</span></span>  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38d68-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="38d68-105">Parameters</span></span>  
 `newILOffset`  
 <span data-ttu-id="38d68-106">[in] Nuevo desplazamiento de MSIL del marco de pila en el que se debe colocar el puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="38d68-106">[in] The stack frame's new MSIL offset at which the instruction pointer should be placed.</span></span> <span data-ttu-id="38d68-107">Este valor debe ser un punto de secuencia.</span><span class="sxs-lookup"><span data-stu-id="38d68-107">This value must be a sequence point.</span></span>  
  
 <span data-ttu-id="38d68-108">Es responsabilidad del llamador para garantizar la validez de este valor.</span><span class="sxs-lookup"><span data-stu-id="38d68-108">It is the caller’s responsibility to ensure the validity of this value.</span></span> <span data-ttu-id="38d68-109">Por ejemplo, el desplazamiento MSIL no es válido si está fuera de los límites de la función.</span><span class="sxs-lookup"><span data-stu-id="38d68-109">For example, the MSIL offset is not valid if it is outside the bounds of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38d68-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38d68-110">Remarks</span></span>  
 <span data-ttu-id="38d68-111">Cuando se ha editado la función de un marco, el depurador puede llamar a la `RemapFunction` método intercambiar en la versión más reciente de la función del marco para que se pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="38d68-111">When a frame’s function has been edited, the debugger can call the `RemapFunction` method to swap in the latest version of the frame's function so it can be executed.</span></span> <span data-ttu-id="38d68-112">Se iniciará la ejecución del código en el desplazamiento dado de MSIL.</span><span class="sxs-lookup"><span data-stu-id="38d68-112">The code execution will begin at the given MSIL offset.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38d68-113">Al llamar a `RemapFunction`, como una llamada a [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), inmediatamente se invalidarán todas las interfaces de depuración que están relacionados con la generación de un seguimiento de pila para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="38d68-113">Calling `RemapFunction`, like calling [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), will immediately invalidate all debugging interfaces that are related to generating a stack trace for the thread.</span></span> <span data-ttu-id="38d68-114">Estas interfaces incluyen [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame y ICorDebugNativeFrame.</span><span class="sxs-lookup"><span data-stu-id="38d68-114">These interfaces include [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame, and ICorDebugNativeFrame.</span></span>  
  
 <span data-ttu-id="38d68-115">El `RemapFunction` método puede llamarse únicamente en el contexto del fotograma actual y sólo en uno de los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="38d68-115">The `RemapFunction` method can be called only in the context of the current frame, and only in one of the following cases:</span></span>  
  
-   <span data-ttu-id="38d68-116">Después de recibir un [ICorDebugManagedCallback2:: FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) devolución de llamada que todavía no ha continuado.</span><span class="sxs-lookup"><span data-stu-id="38d68-116">After receipt of a [ICorDebugManagedCallback2::FunctionRemapOpportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) callback that has not yet been continued.</span></span>  
  
-   <span data-ttu-id="38d68-117">Aunque la ejecución de código se detiene debido un [ICorDebugManagedCallback:: EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) eventos de este fotograma.</span><span class="sxs-lookup"><span data-stu-id="38d68-117">While code execution is stopped because of an [ICorDebugManagedCallback::EditAndContinueRemap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) event for this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38d68-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38d68-118">Requirements</span></span>  
 <span data-ttu-id="38d68-119">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38d68-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38d68-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38d68-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38d68-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38d68-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38d68-122">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38d68-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
