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
ms.openlocfilehash: fdc3d96fd5ad9a6ff59b863cd3f0450283ea0146
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721379"
---
# <a name="icordebugilframesetip-method"></a><span data-ttu-id="a17c4-102">ICorDebugILFrame::SetIP (Método)</span><span class="sxs-lookup"><span data-stu-id="a17c4-102">ICorDebugILFrame::SetIP Method</span></span>

<span data-ttu-id="a17c4-103">Establece el puntero de instrucción en la ubicación de desplazamiento especificada en el código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="a17c4-103">Sets the instruction pointer to the specified offset location in the Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a17c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a17c4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a17c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a17c4-105">Parameters</span></span>  

 `nOffset`  
 <span data-ttu-id="a17c4-106">Ubicación de desplazamiento en el código MSIL.</span><span class="sxs-lookup"><span data-stu-id="a17c4-106">The offset location in the MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a17c4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a17c4-107">Remarks</span></span>  

 <span data-ttu-id="a17c4-108">Llama a para `SetIP` invalidar inmediatamente todos los marcos y cadenas del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="a17c4-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="a17c4-109">Si el depurador necesita información de fotogramas después de una llamada a `SetIP` , debe realizar un nuevo seguimiento de la pila.</span><span class="sxs-lookup"><span data-stu-id="a17c4-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="a17c4-110">[ICorDebug](icordebug-interface.md) intentará mantener el marco de pila en un estado válido.</span><span class="sxs-lookup"><span data-stu-id="a17c4-110">[ICorDebug](icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="a17c4-111">Sin embargo, aunque el marco esté en un estado válido, puede haber problemas como las variables locales sin inicializar.</span><span class="sxs-lookup"><span data-stu-id="a17c4-111">However, even if the frame is in a valid state, there still may be problems such as uninitialized local variables.</span></span> <span data-ttu-id="a17c4-112">El autor de la llamada es responsable de garantizar la coherencia del programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a17c4-112">The caller is responsible for ensuring the coherency of the running program.</span></span>  
  
 <span data-ttu-id="a17c4-113">En las plataformas de 64 bits, el puntero de instrucción no se puede sacar de un `catch` `finally` bloque o.</span><span class="sxs-lookup"><span data-stu-id="a17c4-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="a17c4-114">Si `SetIP` se llama a para hacer este tipo de movimiento en una plataforma de 64 bits, devolverá un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="a17c4-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a17c4-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a17c4-115">Requirements</span></span>  

 <span data-ttu-id="a17c4-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a17c4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a17c4-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a17c4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a17c4-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a17c4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a17c4-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a17c4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
