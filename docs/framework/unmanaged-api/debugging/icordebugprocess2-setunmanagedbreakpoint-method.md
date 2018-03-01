---
title: "ICorDebugProcess2::SetUnmanagedBreakpoint (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 825917d48aaab5d9d5ce482fa600ca02efa158ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="26a56-102">ICorDebugProcess2::SetUnmanagedBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="26a56-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="26a56-103">Establece un punto de interrupción no administrado en el desplazamiento de imagen nativa especificado.</span><span class="sxs-lookup"><span data-stu-id="26a56-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26a56-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26a56-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26a56-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="26a56-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="26a56-106">[in] Un `CORDB_ADDRESS` objeto que especifica el desplazamiento de imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="26a56-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="26a56-107">[in] El tamaño, en bytes, de la `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="26a56-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="26a56-108">[out] Una matriz que contiene el código de operación que se ha reemplazado por el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="26a56-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="26a56-109">[out] Un puntero al número de bytes devueltos en el `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="26a56-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26a56-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26a56-110">Remarks</span></span>  
 <span data-ttu-id="26a56-111">Si el desplazamiento de imagen nativa está dentro de common language runtime (CLR), el punto de interrupción se omitirá.</span><span class="sxs-lookup"><span data-stu-id="26a56-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="26a56-112">Esto permite que el CLR evitar enviar un punto de interrupción fuera de banda, cuando el punto de interrupción se establece mediante el depurador.</span><span class="sxs-lookup"><span data-stu-id="26a56-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26a56-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26a56-113">Requirements</span></span>  
 <span data-ttu-id="26a56-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26a56-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26a56-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26a56-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26a56-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26a56-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26a56-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26a56-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
