---
title: Interfaz ICorDebugMutableDataTarget
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
ms.openlocfilehash: 682e927388d3392d970338314f97d46c9e57e760
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139337"
---
# <a name="icordebugmutabledatatarget-interface"></a><span data-ttu-id="9551a-102">Interfaz ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="9551a-102">ICorDebugMutableDataTarget Interface</span></span>
<span data-ttu-id="9551a-103">Extiende la interfaz [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) para admitir destinos de datos mutables.</span><span class="sxs-lookup"><span data-stu-id="9551a-103">Extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9551a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9551a-104">Methods</span></span>  
  
|<span data-ttu-id="9551a-105">Método</span><span class="sxs-lookup"><span data-stu-id="9551a-105">Method</span></span>|<span data-ttu-id="9551a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9551a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9551a-107">ContinueStatusChanged (método)</span><span class="sxs-lookup"><span data-stu-id="9551a-107">ContinueStatusChanged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|<span data-ttu-id="9551a-108">Cambia el estado de continuación para el evento de depuración pendiente en el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="9551a-108">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>|  
|[<span data-ttu-id="9551a-109">SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="9551a-109">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|<span data-ttu-id="9551a-110">Establece el contexto (valores de registro) para un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9551a-110">Sets the context (register values) for a thread.</span></span>|  
|[<span data-ttu-id="9551a-111">WriteVirtual (método)</span><span class="sxs-lookup"><span data-stu-id="9551a-111">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|<span data-ttu-id="9551a-112">Escribe la memoria en el espacio de direcciones de procesos de destino.</span><span class="sxs-lookup"><span data-stu-id="9551a-112">Writes memory into the target process address space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9551a-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9551a-113">Remarks</span></span>  
 <span data-ttu-id="9551a-114">Esta extensión de la interfaz [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) se puede implementar mediante herramientas de depuración que deseen modificar el proceso de destino (por ejemplo, para realizar una depuración invasiva en directo).</span><span class="sxs-lookup"><span data-stu-id="9551a-114">This extension to the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface can be implemented by debugging tools that wish to modify the target process (for example, to perform live invasive debugging).</span></span>  
  
 <span data-ttu-id="9551a-115">Todos estos métodos son opcionales en el sentido de que, si no se implementa esta interfaz o en caso de error en las llamadas a estos métodos, no se pierde ninguna funcionalidad de depuración basada en una inspección principal.</span><span class="sxs-lookup"><span data-stu-id="9551a-115">All of these methods are optional in the sense that no core inspection-based debugging functionality is lost by not implementing this interface or by the failure of calls to these methods.</span></span>  <span data-ttu-id="9551a-116">Cualquier error `HRESULT` de estos métodos se propaga como el `HRESULT` de la llamada al método ICorDebug.</span><span class="sxs-lookup"><span data-stu-id="9551a-116">Any failure `HRESULT` from these methods will propagate out as the `HRESULT` from the ICorDebug method call.</span></span>  
  
 <span data-ttu-id="9551a-117">Tenga en cuenta que una sola llamada al método ICorDebug puede provocar diversas mutaciones y que no hay ningún mecanismo que garantice que las mutaciones relativas se aplican de forma transaccional (todas-o-ninguna).</span><span class="sxs-lookup"><span data-stu-id="9551a-117">Note that a single ICorDebug method call may result in multiple mutations, and that there is no mechanism for ensuring related mutations are applied transactionally (all-or-none).</span></span>  <span data-ttu-id="9551a-118">Es decir, si una mutación produce un error después de que otras mutaciones (para la misma llamada ICorDebug) se hayan realizado correctamente, el proceso de destino podría quedarse en un estado incoherente y la depuración podría dejar de ser confiable.</span><span class="sxs-lookup"><span data-stu-id="9551a-118">This means that if a mutation fails after others (for the same ICorDebug call) have succeeded, the target process may be left in an inconsistent state and debugging may become unreliable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9551a-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9551a-119">Requirements</span></span>  
 <span data-ttu-id="9551a-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9551a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9551a-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9551a-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9551a-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9551a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9551a-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9551a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9551a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9551a-124">See also</span></span>

- [<span data-ttu-id="9551a-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9551a-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9551a-126">Depuración</span><span class="sxs-lookup"><span data-stu-id="9551a-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
