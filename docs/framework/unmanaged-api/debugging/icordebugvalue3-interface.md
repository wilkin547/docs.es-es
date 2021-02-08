---
description: 'Más información acerca de: interfaz Icordebugvalue3 ('
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
ms.openlocfilehash: e5868b91d23426a2d8dd8fed87b13ec61fef95ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794655"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="4421b-103">ICorDebugValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4421b-103">ICorDebugValue3 Interface</span></span>

<span data-ttu-id="4421b-104">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="4421b-104">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4421b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4421b-105">Methods</span></span>  
  
|<span data-ttu-id="4421b-106">Método</span><span class="sxs-lookup"><span data-stu-id="4421b-106">Method</span></span>|<span data-ttu-id="4421b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4421b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4421b-108">Método GetSize64</span><span class="sxs-lookup"><span data-stu-id="4421b-108">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="4421b-109">Obtiene el tamaño, en bytes, de este `ICorDebugValue3` objeto.</span><span class="sxs-lookup"><span data-stu-id="4421b-109">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4421b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4421b-110">Remarks</span></span>  

 <span data-ttu-id="4421b-111">El método [ICorDebugValue::FUL](icordebugvalue3-getsize64-method.md) devuelve un tamaño de objeto comprendido entre 0 y 2.147.483.647 bytes.</span><span class="sxs-lookup"><span data-stu-id="4421b-111">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="4421b-112">En el .NET Framework 4,5, el tamaño de las matrices puede superar los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="4421b-112">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="4421b-113">La `ICorDebugValue3` interfaz le permite determinar el tamaño de estas matrices.</span><span class="sxs-lookup"><span data-stu-id="4421b-113">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4421b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4421b-114">Requirements</span></span>  

 <span data-ttu-id="4421b-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4421b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4421b-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4421b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4421b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4421b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4421b-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4421b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4421b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4421b-119">See also</span></span>

- [<span data-ttu-id="4421b-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4421b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4421b-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="4421b-121">Debugging</span></span>](index.md)
