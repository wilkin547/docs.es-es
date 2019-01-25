---
title: ICorDebugMutableDataTarget::ContinueStatusChanged (método)
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9d70bb7b886556dbf87590e9f0717f1d161b0ee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559741"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="4edda-102">ICorDebugMutableDataTarget::ContinueStatusChanged (método)</span><span class="sxs-lookup"><span data-stu-id="4edda-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="4edda-103">Cambia el estado de continuación para el evento de depuración pendiente en el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="4edda-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4edda-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4edda-104">Syntax</span></span>  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4edda-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4edda-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="4edda-106">Identificador de subproceso definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4edda-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="4edda-107">Valor [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que representa el nuevo estado de continuación solicitado.</span><span class="sxs-lookup"><span data-stu-id="4edda-107">A [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4edda-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4edda-108">Remarks</span></span>  
 <span data-ttu-id="4edda-109">El depurador llama al método `ContinueStatusChanged` cuando llama a un método ICorDebug que requiere que el evento de depuración actual se trate de una manera potencialmente diferente al modo en que se suele tratar.</span><span class="sxs-lookup"><span data-stu-id="4edda-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="4edda-110">Por ejemplo, si hay una excepción pendiente y el depurador solicita una operación que cancelará la excepción (como [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o `FuncEval`), esta API se usa para solicitar que se cancele la excepción.</span><span class="sxs-lookup"><span data-stu-id="4edda-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4edda-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4edda-111">Requirements</span></span>  
 <span data-ttu-id="4edda-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4edda-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4edda-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4edda-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4edda-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4edda-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4edda-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4edda-115">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4edda-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4edda-116">See also</span></span>
- [<span data-ttu-id="4edda-117">ICorDebugMutableDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4edda-117">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="4edda-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4edda-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
