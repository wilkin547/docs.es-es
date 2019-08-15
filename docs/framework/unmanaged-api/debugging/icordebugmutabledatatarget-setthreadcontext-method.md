---
title: ICorDebugMutableDataTarget::SetThreadContext (método)
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21a24b3ae3563db09f1f7e9229f388abf8de654c
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038312"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="96909-102">ICorDebugMutableDataTarget::SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="96909-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="96909-103">Establece el contexto (valores de registro) para un subproceso.</span><span class="sxs-lookup"><span data-stu-id="96909-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96909-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96909-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96909-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="96909-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="96909-106">[in] Identificador de subproceso definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="96909-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="96909-107">[in] Tamaño del búfer `pContext` que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="96909-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="96909-108">[in] Puntero a los bytes que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="96909-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96909-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96909-109">Remarks</span></span>  
 <span data-ttu-id="96909-110">El método `SetThreadContext` actualiza el contexto actual para el subproceso especificado por el argumento `dwThreadID` definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="96909-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="96909-111">El formato del registro de contexto viene determinado por la plataforma indicada por el método [ICorDebugDataTarget:: GetPlatform (](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="96909-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="96909-112">En Windows, se trata de una estructura de [contexto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="96909-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96909-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="96909-113">Requirements</span></span>  
 <span data-ttu-id="96909-114">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96909-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96909-115">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="96909-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96909-116">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96909-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96909-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96909-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96909-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="96909-118">See also</span></span>

- [<span data-ttu-id="96909-119">ICorDebugMutableDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="96909-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="96909-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="96909-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
