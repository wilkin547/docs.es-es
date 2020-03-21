---
title: ICorDebugProcess2::SetUnmanagedBreakpoint (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
ms.openlocfilehash: fb8b8f3e29c141e91587a4d0cdc81cdabccdbc9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178648"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="1a1a1-102">ICorDebugProcess2::SetUnmanagedBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="1a1a1-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="1a1a1-103">Establece un punto de interrupción no administrado en el desplazamiento de imagen nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="1a1a1-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a1a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a1a1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a1a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a1a1-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="1a1a1-106">[en] Objeto `CORDB_ADDRESS` que especifica el desplazamiento de imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="1a1a1-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="1a1a1-107">[en] El tamaño, en bytes, de la `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="1a1a1-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="1a1a1-108">[fuera] Matriz que contiene el código de operación que se reemplaza por el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="1a1a1-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="1a1a1-109">[fuera] Puntero al número de bytes `buffer` devueltos en la matriz.</span><span class="sxs-lookup"><span data-stu-id="1a1a1-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a1a1-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1a1a1-110">Remarks</span></span>  
 <span data-ttu-id="1a1a1-111">Si el desplazamiento de imagen nativa está dentro de Common Language Runtime (CLR), se omitirá el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="1a1a1-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="1a1a1-112">Esto permite que CLR evite distribuir un punto de interrupción fuera de banda, cuando el depurador establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="1a1a1-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a1a1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a1a1-113">Requirements</span></span>  
 <span data-ttu-id="1a1a1-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a1a1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a1a1-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a1a1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a1a1-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a1a1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a1a1-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a1a1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
