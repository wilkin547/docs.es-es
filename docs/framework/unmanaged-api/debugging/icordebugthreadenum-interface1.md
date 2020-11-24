---
title: Interfaz ICorDebugThreadEnum
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
ms.openlocfilehash: ca7668f23671721477c561774bab03279c4c18c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678563"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="d1f5e-102">Interfaz ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="d1f5e-102">ICorDebugThreadEnum Interface</span></span>

<span data-ttu-id="d1f5e-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="d1f5e-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1f5e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d1f5e-104">Methods</span></span>  
  
|<span data-ttu-id="d1f5e-105">Método</span><span class="sxs-lookup"><span data-stu-id="d1f5e-105">Method</span></span>|<span data-ttu-id="d1f5e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1f5e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1f5e-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="d1f5e-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="d1f5e-108">Obtiene el número especificado de `ICorDebugThread` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="d1f5e-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1f5e-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1f5e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1f5e-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d1f5e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1f5e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1f5e-111">Requirements</span></span>  

 <span data-ttu-id="d1f5e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1f5e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1f5e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1f5e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1f5e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1f5e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1f5e-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1f5e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f5e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1f5e-116">See also</span></span>

- [<span data-ttu-id="d1f5e-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d1f5e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
