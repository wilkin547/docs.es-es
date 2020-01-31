---
title: ICorDebugVirtualUnwinder::Next (método)
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: 06d5377ef123cc3f9c91fbfbcf0b0f17a14eb629
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790814"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="c65ac-102">ICorDebugVirtualUnwinder::Next (método)</span><span class="sxs-lookup"><span data-stu-id="c65ac-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="c65ac-103">Avanza hasta el contexto del llamador.</span><span class="sxs-lookup"><span data-stu-id="c65ac-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c65ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c65ac-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="c65ac-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c65ac-105">Parameters</span></span>  
 <span data-ttu-id="c65ac-106">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="c65ac-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c65ac-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c65ac-107">Return Value</span></span>  
 <span data-ttu-id="c65ac-108">`S_OK` Si el desenredado se realizó correctamente o `CORDBG_S_AT_END_OF_STACK` si el desenredado no se puede completar porque no hay más marcos.</span><span class="sxs-lookup"><span data-stu-id="c65ac-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="c65ac-109">Si se devuelve un error HRESULT, las API ICorDebug devolverán `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="c65ac-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c65ac-110">Notas</span><span class="sxs-lookup"><span data-stu-id="c65ac-110">Remarks</span></span>  
 <span data-ttu-id="c65ac-111">El rastreador de pila debe garantizar que permite avanzar, de manera que una posible llamada a `Next` devuelva un error HRESULT o `CORDBG_S_AT_END_OF_STACK`.</span><span class="sxs-lookup"><span data-stu-id="c65ac-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="c65ac-112">Devolver `S_OK` indefinidamente puede producir un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="c65ac-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c65ac-113">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c65ac-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c65ac-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c65ac-114">Requirements</span></span>  
 <span data-ttu-id="c65ac-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c65ac-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c65ac-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c65ac-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c65ac-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c65ac-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c65ac-118">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c65ac-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65ac-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c65ac-119">See also</span></span>

- [<span data-ttu-id="c65ac-120">ICorDebugMemoryBuffer (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c65ac-120">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="c65ac-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c65ac-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
