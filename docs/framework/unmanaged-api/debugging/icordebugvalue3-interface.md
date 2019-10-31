---
title: ICorDebugValue3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 1f46866a1b975455acd294221e38ef3b4c358660
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140210"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="e7ed0-102">ICorDebugValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7ed0-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="e7ed0-103">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="e7ed0-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7ed0-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e7ed0-104">Methods</span></span>  
  
|<span data-ttu-id="e7ed0-105">Método</span><span class="sxs-lookup"><span data-stu-id="e7ed0-105">Method</span></span>|<span data-ttu-id="e7ed0-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7ed0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7ed0-107">GetSize64 (método)</span><span class="sxs-lookup"><span data-stu-id="e7ed0-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="e7ed0-108">Obtiene el tamaño, en bytes, de este objeto `ICorDebugValue3`.</span><span class="sxs-lookup"><span data-stu-id="e7ed0-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7ed0-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7ed0-109">Remarks</span></span>  
 <span data-ttu-id="e7ed0-110">El método [ICorDebugValue::FUL](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) devuelve un tamaño de objeto comprendido entre 0 y 2.147.483.647 bytes.</span><span class="sxs-lookup"><span data-stu-id="e7ed0-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="e7ed0-111">En el .NET Framework 4,5, el tamaño de las matrices puede superar los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="e7ed0-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="e7ed0-112">La interfaz de `ICorDebugValue3` permite determinar el tamaño de estas matrices.</span><span class="sxs-lookup"><span data-stu-id="e7ed0-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7ed0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7ed0-113">Requirements</span></span>  
 <span data-ttu-id="e7ed0-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7ed0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7ed0-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7ed0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7ed0-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7ed0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7ed0-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7ed0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7ed0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7ed0-118">See also</span></span>

- [<span data-ttu-id="e7ed0-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e7ed0-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e7ed0-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="e7ed0-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
