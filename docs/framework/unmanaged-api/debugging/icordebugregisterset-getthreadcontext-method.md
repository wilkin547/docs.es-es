---
title: ICorDebugRegisterSet::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 668b3849af9be24e019dc472a0b80067f0e1e0c1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612741"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="d687b-102">ICorDebugRegisterSet::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="d687b-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="d687b-103">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="d687b-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d687b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d687b-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d687b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d687b-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="d687b-106">[in] El tamaño, en bytes, de la `context` matriz.</span><span class="sxs-lookup"><span data-stu-id="d687b-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="d687b-107">[in, out] Una matriz de bytes que componen el Win32 `CONTEXT` estructura para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="d687b-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d687b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d687b-108">Remarks</span></span>  
 <span data-ttu-id="d687b-109">El depurador debe llamar a esta función en lugar de Win32 `GetThreadContext` funcione, porque el subproceso puede encontrarse en un estado de "secuestro" donde su contexto cambió temporalmente.</span><span class="sxs-lookup"><span data-stu-id="d687b-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="d687b-110">Los datos devueltos son Win32 `CONTEXT` estructura para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="d687b-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="d687b-111">Para los marcos no hoja, los clientes deberían comprobar qué registros son válidos mediante el uso de [GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="d687b-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d687b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d687b-112">Requirements</span></span>  
 <span data-ttu-id="d687b-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d687b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d687b-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d687b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d687b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d687b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d687b-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d687b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d687b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d687b-117">See also</span></span>
- [<span data-ttu-id="d687b-118">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d687b-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="d687b-119">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d687b-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
