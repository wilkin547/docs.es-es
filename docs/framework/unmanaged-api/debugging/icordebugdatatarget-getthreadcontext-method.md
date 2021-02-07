---
description: 'Más información sobre: ICorDebugDataTarget:: GetThreadContext (método)'
title: ICorDebugDataTarget::GetThreadContext (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: cf40579aa0a495af4e5e775334d177ca6f3da86f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710639"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="c43e2-103">ICorDebugDataTarget::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="c43e2-103">ICorDebugDataTarget::GetThreadContext Method</span></span>

<span data-ttu-id="c43e2-104">Devuelve el contexto del subproceso actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="c43e2-104">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c43e2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c43e2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c43e2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c43e2-106">Parameters</span></span>  

 `dwThreadID`  
 <span data-ttu-id="c43e2-107">de Identificador del subproceso cuyo contexto se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="c43e2-107">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="c43e2-108">El identificador está definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c43e2-108">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="c43e2-109">de Combinación bit a bit de las marcas dependientes de la plataforma que indican qué partes del contexto se deben leer.</span><span class="sxs-lookup"><span data-stu-id="c43e2-109">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c43e2-110">[in] Tamaño de `pContext`.</span><span class="sxs-lookup"><span data-stu-id="c43e2-110">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="c43e2-111">enuncia Búfer donde se almacenará el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="c43e2-111">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c43e2-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c43e2-112">Remarks</span></span>  

 <span data-ttu-id="c43e2-113">En las plataformas de Windows, `pContext` debe ser una `CONTEXT` estructura (definida en Winnt. h) que sea adecuada para el tipo de equipo especificado por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c43e2-113">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="c43e2-114">`contextFlags` debe tener los mismos valores que el `ContextFlags` campo de la `CONTEXT` estructura.</span><span class="sxs-lookup"><span data-stu-id="c43e2-114">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="c43e2-115">La `CONTEXT` estructura es específica del procesador; Consulte el archivo winnt. h para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c43e2-115">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c43e2-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c43e2-116">Requirements</span></span>  

 <span data-ttu-id="c43e2-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c43e2-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c43e2-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c43e2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c43e2-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c43e2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c43e2-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c43e2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c43e2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c43e2-121">See also</span></span>

- [<span data-ttu-id="c43e2-122">ICorDebugDataTarget (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c43e2-122">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="c43e2-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c43e2-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c43e2-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="c43e2-124">Debugging</span></span>](index.md)
