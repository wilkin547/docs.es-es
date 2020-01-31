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
ms.openlocfilehash: b019c198635373fa6aaea01914dc9747b7486ae0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792876"
---
# <a name="icordebugmoduleenum-interface"></a><span data-ttu-id="2fd6d-102">Interfaz ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="2fd6d-102">ICorDebugModuleEnum Interface</span></span>

<span data-ttu-id="2fd6d-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugModule.</span><span class="sxs-lookup"><span data-stu-id="2fd6d-103">Implements ICorDebugEnum methods, and enumerates ICorDebugModule arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2fd6d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2fd6d-104">Methods</span></span>  
  
|<span data-ttu-id="2fd6d-105">Método</span><span class="sxs-lookup"><span data-stu-id="2fd6d-105">Method</span></span>|<span data-ttu-id="2fd6d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2fd6d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2fd6d-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="2fd6d-107">Next Method</span></span>](icordebugmoduleenum-next-method.md)|<span data-ttu-id="2fd6d-108">Obtiene el número especificado de instancias de `ICorDebugModule` de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="2fd6d-108">Gets the specified number of `ICorDebugModule` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fd6d-109">Notas</span><span class="sxs-lookup"><span data-stu-id="2fd6d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2fd6d-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2fd6d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fd6d-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2fd6d-111">Requirements</span></span>  
 <span data-ttu-id="2fd6d-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fd6d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fd6d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fd6d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fd6d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fd6d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fd6d-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fd6d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd6d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="2fd6d-116">See also</span></span>

- [<span data-ttu-id="2fd6d-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2fd6d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
