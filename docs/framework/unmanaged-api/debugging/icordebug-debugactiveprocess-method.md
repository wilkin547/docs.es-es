---
title: "ICorDebug::DebugActiveProcess (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 10cb2a5323db67c6f5664e13cb1f97d1a807d20c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="d4f32-102">ICorDebug::DebugActiveProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="d4f32-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="d4f32-103">Asocia al depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="d4f32-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f32-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4f32-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4f32-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4f32-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="d4f32-106">[in] El identificador del proceso al que va a adjuntar el depurador.</span><span class="sxs-lookup"><span data-stu-id="d4f32-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="d4f32-107">[in] Valor booleano que se establece en `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y envía las devoluciones de llamada no administradas; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d4f32-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="d4f32-108">[out] Un puntero a la dirección de un objeto de "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.</span><span class="sxs-lookup"><span data-stu-id="d4f32-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4f32-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d4f32-109">Remarks</span></span>  
 <span data-ttu-id="d4f32-110">No se admite la depuración de interoperabilidad en plataformas Win9x y no x86, como plataformas basadas en IA-64 y AMD64-based.</span><span class="sxs-lookup"><span data-stu-id="d4f32-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4f32-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4f32-111">Requirements</span></span>  
 <span data-ttu-id="d4f32-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4f32-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4f32-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4f32-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4f32-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4f32-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4f32-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4f32-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f32-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4f32-116">See Also</span></span>  
 [<span data-ttu-id="d4f32-117">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4f32-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
