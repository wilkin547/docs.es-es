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
ms.openlocfilehash: 8137d5477b75b864e223852cf524ac8c5b6c0f2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792093"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="0170e-102">ICorDebugRegisterSet::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="0170e-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="0170e-103">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="0170e-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0170e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0170e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0170e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0170e-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="0170e-106">de Tamaño, en bytes, de la matriz de `context`.</span><span class="sxs-lookup"><span data-stu-id="0170e-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="0170e-107">[in, out] Matriz de bytes que componen la estructura de `CONTEXT` Win32 para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="0170e-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0170e-108">Notas</span><span class="sxs-lookup"><span data-stu-id="0170e-108">Remarks</span></span>  
 <span data-ttu-id="0170e-109">El depurador debe llamar a esta función en lugar de a la función `GetThreadContext` de Win32, porque el subproceso puede estar en un estado "secuestrado" donde su contexto ha cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="0170e-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="0170e-110">Los datos devueltos son una estructura de `CONTEXT` Win32 para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="0170e-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="0170e-111">En el caso de los marcos no hoja, los clientes deben comprobar qué registros son válidos mediante [ICorDebugRegisterSet:: getregistersavailable (](icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="0170e-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0170e-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0170e-112">Requirements</span></span>  
 <span data-ttu-id="0170e-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0170e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0170e-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0170e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0170e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0170e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0170e-116">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0170e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0170e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0170e-117">See also</span></span>

- [<span data-ttu-id="0170e-118">ICorDebugRegisterSet (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0170e-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="0170e-119">ICorDebugRegisterSet2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0170e-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
