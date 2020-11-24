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
ms.openlocfilehash: 6a0c33799b2b2aaa48e3b18b7b4bb37643508bd4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678888"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="1302f-102">ICorDebugExceptionObjectValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1302f-102">ICorDebugExceptionObjectValue Interface</span></span>

<span data-ttu-id="1302f-103">Extiende la interfaz "ICorDebugObjectValue" para proporcionar información de seguimiento de la pila de un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="1302f-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1302f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1302f-104">Methods</span></span>  
  
|<span data-ttu-id="1302f-105">Método</span><span class="sxs-lookup"><span data-stu-id="1302f-105">Method</span></span>|<span data-ttu-id="1302f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1302f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1302f-107">Método EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="1302f-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="1302f-108">Obtiene un enumerador para la pila de llamadas incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="1302f-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1302f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1302f-109">Remarks</span></span>  

 <span data-ttu-id="1302f-110">La llamada a `QueryInterface` se realizará correctamente para los objetos administrados que derivan de <xref:System.Exception?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="1302f-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1302f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1302f-111">Requirements</span></span>  

 <span data-ttu-id="1302f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1302f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1302f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1302f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1302f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1302f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1302f-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1302f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1302f-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1302f-116">See also</span></span>

- [<span data-ttu-id="1302f-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1302f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1302f-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="1302f-118">Debugging</span></span>](index.md)
