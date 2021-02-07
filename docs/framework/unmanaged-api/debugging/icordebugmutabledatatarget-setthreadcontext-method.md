---
description: 'Más información sobre: ICorDebugMutableDataTarget:: SetThreadContext (método)'
title: ICorDebugMutableDataTarget::SetThreadContext (método)
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 4674df92b72b44e19eff663c9a17dd8ca4b5a1b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722482"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="c0d40-103">ICorDebugMutableDataTarget::SetThreadContext (método)</span><span class="sxs-lookup"><span data-stu-id="c0d40-103">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="c0d40-104">Establece el contexto (valores de registro) para un subproceso.</span><span class="sxs-lookup"><span data-stu-id="c0d40-104">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d40-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0d40-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0d40-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0d40-106">Parameters</span></span>  

 `dwThreadID`  
 <span data-ttu-id="c0d40-107">[in] Identificador de subproceso definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c0d40-107">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c0d40-108">[in] Tamaño del búfer `pContext` que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="c0d40-108">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="c0d40-109">[in] Puntero a los bytes que se van a escribir.</span><span class="sxs-lookup"><span data-stu-id="c0d40-109">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0d40-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c0d40-110">Remarks</span></span>  

 <span data-ttu-id="c0d40-111">El método `SetThreadContext` actualiza el contexto actual para el subproceso especificado por el argumento `dwThreadID` definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c0d40-111">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="c0d40-112">El formato del registro de contexto viene determinado por la plataforma indicada por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c0d40-112">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="c0d40-113">En Windows, se trata de una estructura de [contexto](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .</span><span class="sxs-lookup"><span data-stu-id="c0d40-113">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0d40-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0d40-114">Requirements</span></span>  

 <span data-ttu-id="c0d40-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0d40-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0d40-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0d40-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0d40-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0d40-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0d40-118">**.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0d40-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d40-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0d40-119">See also</span></span>

- [<span data-ttu-id="c0d40-120">Interfaz ICorDebugMutableDataTarget</span><span class="sxs-lookup"><span data-stu-id="c0d40-120">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="c0d40-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c0d40-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
