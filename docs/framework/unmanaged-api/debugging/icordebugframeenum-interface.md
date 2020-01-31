---
title: Interfaz ICorDebugFrameEnum
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
ms.openlocfilehash: 6cc1ef5f778902efaa53156fbefe334046c82114
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794533"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="ca841-102">Interfaz ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="ca841-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="ca841-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="ca841-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca841-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ca841-104">Methods</span></span>  
  
|<span data-ttu-id="ca841-105">Método</span><span class="sxs-lookup"><span data-stu-id="ca841-105">Method</span></span>|<span data-ttu-id="ca841-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca841-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca841-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="ca841-107">Next Method</span></span>](icordebugframeenum-next-method.md)|<span data-ttu-id="ca841-108">Obtiene el número especificado de instancias de `ICorDebugFrame` de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="ca841-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca841-109">Notas</span><span class="sxs-lookup"><span data-stu-id="ca841-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca841-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ca841-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca841-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ca841-111">Requirements</span></span>  
 <span data-ttu-id="ca841-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca841-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca841-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca841-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca841-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca841-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca841-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca841-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca841-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca841-116">See also</span></span>

- [<span data-ttu-id="ca841-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ca841-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
