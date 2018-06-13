---
title: ICorDebugMutableDataTarget::SetThreadContext (método)
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05f0c0d23b4885f2d6fd351fdf845a25c899228e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418423"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="c0c5e-102">ICorDebugMutableDataTarget::SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="c0c5e-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="c0c5e-103">Establece el contexto (valores de registro) para un subproceso.</span><span class="sxs-lookup"><span data-stu-id="c0c5e-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0c5e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0c5e-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0c5e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0c5e-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="c0c5e-106">[in] Identificador de subproceso definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c0c5e-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c0c5e-107">[in] Tamaño del búfer `pContext` que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="c0c5e-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="c0c5e-108">[in] Puntero a los bytes que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="c0c5e-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0c5e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0c5e-109">Remarks</span></span>  
 <span data-ttu-id="c0c5e-110">El método `SetThreadContext` actualiza el contexto actual para el subproceso especificado por el argumento `dwThreadID` definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c0c5e-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="c0c5e-111">El formato de registro de contexto que viene determinado por la plataforma que indica la [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="c0c5e-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="c0c5e-112">En Windows, se trata de un [contexto](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="c0c5e-112">On Windows, this is a [CONTEXT](http://msdn.microsoft.com/library/windows/desktop/ms679284.aspx) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0c5e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0c5e-113">Requirements</span></span>  
 <span data-ttu-id="c0c5e-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0c5e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0c5e-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0c5e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0c5e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0c5e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0c5e-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0c5e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c5e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0c5e-118">See Also</span></span>  
 [<span data-ttu-id="c0c5e-119">ICorDebugMutableDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0c5e-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="c0c5e-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c0c5e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
