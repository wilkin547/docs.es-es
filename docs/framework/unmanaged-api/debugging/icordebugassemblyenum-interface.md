---
title: Interfaz ICorDebugAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum
helpviewer_keywords:
- ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: 891ceb43-5161-421e-a0bf-299962fd7efd
topic_type:
- apiref
ms.openlocfilehash: 1893f1f08d727606fecda7669719760179bb76f9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778056"
---
# <a name="icordebugassemblyenum-interface"></a><span data-ttu-id="bbc19-102">Interfaz ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="bbc19-102">ICorDebugAssemblyEnum Interface</span></span>

<span data-ttu-id="bbc19-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugAssembly.</span><span class="sxs-lookup"><span data-stu-id="bbc19-103">Implements ICorDebugEnum methods and enumerates ICorDebugAssembly arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bbc19-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="bbc19-104">Methods</span></span>  
  
|<span data-ttu-id="bbc19-105">Método</span><span class="sxs-lookup"><span data-stu-id="bbc19-105">Method</span></span>|<span data-ttu-id="bbc19-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbc19-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bbc19-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="bbc19-107">Next Method</span></span>](icordebugassemblyenum-next-method.md)|<span data-ttu-id="bbc19-108">Obtiene el número especificado de instancias de `ICorDebugAssembly` en la enumeración, a partir de la posición actual.</span><span class="sxs-lookup"><span data-stu-id="bbc19-108">Gets the specified number of `ICorDebugAssembly` instances in the enumeration, starting from the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbc19-109">Notas</span><span class="sxs-lookup"><span data-stu-id="bbc19-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bbc19-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="bbc19-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbc19-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="bbc19-111">Requirements</span></span>  
 <span data-ttu-id="bbc19-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbc19-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbc19-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbc19-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbc19-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbc19-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbc19-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbc19-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbc19-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbc19-116">See also</span></span>

- [<span data-ttu-id="bbc19-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bbc19-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
