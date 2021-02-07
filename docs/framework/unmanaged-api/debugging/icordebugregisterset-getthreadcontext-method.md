---
description: 'Más información acerca de: ICorDebugRegisterSet:: GetThreadContext (método)'
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
ms.openlocfilehash: be6384562858d04b6e139eda83c172c09f2dfc0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690813"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="c3ccb-103">ICorDebugRegisterSet::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="c3ccb-103">ICorDebugRegisterSet::GetThreadContext Method</span></span>

<span data-ttu-id="c3ccb-104">Obtiene el contexto del subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="c3ccb-104">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3ccb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3ccb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3ccb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3ccb-106">Parameters</span></span>  

 `contextSize`  
 <span data-ttu-id="c3ccb-107">de Tamaño, en bytes, de la `context` matriz.</span><span class="sxs-lookup"><span data-stu-id="c3ccb-107">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="c3ccb-108">[in, out] Matriz de bytes que componen la `CONTEXT` estructura de Win32 para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="c3ccb-108">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3ccb-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c3ccb-109">Remarks</span></span>  

 <span data-ttu-id="c3ccb-110">El depurador debe llamar a esta función en lugar de a la función de Win32 `GetThreadContext` , ya que el subproceso puede estar en un estado "secuestrado" donde su contexto ha cambiado temporalmente.</span><span class="sxs-lookup"><span data-stu-id="c3ccb-110">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="c3ccb-111">Los datos devueltos son una `CONTEXT` estructura Win32 para la plataforma actual.</span><span class="sxs-lookup"><span data-stu-id="c3ccb-111">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="c3ccb-112">En el caso de los marcos no hoja, los clientes deben comprobar qué registros son válidos mediante [ICorDebugRegisterSet:: getregistersavailable (](icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="c3ccb-112">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3ccb-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3ccb-113">Requirements</span></span>  

 <span data-ttu-id="c3ccb-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3ccb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3ccb-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3ccb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3ccb-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3ccb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3ccb-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ccb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ccb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3ccb-118">See also</span></span>

- [<span data-ttu-id="c3ccb-119">ICorDebugRegisterSet (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3ccb-119">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="c3ccb-120">ICorDebugRegisterSet2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3ccb-120">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
