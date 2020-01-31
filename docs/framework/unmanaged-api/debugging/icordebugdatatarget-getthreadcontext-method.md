---
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
ms.openlocfilehash: 3eace2d91b3bb6e637a659b8b49a31450ebc2c42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783728"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="30a91-102">ICorDebugDataTarget::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="30a91-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="30a91-103">Devuelve el contexto del subproceso actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="30a91-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a91-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30a91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30a91-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="30a91-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="30a91-106">de Identificador del subproceso cuyo contexto se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="30a91-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="30a91-107">El identificador está definido por el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="30a91-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="30a91-108">de Combinación bit a bit de las marcas dependientes de la plataforma que indican qué partes del contexto se deben leer.</span><span class="sxs-lookup"><span data-stu-id="30a91-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="30a91-109">[in] Tamaño de `pContext`.</span><span class="sxs-lookup"><span data-stu-id="30a91-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="30a91-110">enuncia Búfer donde se almacenará el contexto del subproceso.</span><span class="sxs-lookup"><span data-stu-id="30a91-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30a91-111">Notas</span><span class="sxs-lookup"><span data-stu-id="30a91-111">Remarks</span></span>  
 <span data-ttu-id="30a91-112">En las plataformas de Windows, `pContext` debe ser una estructura de `CONTEXT` (definida en Winnt. h) que sea adecuada para el tipo de equipo especificado por el método [ICorDebugDataTarget:: GetPlatform (](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="30a91-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="30a91-113">`contextFlags` deben tener los mismos valores que el campo `ContextFlags` de la estructura `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="30a91-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="30a91-114">La estructura de `CONTEXT` es específica del procesador; Consulte el archivo winnt. h para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="30a91-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a91-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="30a91-115">Requirements</span></span>  
 <span data-ttu-id="30a91-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30a91-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a91-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30a91-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30a91-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30a91-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30a91-119">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30a91-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a91-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="30a91-120">See also</span></span>

- [<span data-ttu-id="30a91-121">ICorDebugDataTarget (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30a91-121">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="30a91-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="30a91-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="30a91-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="30a91-123">Debugging</span></span>](index.md)
