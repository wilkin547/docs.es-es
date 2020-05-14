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
ms.openlocfilehash: 9f521eb942f37b8cf1d00bcc672071a69692b876
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396646"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="8a674-102">ICorDebugValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a674-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="8a674-103">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad con matrices mayores de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="8a674-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a674-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8a674-104">Methods</span></span>  
  
|<span data-ttu-id="8a674-105">Método</span><span class="sxs-lookup"><span data-stu-id="8a674-105">Method</span></span>|<span data-ttu-id="8a674-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a674-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a674-107">Método GetSize64</span><span class="sxs-lookup"><span data-stu-id="8a674-107">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="8a674-108">Obtiene el tamaño, en bytes, de este `ICorDebugValue3` objeto.</span><span class="sxs-lookup"><span data-stu-id="8a674-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a674-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a674-109">Remarks</span></span>  
 <span data-ttu-id="8a674-110">El método [ICorDebugValue::FUL](icordebugvalue3-getsize64-method.md) devuelve un tamaño de objeto comprendido entre 0 y 2.147.483.647 bytes.</span><span class="sxs-lookup"><span data-stu-id="8a674-110">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="8a674-111">En el .NET Framework 4,5, el tamaño de las matrices puede superar los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="8a674-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="8a674-112">La `ICorDebugValue3` interfaz le permite determinar el tamaño de estas matrices.</span><span class="sxs-lookup"><span data-stu-id="8a674-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a674-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a674-113">Requirements</span></span>  
 <span data-ttu-id="8a674-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a674-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a674-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a674-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a674-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a674-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a674-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a674-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a674-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a674-118">See also</span></span>

- [<span data-ttu-id="8a674-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8a674-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8a674-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="8a674-120">Debugging</span></span>](index.md)
