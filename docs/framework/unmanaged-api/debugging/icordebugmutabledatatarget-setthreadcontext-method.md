---
title: ICorDebugMutableDataTarget::SetThreadContext (método)
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 558a1ee2eb0ac06213c2ebcebbd5595b69ecc43e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695715"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="4383d-102">ICorDebugMutableDataTarget::SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="4383d-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="4383d-103">Establece el contexto (valores de registro) para un subproceso.</span><span class="sxs-lookup"><span data-stu-id="4383d-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4383d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4383d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4383d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4383d-105">Parameters</span></span>  

 `dwThreadID`  
 <span data-ttu-id="4383d-106">[in] Identificador de subproceso definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4383d-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="4383d-107">[in] Tamaño del búfer `pContext` que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="4383d-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="4383d-108">[in] Puntero a los bytes que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="4383d-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4383d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4383d-109">Remarks</span></span>  

 <span data-ttu-id="4383d-110">El método `SetThreadContext` actualiza el contexto actual para el subproceso especificado por el argumento `dwThreadID` definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4383d-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="4383d-111">El formato del registro de contexto viene determinado por la plataforma indicada por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4383d-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="4383d-112">En Windows, se trata de una estructura de [contexto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="4383d-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4383d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4383d-113">Requirements</span></span>  

 <span data-ttu-id="4383d-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4383d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4383d-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4383d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4383d-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4383d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4383d-117">**.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4383d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4383d-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4383d-118">See also</span></span>

- [<span data-ttu-id="4383d-119">Interfaz ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="4383d-119">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="4383d-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4383d-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
