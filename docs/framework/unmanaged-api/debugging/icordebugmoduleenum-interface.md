---
title: Interfaz ICorDebugModuleEnum
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum
helpviewer_keywords:
- ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 2fb93cd6-6d47-4fdc-a9a0-047726fd03a1
topic_type:
- apiref
ms.openlocfilehash: 08d16393a04888cd3f1a03fa209a1fceac28520b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724759"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="17e5d-102">Interfaz ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="17e5d-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="17e5d-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="17e5d-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17e5d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="17e5d-104">Methods</span></span>  
  
|<span data-ttu-id="17e5d-105">Método</span><span class="sxs-lookup"><span data-stu-id="17e5d-105">Method</span></span>|<span data-ttu-id="17e5d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="17e5d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17e5d-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="17e5d-107">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="17e5d-108">Obtiene el número especificado de `ICorDebugModule` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="17e5d-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17e5d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17e5d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17e5d-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="17e5d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17e5d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17e5d-111">Requirements</span></span>  

 <span data-ttu-id="17e5d-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17e5d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17e5d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17e5d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17e5d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17e5d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17e5d-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17e5d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17e5d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17e5d-116">See also</span></span>

- [<span data-ttu-id="17e5d-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="17e5d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
