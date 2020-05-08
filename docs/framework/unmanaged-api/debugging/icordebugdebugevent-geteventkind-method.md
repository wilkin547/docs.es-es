---
title: Método ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 6e3ebdcb5b3e85f6f5a329ed249aa58be903e30f
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976400"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="e28aa-102">Método ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="e28aa-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="e28aa-103">Indica el tipo de evento que este objeto `ICorDebugDebugEvent` representa.</span><span class="sxs-lookup"><span data-stu-id="e28aa-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e28aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e28aa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e28aa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e28aa-105">Parameters</span></span>  
 <span data-ttu-id="e28aa-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="e28aa-106">pDebugEventKind</span></span>  
 <span data-ttu-id="e28aa-107">Un puntero a un miembro de la enumeración [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) que indica el tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="e28aa-107">A pointer to a [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e28aa-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e28aa-108">Remarks</span></span>  
 <span data-ttu-id="e28aa-109">Según el valor de `pDebugEventKind`, se puede llamar a `QueryInterface` para obtener una interfaz de evento de depuración más precisa con datos adicionales.</span><span class="sxs-lookup"><span data-stu-id="e28aa-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e28aa-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e28aa-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e28aa-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e28aa-111">Requirements</span></span>  
 <span data-ttu-id="e28aa-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e28aa-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e28aa-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e28aa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e28aa-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e28aa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e28aa-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e28aa-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28aa-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e28aa-116">See also</span></span>

- [<span data-ttu-id="e28aa-117">Interfaz ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e28aa-117">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="e28aa-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e28aa-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
