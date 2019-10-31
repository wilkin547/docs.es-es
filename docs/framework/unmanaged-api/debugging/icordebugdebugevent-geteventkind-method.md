---
title: Método ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 92606d7bd0a277dd327ce4fd430ce963a260206d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136657"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="98439-102">Método ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="98439-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="98439-103">Indica el tipo de evento que este objeto `ICorDebugDebugEvent` representa.</span><span class="sxs-lookup"><span data-stu-id="98439-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98439-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98439-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98439-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98439-105">Parameters</span></span>  
 <span data-ttu-id="98439-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="98439-106">pDebugEventKind</span></span>  
 <span data-ttu-id="98439-107">Un puntero a un miembro de la enumeración [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) que indica el tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="98439-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98439-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98439-108">Remarks</span></span>  
 <span data-ttu-id="98439-109">Según el valor de `pDebugEventKind`, se puede llamar a `QueryInterface` para obtener una interfaz de evento de depuración más precisa con datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="98439-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="98439-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="98439-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98439-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98439-111">Requirements</span></span>  
 <span data-ttu-id="98439-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98439-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98439-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98439-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98439-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98439-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98439-115">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98439-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98439-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="98439-116">See also</span></span>

- [<span data-ttu-id="98439-117">ICorDebugDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98439-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="98439-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="98439-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
