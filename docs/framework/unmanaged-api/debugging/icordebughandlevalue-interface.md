---
title: ICorDebugHandleValue Interfaz1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed6ba8a738b4086b9150e0a1c7b300a519fa3092
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419112"
---
# <a name="icordebughandlevalue-interface1"></a><span data-ttu-id="117f7-102">ICorDebugHandleValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="117f7-102">ICorDebugHandleValue Interface1</span></span>
<span data-ttu-id="117f7-103">Una subclase de ICorDebugReferenceValue que representa un valor de referencia a la que el depurador ha creado un identificador para la recolección.</span><span class="sxs-lookup"><span data-stu-id="117f7-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="117f7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="117f7-104">Methods</span></span>  
  
|<span data-ttu-id="117f7-105">Método</span><span class="sxs-lookup"><span data-stu-id="117f7-105">Method</span></span>|<span data-ttu-id="117f7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="117f7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="117f7-107">Dispose (método)</span><span class="sxs-lookup"><span data-stu-id="117f7-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="117f7-108">Libera el identificador hace referencia este `ICorDebugHandleValue` objeto sin liberar explícitamente el puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="117f7-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="117f7-109">GetHandleType (método)</span><span class="sxs-lookup"><span data-stu-id="117f7-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="117f7-110">Obtiene un valor de CorDebugHandleType que describe el tipo de identificador que hace referencia esta `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="117f7-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="117f7-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="117f7-111">Remarks</span></span>  
 <span data-ttu-id="117f7-112">Un `ICorDebugReferenceValue` objeto se invalida mediante una interrupción en la ejecución del código depurado.</span><span class="sxs-lookup"><span data-stu-id="117f7-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="117f7-113">Un `ICorDebugHandleValue` mantiene su referencia a través de interrupciones y continuaciones, hasta que se libere explícitamente.</span><span class="sxs-lookup"><span data-stu-id="117f7-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="117f7-114">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="117f7-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="117f7-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="117f7-115">Requirements</span></span>  
 <span data-ttu-id="117f7-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="117f7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="117f7-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="117f7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="117f7-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="117f7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="117f7-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="117f7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="117f7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="117f7-120">See Also</span></span>  
 [<span data-ttu-id="117f7-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="117f7-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
