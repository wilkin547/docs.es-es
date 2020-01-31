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
ms.openlocfilehash: fa154d0bb48f4ecd4fc6a50ce22fd13c592b7c40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782730"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="1561b-102">ICorDebugExceptionObjectValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1561b-102">ICorDebugExceptionObjectValue Interface</span></span>
<span data-ttu-id="1561b-103">Extiende la interfaz "ICorDebugObjectValue" para proporcionar información de seguimiento de la pila de un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="1561b-103">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1561b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1561b-104">Methods</span></span>  
  
|<span data-ttu-id="1561b-105">Método</span><span class="sxs-lookup"><span data-stu-id="1561b-105">Method</span></span>|<span data-ttu-id="1561b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1561b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1561b-107">EnumerateExceptionCallStack (método)</span><span class="sxs-lookup"><span data-stu-id="1561b-107">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="1561b-108">Obtiene un enumerador para la pila de llamadas incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="1561b-108">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1561b-109">Notas</span><span class="sxs-lookup"><span data-stu-id="1561b-109">Remarks</span></span>  
 <span data-ttu-id="1561b-110">La llamada a `QueryInterface` se realizará correctamente para los objetos administrados que derivan de <xref:System.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1561b-110">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1561b-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1561b-111">Requirements</span></span>  
 <span data-ttu-id="1561b-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1561b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1561b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1561b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1561b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1561b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1561b-115">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1561b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1561b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1561b-116">See also</span></span>

- [<span data-ttu-id="1561b-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1561b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1561b-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="1561b-118">Debugging</span></span>](index.md)
