---
title: "ICorDebugCode::CreateBreakpoint (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 214d032129613230b8c55cdd286ea637227a626e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="48d39-102">ICorDebugCode::CreateBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="48d39-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="48d39-103">Crea un punto de interrupción en este segmento de código en el desplazamiento especificado.</span><span class="sxs-lookup"><span data-stu-id="48d39-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d39-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48d39-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48d39-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48d39-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="48d39-106">[in] Desplazamiento en el que se va a crear el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="48d39-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="48d39-107">[out] Un puntero a la dirección de un objeto de "ICorDebugFunctionBreakpoint" que representa el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="48d39-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48d39-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="48d39-108">Remarks</span></span>  
 <span data-ttu-id="48d39-109">Antes de que el punto de interrupción está activo, se debe agregar al objeto de proceso.</span><span class="sxs-lookup"><span data-stu-id="48d39-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="48d39-110">Si este código es código de lenguaje intermedio (MSIL) de Microsoft y no hay un just-in-time (JIT)-versión nativa compilada del código, el punto de interrupción se aplicará en el código compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="48d39-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="48d39-111">(El mismo es verdadero si el código compilado JIT más adelante).</span><span class="sxs-lookup"><span data-stu-id="48d39-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d39-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48d39-112">Requirements</span></span>  
 <span data-ttu-id="48d39-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d39-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d39-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48d39-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48d39-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48d39-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48d39-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d39-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d39-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="48d39-117">See Also</span></span>  
 
