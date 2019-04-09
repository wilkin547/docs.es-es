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
ms.openlocfilehash: fecbcff0fd124b94aeeecf82e23d9875c34ebb9b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091582"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="1479a-102">ICorDebugRegisterSet::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="1479a-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="1479a-103">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1479a-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1479a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1479a-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1479a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1479a-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="1479a-106">[in] El tamaño, en bytes, de la `context` matriz.</span><span class="sxs-lookup"><span data-stu-id="1479a-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="1479a-107">[in, out] Una matriz de bytes que componen el Win32 `CONTEXT` estructura para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="1479a-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1479a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1479a-108">Remarks</span></span>  
 <span data-ttu-id="1479a-109">El depurador debe llamar a esta función en lugar de Win32 `GetThreadContext` funcione, porque el subproceso puede encontrarse en un estado de "secuestro" donde su contexto cambió temporalmente.</span><span class="sxs-lookup"><span data-stu-id="1479a-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="1479a-110">Los datos devueltos son Win32 `CONTEXT` estructura para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="1479a-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="1479a-111">Para los marcos no hoja, los clientes deberían comprobar qué registros son válidos mediante el uso de [GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="1479a-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1479a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1479a-112">Requirements</span></span>  
 <span data-ttu-id="1479a-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1479a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1479a-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1479a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1479a-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1479a-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1479a-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1479a-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1479a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1479a-117">See also</span></span>

- [<span data-ttu-id="1479a-118">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1479a-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="1479a-119">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1479a-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
