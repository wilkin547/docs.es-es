---
description: 'Más información acerca de: interfaz Icordebugexceptionobjectvalue ('
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
ms.openlocfilehash: 67672f9921bab31019a42b742480176e6d0bf3d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693205"
---
# <a name="icordebugexceptionobjectvalue-interface"></a><span data-ttu-id="2f139-103">ICorDebugExceptionObjectValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2f139-103">ICorDebugExceptionObjectValue Interface</span></span>

<span data-ttu-id="2f139-104">Extiende la interfaz "ICorDebugObjectValue" para proporcionar información de seguimiento de la pila de un objeto de excepción administrado.</span><span class="sxs-lookup"><span data-stu-id="2f139-104">Extends the "ICorDebugObjectValue" interface to provide stack trace information from a managed exception object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2f139-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2f139-105">Methods</span></span>  
  
|<span data-ttu-id="2f139-106">Método</span><span class="sxs-lookup"><span data-stu-id="2f139-106">Method</span></span>|<span data-ttu-id="2f139-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f139-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2f139-108">Método EnumerateExceptionCallStack</span><span class="sxs-lookup"><span data-stu-id="2f139-108">EnumerateExceptionCallStack Method</span></span>](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md)|<span data-ttu-id="2f139-109">Obtiene un enumerador para la pila de llamadas incrustada en un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="2f139-109">Gets an enumerator to the call stack embedded in an exception object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f139-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2f139-110">Remarks</span></span>  

 <span data-ttu-id="2f139-111">La llamada a `QueryInterface` se realizará correctamente para los objetos administrados que derivan de <xref:System.Exception?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2f139-111">The call to `QueryInterface` will succeed for managed objects that derive from <xref:System.Exception?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f139-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f139-112">Requirements</span></span>  

 <span data-ttu-id="2f139-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f139-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f139-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f139-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f139-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f139-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f139-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f139-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f139-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f139-117">See also</span></span>

- [<span data-ttu-id="2f139-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2f139-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2f139-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="2f139-119">Debugging</span></span>](index.md)
