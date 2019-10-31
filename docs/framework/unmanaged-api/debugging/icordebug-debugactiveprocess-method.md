---
title: ICorDebug::DebugActiveProcess (Método)
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 5b988b110100cd159b8e262573df409847d635c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134123"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="9dcbf-102">ICorDebug::DebugActiveProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="9dcbf-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="9dcbf-103">Asocia el depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="9dcbf-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dcbf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dcbf-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dcbf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9dcbf-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="9dcbf-106">de IDENTIFICADOR del proceso al que se va a adjuntar el depurador.</span><span class="sxs-lookup"><span data-stu-id="9dcbf-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="9dcbf-107">de Valor booleano que se establece en `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9dcbf-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="9dcbf-108">enuncia Puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.</span><span class="sxs-lookup"><span data-stu-id="9dcbf-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dcbf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9dcbf-109">Remarks</span></span>  
 <span data-ttu-id="9dcbf-110">No se admite la depuración de interoperabilidad en las plataformas Win9x y no x86, como las plataformas basadas en IA-64 y AMD64.</span><span class="sxs-lookup"><span data-stu-id="9dcbf-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dcbf-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dcbf-111">Requirements</span></span>  
 <span data-ttu-id="9dcbf-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dcbf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dcbf-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9dcbf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9dcbf-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dcbf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dcbf-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dcbf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dcbf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dcbf-116">See also</span></span>

- [<span data-ttu-id="9dcbf-117">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dcbf-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
