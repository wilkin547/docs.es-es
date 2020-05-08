---
title: ICorDebugExceptionObjectValue (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue
helpviewer_keywords:
- ICorDebugExceptionObjectValue interface [.NET Framework debugging]
ms.assetid: 43416dd5-8892-4106-9f59-f9143b19ddb4
topic_type:
- apiref
ms.openlocfilehash: 8e4f745440936a39e22faf60d10a05a0bb110606
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975958"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="c2bb3-102">ICorDebugExceptionObjectValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2bb3-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="c2bb3-103">Extiende la interfaz "ICorDebugObjectValue" para proporcionar información de seguimiento de la pila de un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="c2bb3-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2bb3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c2bb3-104">Methods</span></span>  
  
|<span data-ttu-id="c2bb3-105">Método</span><span class="sxs-lookup"><span data-stu-id="c2bb3-105">Method</span></span>|<span data-ttu-id="c2bb3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2bb3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2bb3-107">Método EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="c2bb3-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="c2bb3-108">Obtiene un enumerador para la pila de llamadas incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="c2bb3-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2bb3-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c2bb3-109">Remarks</span></span>  
 <span data-ttu-id="c2bb3-110">La llamada a `QueryInterface` se realizará correctamente para los objetos administrados que derivan de <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c2bb3-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2bb3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2bb3-111">Requirements</span></span>  
 <span data-ttu-id="c2bb3-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2bb3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2bb3-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2bb3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2bb3-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2bb3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2bb3-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2bb3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2bb3-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c2bb3-116">See also</span></span>

- [<span data-ttu-id="c2bb3-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c2bb3-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c2bb3-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="c2bb3-118">Debugging</span></span>](index.md)
