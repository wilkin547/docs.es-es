---
title: ICorDebugHandleValue (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
ms.openlocfilehash: 94472e84b73cdffe09505088b1e7fbc20a209bc3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138476"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="f130e-102">ICorDebugHandleValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f130e-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="f130e-103">Subclase de ICorDebugReferenceValue que representa un valor de referencia en el que el depurador ha creado un identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="f130e-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f130e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f130e-104">Methods</span></span>  
  
|<span data-ttu-id="f130e-105">Método</span><span class="sxs-lookup"><span data-stu-id="f130e-105">Method</span></span>|<span data-ttu-id="f130e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f130e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f130e-107">Dispose (método)</span><span class="sxs-lookup"><span data-stu-id="f130e-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="f130e-108">Libera el identificador al que hace referencia este objeto `ICorDebugHandleValue` sin liberar explícitamente el puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="f130e-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="f130e-109">GetHandleType (método)</span><span class="sxs-lookup"><span data-stu-id="f130e-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="f130e-110">Obtiene un valor CorDebugHandleType (que describe el tipo de identificador al que hace referencia este `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="f130e-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f130e-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f130e-111">Remarks</span></span>  
 <span data-ttu-id="f130e-112">Un objeto `ICorDebugReferenceValue` invalidado por una interrupción en la ejecución de código depurado.</span><span class="sxs-lookup"><span data-stu-id="f130e-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="f130e-113">Un `ICorDebugHandleValue` mantiene su referencia a través de saltos y continuaciones hasta que se libera explícitamente.</span><span class="sxs-lookup"><span data-stu-id="f130e-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f130e-114">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f130e-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f130e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f130e-115">Requirements</span></span>  
 <span data-ttu-id="f130e-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f130e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f130e-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f130e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f130e-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f130e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f130e-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f130e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f130e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f130e-120">See also</span></span>

- [<span data-ttu-id="f130e-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f130e-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
