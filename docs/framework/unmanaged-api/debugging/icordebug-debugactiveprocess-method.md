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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84137e7163101f7eaa54a45df0fbaa4e7bcf70fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404591"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="c05ad-102">ICorDebug::DebugActiveProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="c05ad-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="c05ad-103">Asocia al depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="c05ad-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c05ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c05ad-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c05ad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c05ad-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="c05ad-106">[in] El identificador del proceso al que va a adjuntar el depurador.</span><span class="sxs-lookup"><span data-stu-id="c05ad-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="c05ad-107">[in] Valor booleano que se establece en `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y envía las devoluciones de llamada no administradas; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c05ad-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="c05ad-108">[out] Un puntero a la dirección de un objeto de "ICorDebugProcess" que representa el proceso al que se ha adjuntado el depurador.</span><span class="sxs-lookup"><span data-stu-id="c05ad-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c05ad-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c05ad-109">Remarks</span></span>  
 <span data-ttu-id="c05ad-110">No se admite la depuración de interoperabilidad en plataformas Win9x y no x86, como plataformas basadas en IA-64 y AMD64-based.</span><span class="sxs-lookup"><span data-stu-id="c05ad-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c05ad-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c05ad-111">Requirements</span></span>  
 <span data-ttu-id="c05ad-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c05ad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c05ad-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c05ad-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c05ad-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c05ad-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c05ad-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c05ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c05ad-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c05ad-116">See Also</span></span>  
 [<span data-ttu-id="c05ad-117">ICorDebug (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c05ad-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
