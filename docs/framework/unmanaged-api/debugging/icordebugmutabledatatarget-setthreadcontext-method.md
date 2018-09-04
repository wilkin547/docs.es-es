---
title: ICorDebugMutableDataTarget::SetThreadContext (método)
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3826bacb935652a282eac359170d9b93518e5cd
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509154"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="a3aaf-102">ICorDebugMutableDataTarget::SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="a3aaf-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="a3aaf-103">Establece el contexto (valores de registro) para un subproceso.</span><span class="sxs-lookup"><span data-stu-id="a3aaf-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3aaf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3aaf-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3aaf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a3aaf-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="a3aaf-106">[in] Identificador de subproceso definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a3aaf-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a3aaf-107">[in] Tamaño del búfer `pContext` que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="a3aaf-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="a3aaf-108">[in] Puntero a los bytes que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="a3aaf-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3aaf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a3aaf-109">Remarks</span></span>  
 <span data-ttu-id="a3aaf-110">El método `SetThreadContext` actualiza el contexto actual para el subproceso especificado por el argumento `dwThreadID` definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a3aaf-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="a3aaf-111">El formato del registro de contexto viene determinada por la plataforma que indica la [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a3aaf-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="a3aaf-112">En Windows, se trata de un [contexto](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) estructura.</span><span class="sxs-lookup"><span data-stu-id="a3aaf-112">On Windows, this is a [CONTEXT](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3aaf-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3aaf-113">Requirements</span></span>  
 <span data-ttu-id="a3aaf-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3aaf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3aaf-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3aaf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3aaf-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3aaf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3aaf-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3aaf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3aaf-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3aaf-118">See Also</span></span>  
 [<span data-ttu-id="a3aaf-119">ICorDebugMutableDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3aaf-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 [<span data-ttu-id="a3aaf-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a3aaf-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
