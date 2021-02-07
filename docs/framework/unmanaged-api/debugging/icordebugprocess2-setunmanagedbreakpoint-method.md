---
description: 'Más información sobre: ICorDebugProcess2:: SetUnmanagedBreakpoint ((método)'
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
ms.openlocfilehash: 7989f0fc9908941513b7d099fde81c79cef82c5b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746547"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="5cd74-103">ICorDebugProcess2::SetUnmanagedBreakpoint (Método)</span><span class="sxs-lookup"><span data-stu-id="5cd74-103">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>

<span data-ttu-id="5cd74-104">Establece un punto de interrupción no administrado en el desplazamiento de imagen nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="5cd74-104">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd74-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5cd74-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cd74-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5cd74-106">Parameters</span></span>  

 `address`  
 <span data-ttu-id="5cd74-107">de `CORDB_ADDRESS` Objeto que especifica el desplazamiento de la imagen nativa.</span><span class="sxs-lookup"><span data-stu-id="5cd74-107">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="5cd74-108">de Tamaño, en bytes, de la `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="5cd74-108">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="5cd74-109">enuncia Una matriz que contiene el código de operación reemplazado por el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5cd74-109">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="5cd74-110">enuncia Puntero al número de bytes devuelto en la `buffer` matriz.</span><span class="sxs-lookup"><span data-stu-id="5cd74-110">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5cd74-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5cd74-111">Remarks</span></span>  

 <span data-ttu-id="5cd74-112">Si el desplazamiento de la imagen nativa se encuentra dentro del Common Language Runtime (CLR), se omitirá el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5cd74-112">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="5cd74-113">Esto permite al CLR evitar el envío de un punto de interrupción fuera de banda, cuando el depurador establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5cd74-113">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cd74-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5cd74-114">Requirements</span></span>  

 <span data-ttu-id="5cd74-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cd74-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cd74-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cd74-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cd74-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cd74-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cd74-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cd74-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
