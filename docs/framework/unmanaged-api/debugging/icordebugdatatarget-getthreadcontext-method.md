---
title: "ICorDebugDataTarget::GetThreadContext (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 44543ca3546827b38643cab0e047032a96be9ea6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="e9caf-102">ICorDebugDataTarget::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="e9caf-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="e9caf-103">Devuelve el contexto del subproceso actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="e9caf-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9caf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9caf-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9caf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9caf-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="e9caf-106">[in] El identificador del subproceso cuyo contexto está va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="e9caf-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="e9caf-107">El identificador está definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e9caf-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="e9caf-108">[in] Una combinación bit a bit de marcas dependientes de la plataforma que indican qué partes del contexto se deben leer.</span><span class="sxs-lookup"><span data-stu-id="e9caf-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e9caf-109">[in] Tamaño de `pContext`.</span><span class="sxs-lookup"><span data-stu-id="e9caf-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="e9caf-110">[out] El búfer donde se almacenará el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="e9caf-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9caf-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9caf-111">Remarks</span></span>  
 <span data-ttu-id="e9caf-112">En plataformas de Windows, `pContext` debe ser un `CONTEXT` estructura (que se definen en WinNT.h) que sea adecuada para el tipo de equipo especificado por el [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="e9caf-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="e9caf-113">`contextFlags`debe tener los mismos valores que la `ContextFlags` campo de la `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="e9caf-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="e9caf-114">El `CONTEXT` estructura es específica del procesador; consulte el archivo WinNT.h para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e9caf-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9caf-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9caf-115">Requirements</span></span>  
 <span data-ttu-id="e9caf-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9caf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9caf-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9caf-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9caf-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9caf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9caf-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9caf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9caf-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9caf-120">See Also</span></span>  
 [<span data-ttu-id="e9caf-121">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9caf-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="e9caf-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e9caf-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e9caf-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="e9caf-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
