---
title: ICorDebugMutableDataTarget::ContinueStatusChanged (método)
ms.date: 03/30/2017
ms.assetid: 5a66d3f4-dd16-4d62-9dcc-0eab7041d894
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 52b5c63f35732655834768eb5b914406203d423c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135621"
---
# <a name="icordebugmutabledatatargetcontinuestatuschanged-method"></a><span data-ttu-id="c7379-102">ICorDebugMutableDataTarget::ContinueStatusChanged (método)</span><span class="sxs-lookup"><span data-stu-id="c7379-102">ICorDebugMutableDataTarget::ContinueStatusChanged Method</span></span>
<span data-ttu-id="c7379-103">Cambia el estado de continuación para el evento de depuración pendiente en el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="c7379-103">Changes the continuation status for the outstanding debug event on the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7379-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7379-104">Syntax</span></span>  
  
```  
HRESULT ContinueStatusChanged(  
   [in] DWORD dwThreadId,  
   [in] CORDB_CONTINUE_STATUS continueStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7379-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c7379-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="c7379-106">Identificador de subproceso definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c7379-106">The operating system-defined thread identifier.</span></span>  
  
 `continueStatus`  
 <span data-ttu-id="c7379-107">Valor [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) que representa el nuevo estado de continuación solicitado.</span><span class="sxs-lookup"><span data-stu-id="c7379-107">A [COREDB_CONTINUE_STATUS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the new requested continuation status.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7379-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c7379-108">Remarks</span></span>  
 <span data-ttu-id="c7379-109">El depurador llama al método `ContinueStatusChanged` cuando llama a un método ICorDebug que requiere que el evento de depuración actual se trate de una manera potencialmente diferente al modo en que se suele tratar.</span><span class="sxs-lookup"><span data-stu-id="c7379-109">The debugger calls the `ContinueStatusChanged` method when it calls an ICorDebug method that requires the current debug event to be handled in a way that is potentially different from the way in which it normally would be handled.</span></span> <span data-ttu-id="c7379-110">Por ejemplo, si hay una excepción pendiente y el depurador solicita una operación que cancelará la excepción (como [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) o `FuncEval`), esta API se usa para solicitar que se cancele la excepción.</span><span class="sxs-lookup"><span data-stu-id="c7379-110">For example, if there is an outstanding exception, and the debugger requests an operation that would cancel the exception (such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or `FuncEval`), this API is used to request that the exception be cancelled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7379-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c7379-111">Requirements</span></span>  
 <span data-ttu-id="c7379-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7379-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7379-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7379-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7379-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7379-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c7379-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c7379-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c7379-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7379-116">See also</span></span>

- [<span data-ttu-id="c7379-117">Interfaz ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="c7379-117">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="c7379-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c7379-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
