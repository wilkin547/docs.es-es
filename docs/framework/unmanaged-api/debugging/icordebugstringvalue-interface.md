---
title: Interfaz ICorDebugStringValue
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cfaf886d09d843f4dbf61af55a9388454b050ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957425"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="1b56c-102">Interfaz ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="1b56c-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="1b56c-103">Subclase de ICorDebugHeapValue que se aplica a los valores de cadena.</span><span class="sxs-lookup"><span data-stu-id="1b56c-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b56c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1b56c-104">Methods</span></span>  
  
|<span data-ttu-id="1b56c-105">Método</span><span class="sxs-lookup"><span data-stu-id="1b56c-105">Method</span></span>|<span data-ttu-id="1b56c-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1b56c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b56c-107">GetLength (método)</span><span class="sxs-lookup"><span data-stu-id="1b56c-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="1b56c-108">Obtiene el número de caracteres de la cadena a la que hace `ICorDebugStringValue`referencia este.</span><span class="sxs-lookup"><span data-stu-id="1b56c-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="1b56c-109">GetString (método)</span><span class="sxs-lookup"><span data-stu-id="1b56c-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="1b56c-110">Obtiene la cadena a la que hace `ICorDebugStringValue`referencia este.</span><span class="sxs-lookup"><span data-stu-id="1b56c-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b56c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b56c-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b56c-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1b56c-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b56c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b56c-113">Requirements</span></span>  
 <span data-ttu-id="1b56c-114">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b56c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b56c-115">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="1b56c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b56c-116">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b56c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b56c-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b56c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b56c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b56c-118">See also</span></span>

- [<span data-ttu-id="1b56c-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1b56c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
