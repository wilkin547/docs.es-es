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
ms.openlocfilehash: 5fa042223e47961dad0a6799ab8ca999ef76e285
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791091"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="2ac16-102">ICorDebugValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ac16-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="2ac16-103">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="2ac16-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ac16-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2ac16-104">Methods</span></span>  
  
|<span data-ttu-id="2ac16-105">Método</span><span class="sxs-lookup"><span data-stu-id="2ac16-105">Method</span></span>|<span data-ttu-id="2ac16-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2ac16-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ac16-107">GetSize64 (método)</span><span class="sxs-lookup"><span data-stu-id="2ac16-107">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="2ac16-108">Obtiene el tamaño, en bytes, de este objeto `ICorDebugValue3`.</span><span class="sxs-lookup"><span data-stu-id="2ac16-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ac16-109">Notas</span><span class="sxs-lookup"><span data-stu-id="2ac16-109">Remarks</span></span>  
 <span data-ttu-id="2ac16-110">El método [ICorDebugValue::FUL](icordebugvalue3-getsize64-method.md) devuelve un tamaño de objeto comprendido entre 0 y 2.147.483.647 bytes.</span><span class="sxs-lookup"><span data-stu-id="2ac16-110">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="2ac16-111">En el .NET Framework 4,5, el tamaño de las matrices puede superar los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="2ac16-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="2ac16-112">La interfaz de `ICorDebugValue3` permite determinar el tamaño de estas matrices.</span><span class="sxs-lookup"><span data-stu-id="2ac16-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ac16-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2ac16-113">Requirements</span></span>  
 <span data-ttu-id="2ac16-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ac16-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ac16-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ac16-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ac16-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ac16-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ac16-117">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ac16-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac16-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ac16-118">See also</span></span>

- [<span data-ttu-id="2ac16-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2ac16-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2ac16-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="2ac16-120">Debugging</span></span>](index.md)
