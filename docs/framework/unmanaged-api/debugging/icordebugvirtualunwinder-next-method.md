---
title: ICorDebugVirtualUnwinder::Next (método)
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: bfc827a1503b0367a442e3f3ca0915bd2aaeb01e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725955"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="52d91-102">ICorDebugVirtualUnwinder::Next (método)</span><span class="sxs-lookup"><span data-stu-id="52d91-102">ICorDebugVirtualUnwinder::Next Method</span></span>

<span data-ttu-id="52d91-103">Avanza hasta el contexto del llamador.</span><span class="sxs-lookup"><span data-stu-id="52d91-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52d91-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52d91-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="52d91-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52d91-105">Parameters</span></span>  

 <span data-ttu-id="52d91-106">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="52d91-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52d91-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52d91-107">Return Value</span></span>  

 <span data-ttu-id="52d91-108">`S_OK` Si el desenredado se realizó correctamente o `CORDBG_S_AT_END_OF_STACK` si el desenredado no se puede completar porque no hay más marcos.</span><span class="sxs-lookup"><span data-stu-id="52d91-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="52d91-109">Si se devuelve un error HRESULT, las API ICorDebug devolverán `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="52d91-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52d91-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52d91-110">Remarks</span></span>  

 <span data-ttu-id="52d91-111">El rastreador de pila debe garantizar que permite avanzar, de manera que una posible llamada a `Next` devuelva un error HRESULT o `CORDBG_S_AT_END_OF_STACK`.</span><span class="sxs-lookup"><span data-stu-id="52d91-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="52d91-112">Devolver `S_OK` indefinidamente puede producir un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="52d91-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="52d91-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="52d91-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52d91-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52d91-114">Requirements</span></span>  

 <span data-ttu-id="52d91-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52d91-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52d91-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="52d91-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="52d91-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52d91-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52d91-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52d91-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52d91-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52d91-119">See also</span></span>

- [<span data-ttu-id="52d91-120">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="52d91-120">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="52d91-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="52d91-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
