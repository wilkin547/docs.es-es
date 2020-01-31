---
title: Interfaz ICorDebugHandleValue
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
ms.openlocfilehash: 406468fc6e2b68e8c8e1dfbd0f0f18cce3f013ab
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794458"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="c2b54-102">Interfaz ICorDebugHandleValue</span><span class="sxs-lookup"><span data-stu-id="c2b54-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="c2b54-103">Subclase de ICorDebugReferenceValue que representa un valor de referencia en el que el depurador ha creado un identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c2b54-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2b54-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c2b54-104">Methods</span></span>  
  
|<span data-ttu-id="c2b54-105">Método</span><span class="sxs-lookup"><span data-stu-id="c2b54-105">Method</span></span>|<span data-ttu-id="c2b54-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2b54-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2b54-107">Dispose (método)</span><span class="sxs-lookup"><span data-stu-id="c2b54-107">Dispose Method</span></span>](icordebughandlevalue-dispose-method.md)|<span data-ttu-id="c2b54-108">Libera el identificador al que hace referencia este objeto `ICorDebugHandleValue` sin liberar explícitamente el puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="c2b54-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="c2b54-109">GetHandleType (método)</span><span class="sxs-lookup"><span data-stu-id="c2b54-109">GetHandleType Method</span></span>](icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="c2b54-110">Obtiene un valor CorDebugHandleType (que describe el tipo de identificador al que hace referencia este `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="c2b54-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2b54-111">Notas</span><span class="sxs-lookup"><span data-stu-id="c2b54-111">Remarks</span></span>  
 <span data-ttu-id="c2b54-112">Un objeto `ICorDebugReferenceValue` invalidado por una interrupción en la ejecución de código depurado.</span><span class="sxs-lookup"><span data-stu-id="c2b54-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="c2b54-113">Un `ICorDebugHandleValue` mantiene su referencia a través de saltos y continuaciones hasta que se libera explícitamente.</span><span class="sxs-lookup"><span data-stu-id="c2b54-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c2b54-114">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c2b54-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2b54-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c2b54-115">Requirements</span></span>  
 <span data-ttu-id="c2b54-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2b54-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2b54-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2b54-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2b54-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2b54-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2b54-119">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2b54-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b54-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2b54-120">See also</span></span>

- [<span data-ttu-id="c2b54-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c2b54-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
