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
ms.openlocfilehash: 1173091a5f2d8814747c93f827150afe39b8b309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33399126"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="25469-102">ICorDebugCode::CreateBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="25469-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="25469-103">Crea un punto de interrupción en este segmento de código en el desplazamiento especificado.</span><span class="sxs-lookup"><span data-stu-id="25469-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25469-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25469-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25469-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25469-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="25469-106">[in] Desplazamiento en el que se va a crear el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="25469-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="25469-107">[out] Un puntero a la dirección de un objeto de "ICorDebugFunctionBreakpoint" que representa el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="25469-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25469-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25469-108">Remarks</span></span>  
 <span data-ttu-id="25469-109">Antes de que el punto de interrupción está activo, se debe agregar al objeto de proceso.</span><span class="sxs-lookup"><span data-stu-id="25469-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="25469-110">Si este código es código de lenguaje intermedio (MSIL) de Microsoft y no hay un just-in-time (JIT)-versión nativa compilada del código, el punto de interrupción se aplicará en el código compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="25469-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="25469-111">(El mismo es verdadero si el código compilado JIT más adelante).</span><span class="sxs-lookup"><span data-stu-id="25469-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25469-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25469-112">Requirements</span></span>  
 <span data-ttu-id="25469-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25469-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25469-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25469-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25469-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25469-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25469-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25469-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25469-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="25469-117">See Also</span></span>  
 
