---
title: ICorDebugCode::CreateBreakpoint (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f8be1a1831bc00eea3cfb659b46b67b6a78711
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747723"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="91113-102">ICorDebugCode::CreateBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="91113-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="91113-103">Crea un punto de interrupción en este segmento de código en el desplazamiento especificado.</span><span class="sxs-lookup"><span data-stu-id="91113-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91113-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91113-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91113-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91113-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="91113-106">[in] Desplazamiento en el que se va a crear el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="91113-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="91113-107">[out] Un puntero a la dirección de un objeto "ICorDebugFunctionBreakpoint" que representa el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="91113-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91113-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91113-108">Remarks</span></span>  
 <span data-ttu-id="91113-109">Antes de que el punto de interrupción está activo, se debe agregar al objeto del proceso.</span><span class="sxs-lookup"><span data-stu-id="91113-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="91113-110">Si este código es código de lenguaje intermedio (MSIL) de Microsoft, y hay un just-in-time (JIT)-se aplicará la versión nativa compilada del código, el punto de interrupción en el código compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="91113-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="91113-111">(El mismo es true si el código compilado JIT más adelante).</span><span class="sxs-lookup"><span data-stu-id="91113-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91113-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91113-112">Requirements</span></span>  
 <span data-ttu-id="91113-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91113-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91113-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91113-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91113-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91113-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91113-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91113-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91113-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="91113-117">See also</span></span>
