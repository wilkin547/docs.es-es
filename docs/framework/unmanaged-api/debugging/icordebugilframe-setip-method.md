---
title: ICorDebugILFrame::SetIP (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
ms.openlocfilehash: 60273d7cf91be04c5fc3041260e4bb146ce9a45e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095432"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="39446-102">ICorDebugILFrame::SetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="39446-102">ICorDebugILFrame::SetIP Method</span></span>
<span data-ttu-id="39446-103">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="39446-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39446-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39446-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39446-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39446-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="39446-106">Ubicación de desplazamiento en el código MSIL.</span><span class="sxs-lookup"><span data-stu-id="39446-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39446-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39446-107">Remarks</span></span>  
 <span data-ttu-id="39446-108">Las llamadas a `SetIP` invalidan inmediatamente todos los marcos y cadenas para el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="39446-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="39446-109">Si el depurador necesita información de fotogramas después de una llamada a `SetIP`, debe realizar un nuevo seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="39446-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="39446-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) intentará mantener el marco de pila en un estado válido.</span><span class="sxs-lookup"><span data-stu-id="39446-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="39446-111">Sin embargo, aunque el marco esté en un estado válido, puede haber problemas como las variables locales sin inicializar.</span><span class="sxs-lookup"><span data-stu-id="39446-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="39446-112">El autor de la llamada es responsable de garantizar la coherencia del programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="39446-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="39446-113">En las plataformas de 64 bits, el puntero de instrucción no se puede sacar de un bloque `catch` o `finally`.</span><span class="sxs-lookup"><span data-stu-id="39446-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="39446-114">Si se llama a `SetIP` para hacer este movimiento en una plataforma de 64 bits, devolverá un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="39446-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39446-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39446-115">Requirements</span></span>  
 <span data-ttu-id="39446-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39446-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39446-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39446-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39446-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39446-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39446-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39446-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
