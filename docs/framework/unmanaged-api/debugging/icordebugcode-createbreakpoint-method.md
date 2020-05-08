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
ms.openlocfilehash: 40582b1289875d5151ea96e3153c6e4760737e84
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893807"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="3bd80-102">ICorDebugCode::CreateBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="3bd80-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="3bd80-103">Crea un punto de interrupción en este segmento de código en el desplazamiento especificado.</span><span class="sxs-lookup"><span data-stu-id="3bd80-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bd80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bd80-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bd80-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bd80-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="3bd80-106">de Desplazamiento en el que se va a crear el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="3bd80-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="3bd80-107">enuncia Puntero a la dirección de un objeto "ICorDebugFunctionBreakpoint" que representa el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="3bd80-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bd80-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3bd80-108">Remarks</span></span>  
 <span data-ttu-id="3bd80-109">Antes de que el punto de interrupción esté activo, debe agregarse al objeto de proceso.</span><span class="sxs-lookup"><span data-stu-id="3bd80-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="3bd80-110">Si este código es código del lenguaje intermedio de Microsoft (MSIL) y hay una versión nativa y compilada Just-in-Time (JIT) del código, el punto de interrupción se aplicará también en el código compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="3bd80-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="3bd80-111">(Lo mismo sucede si el código se compila posteriormente).</span><span class="sxs-lookup"><span data-stu-id="3bd80-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bd80-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bd80-112">Requirements</span></span>  
 <span data-ttu-id="3bd80-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bd80-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bd80-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3bd80-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3bd80-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bd80-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bd80-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bd80-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
