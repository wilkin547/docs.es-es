---
description: 'Más información acerca de: ICorDebugHandleValue (interfaz)'
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
ms.openlocfilehash: 3bdb1f5668be283d8722c15f4779adfe4d7b3a2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692049"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="5c100-103">Interfaz ICorDebugHandleValue</span><span class="sxs-lookup"><span data-stu-id="5c100-103">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="5c100-104">Subclase de ICorDebugReferenceValue que representa un valor de referencia en el que el depurador ha creado un identificador para la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5c100-104">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5c100-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5c100-105">Methods</span></span>  
  
|<span data-ttu-id="5c100-106">Método</span><span class="sxs-lookup"><span data-stu-id="5c100-106">Method</span></span>|<span data-ttu-id="5c100-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c100-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5c100-108">Dispose (Método)</span><span class="sxs-lookup"><span data-stu-id="5c100-108">Dispose Method</span></span>](icordebughandlevalue-dispose-method.md)|<span data-ttu-id="5c100-109">Libera el identificador al que hace referencia este `ICorDebugHandleValue` objeto sin liberar explícitamente el puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="5c100-109">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="5c100-110">Método GetHandleType</span><span class="sxs-lookup"><span data-stu-id="5c100-110">GetHandleType Method</span></span>](icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="5c100-111">Obtiene un valor CorDebugHandleType (que describe el tipo de identificador al que hace referencia este `ICorDebugHandleValue` .</span><span class="sxs-lookup"><span data-stu-id="5c100-111">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c100-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5c100-112">Remarks</span></span>  

 <span data-ttu-id="5c100-113">Un `ICorDebugReferenceValue` objeto queda invalidado por una interrupción en la ejecución de código depurado.</span><span class="sxs-lookup"><span data-stu-id="5c100-113">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="5c100-114">Un `ICorDebugHandleValue` mantiene su referencia mediante saltos y continuaciones hasta que se libera explícitamente.</span><span class="sxs-lookup"><span data-stu-id="5c100-114">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5c100-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5c100-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c100-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c100-116">Requirements</span></span>  

 <span data-ttu-id="5c100-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c100-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c100-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c100-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c100-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c100-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c100-120">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c100-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c100-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c100-121">See also</span></span>

- [<span data-ttu-id="5c100-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5c100-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
