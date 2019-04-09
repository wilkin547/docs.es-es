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
ms.openlocfilehash: b880358ed0d7bce4896217bc07c6ef6268d62962
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076281"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="93b7b-102">ICorDebug::DebugActiveProcess (Método)</span><span class="sxs-lookup"><span data-stu-id="93b7b-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="93b7b-103">Asocia al depurador a un proceso existente.</span><span class="sxs-lookup"><span data-stu-id="93b7b-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93b7b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93b7b-104">Syntax</span></span>  
  
```  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93b7b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93b7b-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="93b7b-106">[in] El identificador del proceso al que va a adjuntar el depurador.</span><span class="sxs-lookup"><span data-stu-id="93b7b-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="93b7b-107">[in] Valor booleano que se establece en `true` si el depurador debe comportarse como el depurador de Win32 para el proceso y enviar las devoluciones de llamada no administradas; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="93b7b-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="93b7b-108">[out] Un puntero a la dirección de un objeto "ICorDebugProcess" que representa el proceso al que se ha vinculado el depurador.</span><span class="sxs-lookup"><span data-stu-id="93b7b-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93b7b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93b7b-109">Remarks</span></span>  
 <span data-ttu-id="93b7b-110">No se admite la depuración de interoperabilidad en plataformas Win9x y no x86, como las plataformas basadas en IA-64 y basado en AMD64.</span><span class="sxs-lookup"><span data-stu-id="93b7b-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93b7b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93b7b-111">Requirements</span></span>  
 <span data-ttu-id="93b7b-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93b7b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93b7b-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93b7b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93b7b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93b7b-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="93b7b-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="93b7b-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="93b7b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="93b7b-116">See also</span></span>

- [<span data-ttu-id="93b7b-117">ICorDebug (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="93b7b-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
