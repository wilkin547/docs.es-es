---
description: 'Más información sobre: ICorDebugVirtualUnwinder:: Next (método)'
title: ICorDebugVirtualUnwinder::Next (método)
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: b509e8e4fb24c66764999e67ba7e36299ce7f570
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790521"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="c87e4-103">ICorDebugVirtualUnwinder::Next (método)</span><span class="sxs-lookup"><span data-stu-id="c87e4-103">ICorDebugVirtualUnwinder::Next Method</span></span>

<span data-ttu-id="c87e4-104">Avanza hasta el contexto del llamador.</span><span class="sxs-lookup"><span data-stu-id="c87e4-104">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c87e4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c87e4-105">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="c87e4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c87e4-106">Parameters</span></span>  

 <span data-ttu-id="c87e4-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c87e4-107">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c87e4-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c87e4-108">Return Value</span></span>  

 <span data-ttu-id="c87e4-109">`S_OK` Si el desenredado se realizó correctamente o `CORDBG_S_AT_END_OF_STACK` si el desenredado no se puede completar porque no hay más marcos.</span><span class="sxs-lookup"><span data-stu-id="c87e4-109">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="c87e4-110">Si se devuelve un error HRESULT, las API ICorDebug devolverán `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="c87e4-110">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c87e4-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c87e4-111">Remarks</span></span>  

 <span data-ttu-id="c87e4-112">El rastreador de pila debe garantizar que permite avanzar, de manera que una posible llamada a `Next` devuelva un error HRESULT o `CORDBG_S_AT_END_OF_STACK`.</span><span class="sxs-lookup"><span data-stu-id="c87e4-112">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="c87e4-113">Devolver `S_OK` indefinidamente puede producir un bucle infinito.</span><span class="sxs-lookup"><span data-stu-id="c87e4-113">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c87e4-114">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c87e4-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c87e4-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c87e4-115">Requirements</span></span>  

 <span data-ttu-id="c87e4-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c87e4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c87e4-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c87e4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c87e4-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c87e4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c87e4-119">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c87e4-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c87e4-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c87e4-120">See also</span></span>

- [<span data-ttu-id="c87e4-121">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="c87e4-121">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="c87e4-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c87e4-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
