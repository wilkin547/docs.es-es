---
title: "ICorDebugRegisterSet::GetThreadContext (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fba96f9d86f1df5c0800c8cafb9c7fd1b0a6f8c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="97559-102">ICorDebugRegisterSet::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="97559-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="97559-103">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="97559-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97559-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97559-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97559-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="97559-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="97559-106">[in] El tamaño, en bytes, de la `context` matriz.</span><span class="sxs-lookup"><span data-stu-id="97559-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="97559-107">[entrada, salida] Una matriz de bytes que compone la Win32 `CONTEXT` estructura de la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="97559-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97559-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97559-108">Remarks</span></span>  
 <span data-ttu-id="97559-109">El depurador debe llamar a esta función en lugar de Win32 `GetThreadContext` funciona, ya que el subproceso podría encontrarse en un estado de "secuestro" su contexto de donde hubiera cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="97559-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="97559-110">Los datos devueltos son Win32 `CONTEXT` estructura de la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="97559-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="97559-111">Para los marcos no hoja, los clientes deberían comprobar qué registros son válidos mediante el uso de [ICorDebugRegisterSet:: GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="97559-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97559-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97559-112">Requirements</span></span>  
 <span data-ttu-id="97559-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97559-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97559-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97559-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97559-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97559-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97559-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97559-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97559-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="97559-117">See Also</span></span>  
 [<span data-ttu-id="97559-118">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="97559-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="97559-119">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="97559-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
